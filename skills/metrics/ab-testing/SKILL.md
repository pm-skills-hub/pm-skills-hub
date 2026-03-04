---
name: ab-test-design
description: Generate a complete A/B test design document for any product experiment. Use this skill whenever the user asks to design an A/B test, experiment, split test, or feature flag rollout with measurement. Also trigger when someone says "help me write up the experiment," "how do I test this hypothesis," "I need a test plan," or "what's the right sample size for this." Produces a full experiment design doc covering hypothesis, metrics, sample size rationale, variant definitions, guardrail metrics, and a decision framework. Includes scripts for sample size calculation and metric instrumentation checks.
---

# A/B Test Design Skill

## Purpose
Produce a rigorous, complete A/B test design document that gives the team a shared, pre-registered understanding of what is being tested, why, how success is defined, and what will happen with each possible result — before a single line of experiment code is written.

---

## Background: Why Pre-Registration Matters

The most common experimentation failure mode is outcome bias — defining "success" after seeing the data. A well-written experiment design doc locks in:
- The hypothesis (falsifiable, directional)
- The primary metric (one, chosen before launch)
- The minimum detectable effect (not reverse-engineered from results)
- The decision rules (what action follows each outcome)

If the team can't agree on these before the experiment runs, the results will be disputed after.

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What is being tested?** (the change being made — UI, copy, flow, algorithm, pricing, etc.)
- **What is the hypothesis?** (what do you believe will happen and why?)
- **What is the primary metric?** (the one metric that determines success)
- **What is the current baseline for that metric?** (needed for sample size calculation)
- **What is the minimum meaningful improvement?** (the smallest effect worth detecting)
- **How much traffic is available?** (daily or weekly eligible users/sessions)
- **Are there guardrail metrics?** (metrics that must not regress)
- **What is the experiment unit?** (user, session, account, device)
- **How long can the experiment run?** (any deadline constraints?)
- **Is there a holdback or control group already defined?**

---

## Step 2: Hypothesis Framework

A good hypothesis has three components:

```
If we [make this change],
then [this metric] will [increase/decrease] by [X%],
because [the mechanism / user behavior change we expect].
```

**Good hypothesis:**
> If we add a progress indicator to the onboarding flow, then 7-day activation will increase by 10%, because users will have a clearer sense of how close they are to completing setup and will be less likely to abandon mid-flow.

**Bad hypothesis:**
> If we improve onboarding, users will engage more.

Help the user sharpen their hypothesis before proceeding. A vague hypothesis produces an uninterpretable result.

---

## Step 3: Sample Size Calculation

Use the script below to calculate required sample size before writing the design doc. This prevents under-powered experiments from being run and producing false negatives.

### Sample Size Calculator Script

```bash
#!/bin/bash
# sample_size_calc.sh
# Calculates required sample size per variant for a two-sample proportion test
# Usage: ./sample_size_calc.sh <baseline_rate> <mde> <significance> <power>
# Example: ./sample_size_calc.sh 0.25 0.05 0.05 0.80

BASELINE=${1:-0.25}       # Current conversion/metric rate (e.g., 0.25 = 25%)
MDE=${2:-0.05}            # Minimum detectable effect as absolute lift (e.g., 0.05 = 5pp)
ALPHA=${3:-0.05}          # Significance level (default: 0.05)
POWER=${4:-0.80}          # Statistical power (default: 0.80)

python3 - <<EOF
import math

baseline = $BASELINE
mde = $MDE
alpha = $ALPHA
power = $POWER

# Z-scores for common alpha and power values
z_alpha = 1.96   # for alpha=0.05, two-tailed
z_power = 0.842  # for power=0.80

p1 = baseline
p2 = baseline + mde
p_bar = (p1 + p2) / 2

numerator = (z_alpha * math.sqrt(2 * p_bar * (1 - p_bar)) + z_power * math.sqrt(p1 * (1 - p1) + p2 * (1 - p2))) ** 2
denominator = (p2 - p1) ** 2

n_per_variant = math.ceil(numerator / denominator)

print(f"\n=== Sample Size Calculation ===")
print(f"Baseline rate:             {p1:.1%}")
print(f"Target rate (with MDE):    {p2:.1%}")
print(f"Minimum detectable effect: {mde:.1%} lift")
print(f"Significance level (α):    {alpha}")
print(f"Statistical power:         {power:.0%}")
print(f"\nRequired per variant:      {n_per_variant:,} users")
print(f"Total required (2 variants): {n_per_variant * 2:,} users")
EOF
```

**Usage:**
```bash
chmod +x sample_size_calc.sh
./sample_size_calc.sh 0.25 0.05 0.05 0.80
```

**Output example:**
```
=== Sample Size Calculation ===
Baseline rate:               25.0%
Target rate (with MDE):      30.0%
Minimum detectable effect:   5.0% lift
Significance level (α):      0.05
Statistical power:           80%

Required per variant:        583 users
Total required (2 variants): 1,166 users
```

Use this output to fill in the "Sample Size & Duration" section of the design doc.

---

### Runtime Estimator Script

After calculating sample size, estimate how long the experiment needs to run:

```bash
#!/bin/bash
# runtime_estimator.sh
# Estimates experiment runtime given traffic volume
# Usage: ./runtime_estimator.sh <required_n_per_variant> <daily_eligible_users> <traffic_split>

REQUIRED_N=${1:-1000}          # Required per variant from sample_size_calc.sh
DAILY_USERS=${2:-500}          # Daily eligible users hitting the experiment
TRAFFIC_SPLIT=${3:-0.50}       # % of traffic in experiment (0.50 = 50%)

python3 - <<EOF
import math

required = $REQUIRED_N
daily = $DAILY_USERS
split = $TRAFFIC_SPLIT

users_per_day_per_variant = (daily * split) / 2
days_required = math.ceil(required / users_per_day_per_variant)
weeks_required = days_required / 7

print(f"\n=== Runtime Estimate ===")
print(f"Required per variant:          {required:,}")
print(f"Daily eligible users:          {daily:,}")
print(f"Traffic in experiment:         {split:.0%}")
print(f"Users/day per variant:         {users_per_day_per_variant:.0f}")
print(f"\nEstimated runtime:             {days_required} days ({weeks_required:.1f} weeks)")

if days_required < 7:
    print("⚠️  Warning: Less than 1 week. Run for at least 7 days to capture weekly cycles.")
if days_required > 42:
    print("⚠️  Warning: Runtime exceeds 6 weeks. Consider increasing MDE or traffic allocation.")
EOF
```

---

### Metric Instrumentation Check Script

Before launching, verify the metrics being tracked are firing correctly in the data layer:

```bash
#!/bin/bash
# metric_check.sh
# Validates that experiment events are present in the events table
# Requires: psql or BigQuery CLI configured with appropriate credentials
# Usage: ./metric_check.sh <experiment_id> <start_date>

EXPERIMENT_ID=${1:-"exp_onboarding_v2"}
START_DATE=${2:-$(date -d "yesterday" +%Y-%m-%d)}

echo "Checking instrumentation for experiment: $EXPERIMENT_ID"
echo "From: $START_DATE"
echo "---"

# Check assignment events
psql $DATABASE_URL -c "
SELECT
  variant,
  COUNT(DISTINCT user_id) AS assigned_users,
  MIN(event_time) AS first_assignment,
  MAX(event_time) AS last_assignment
FROM experiment_assignments
WHERE experiment_id = '$EXPERIMENT_ID'
  AND event_date >= '$START_DATE'
GROUP BY variant
ORDER BY variant;
"

# Check primary metric events
psql $DATABASE_URL -c "
SELECT
  ea.variant,
  COUNT(DISTINCT ea.user_id) AS assigned,
  COUNT(DISTINCT pm.user_id) AS converted,
  ROUND(COUNT(DISTINCT pm.user_id)::numeric / NULLIF(COUNT(DISTINCT ea.user_id), 0) * 100, 2) AS conversion_rate_pct
FROM experiment_assignments ea
LEFT JOIN primary_metric_events pm
  ON ea.user_id = pm.user_id
  AND pm.event_date >= ea.assignment_date
WHERE ea.experiment_id = '$EXPERIMENT_ID'
  AND ea.event_date >= '$START_DATE'
GROUP BY ea.variant
ORDER BY ea.variant;
"

echo "---"
echo "✅ If both queries return rows for each variant, instrumentation is healthy."
echo "⚠️  If conversion_rate_pct is 0% for all variants, primary metric events may not be logging."
```

---

## Step 4: A/B Test Design Doc Structure

---

### [Experiment Name] — A/B Test Design

**Experiment ID:** [exp_feature_name_v1]  
**Status:** Draft / In Review / Approved / Running / Complete  
**PM Owner:** [Name]  
**Eng Owner:** [Name]  
**Start Date:** [Date]  
**Planned End Date:** [Date]

---

#### 1. Hypothesis

> If we [change], then [primary metric] will [direction] by [X%], because [mechanism].

**Confidence in hypothesis:** High / Medium / Low  
**Source of confidence:** [User research, qualitative signal, prior experiment, competitive observation]

---

#### 2. Experiment Design

| Parameter | Value |
|---|---|
| Experiment unit | User / Session / Account |
| Variants | Control (A), Treatment (B) [add more if applicable] |
| Traffic split | 50% / 50% [adjust as needed] |
| Eligible population | [Who qualifies — new users, paid accounts, specific feature users, etc.] |
| Exclusions | [Who is excluded and why] |
| Randomization method | [User ID hash / feature flag / server-side split] |

**Variant descriptions:**
- **Control (A):** [Exact current behavior — be specific]
- **Treatment (B):** [Exact change being tested — be specific, no ambiguity]

---

#### 3. Metrics

**Primary metric (one only):**
- [Metric name] — [Definition] — [Current baseline]

*This is the only metric that determines success or failure. Choose it before the experiment runs and do not change it.*

**Secondary metrics (directional signal, not decision criteria):**
- [Metric 2] — [Definition]
- [Metric 3] — [Definition]

**Guardrail metrics (must not regress):**
- [Metric] — [Acceptable threshold — e.g., "must not drop more than 2%"]
- [Metric] — [Threshold]

---

#### 4. Sample Size & Duration

*Generated using `sample_size_calc.sh` and `runtime_estimator.sh`*

| Parameter | Value |
|---|---|
| Baseline rate | [X%] |
| Minimum detectable effect | [X%] |
| Required per variant | [N users] |
| Daily eligible traffic | [N users/day] |
| Traffic allocation | [X% of eligible] |
| Estimated runtime | [N days / N weeks] |
| Planned runtime | [N days — add buffer for weekly cycle coverage] |

**Runtime notes:**
- Minimum runtime: 7 days regardless of traffic volume (capture Mon-Sun weekly cycle)
- Flag if runtime exceeds 6 weeks — reconsider MDE or traffic allocation

---

#### 5. Decision Framework

Pre-register the decision rules. This must be written before seeing data.

| Outcome | Criteria | Decision |
|---|---|---|
| **Ship** | Primary metric lifts ≥ MDE, p < 0.05, no guardrail regression | Ship Treatment to 100% |
| **Iterate** | Positive trend but underpowered, or mixed signals | Extend runtime or redesign |
| **Kill** | No lift detected (p > 0.05, practical significance low) | Revert to Control; document learnings |
| **Rollback** | Guardrail metric regresses beyond threshold | Immediately stop experiment |

**Riskiest assumption:** [The one thing that most needs to be true for this experiment to work]

---

#### 6. Instrumentation Plan

Before launching, confirm:

- [ ] Assignment event fires on exposure (not on page load)
- [ ] Primary metric event has user ID and timestamp
- [ ] Variant attribution is logged with each primary metric event
- [ ] Guardrail metric events are tracked
- [ ] `metric_check.sh` returns healthy counts for both variants within 24 hours of launch

**Events to instrument:**

| Event Name | Trigger | Properties Required |
|---|---|---|
| `experiment_assigned` | User enters experiment | user_id, variant, timestamp |
| `[primary_metric_event]` | [When it fires] | user_id, timestamp, variant |
| `[guardrail_event]` | [When it fires] | user_id, timestamp |

---

#### 7. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Novelty effect inflates early results | Medium | High | Enforce minimum 2-week runtime |
| Sample ratio mismatch (SRM) | Low | High | Check assignment counts daily for first 3 days |
| Instrumentation gap discovered post-launch | Medium | High | Run `metric_check.sh` within 24h of launch |
| Interference between experiments | Low | Medium | Confirm no overlapping experiments on same population |

---

#### 8. Open Questions

| # | Question | Owner | Due |
|---|----------|-------|-----|
| 1 | | | |

---

#### 9. Post-Experiment Checklist

- [ ] Primary metric result recorded with confidence interval
- [ ] Decision documented with rationale
- [ ] Learnings written up (even for null results)
- [ ] Feature flag cleaned up or shipped
- [ ] Results shared with relevant stakeholders
- [ ] Findings fed back into OST / roadmap

---

## Output Format

- Produce the full design doc as structured Markdown
- Run `sample_size_calc.sh` logic mentally to populate the sample size table if the user provides baseline rate, MDE, and traffic volume
- Flag any section where pre-registration is being violated (e.g., metric defined after seeing data)
- Offer to produce a lightweight 1-page experiment brief for lower-stakes tests on request
