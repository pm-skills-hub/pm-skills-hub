---
name: okr-drafting
description: Generate well-structured, outcome-oriented OKRs (Objectives and Key Results) for a product team, individual PM, or organization. Use this skill whenever the user asks to write OKRs, key results, quarterly goals, or planning objectives. Also trigger when someone says "help me write my Q[N] OKRs," "my KRs aren't measuring the right things," "I need to set goals for the quarter," "help me write my objectives," or "review my OKRs." Also trigger when the user pastes existing OKRs and asks for feedback or a rewrite. Produces properly structured OKRs with diagnostic feedback on common failure modes — activity-based KRs, vanity metrics, missing baselines, and misalignment between O and KR.
---

# OKR Drafting Skill

## Purpose
Produce rigorous, outcome-oriented OKRs that give a product team a clear, measurable definition of quarterly success — and diagnose the most common failure modes before they get locked into a planning cycle.

---

## Background: What Makes OKRs Work (and Fail)

OKRs are one of the most widely adopted and most widely misused frameworks in product. The failure modes are predictable and fixable.

### The Anatomy of a Good OKR

```
OBJECTIVE
  └── Key Result 1
  └── Key Result 2
  └── Key Result 3
```

**Objective:** Qualitative, aspirational, motivating. Answers "where are we going and why does it matter?" Should be memorable enough to say out loud without looking at a doc.

**Key Result:** Quantitative, time-bound, outcome-based. Answers "how will we know we got there?" Should be falsifiable — at the end of the quarter, it is either true or it isn't.

---

### The 6 Most Common OKR Failure Modes

Run every draft through these before finalizing:

**1. Activity KRs (the most common)**
> ❌ "Launch the onboarding redesign"  
> ✅ "Increase 7-day activation rate from 32% to 45%"

A KR that describes a thing you will do, not a result you will achieve. If you can check it off regardless of outcome, it's an activity.

**2. Vanity metric KRs**
> ❌ "Increase page views to 1M"  
> ✅ "Increase weekly active users who complete a core workflow from 12K to 18K"

Metrics that go up automatically with time, traffic, or growth — but don't indicate real product health or value delivery.

**3. Missing baseline**
> ❌ "Improve NPS by 10 points"  
> ✅ "Improve NPS from 28 to 38"

Without a baseline, you can't evaluate progress, and the target is unanchored. Always state: from X to Y.

**4. Objective masquerading as a KR**
> ❌ KR: "Deliver a world-class onboarding experience"  
> ✅ KR: "Reduce median time-to-first-value from 14 days to 5 days"

If the "KR" can't be scored on a 0.0-1.0 scale at the end of the quarter, it's not a KR.

**5. Too many KRs**
> ❌ 6 KRs under one objective  
> ✅ 2-4 KRs under one objective

More than 4 KRs means the team is tracking everything and prioritizing nothing. Force the hard choices.

**6. O and KRs don't connect**
> ❌ Objective: "Be the platform teams trust"  
>    KR: "Ship 3 new integrations"  
> ✅ KR: "Achieve 85% platform uptime SLA across all enterprise accounts"

Every KR should be a direct, measurable indicator of the objective being achieved. If you hit all the KRs but haven't made progress on the objective, the KRs are wrong.

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What is the team or individual?** (product team, squad, individual PM, org-level)
- **What quarter and year?**
- **What is the team's primary focus area this quarter?** (growth, retention, platform, expansion, new product, etc.)
- **Are there company-level OKRs this should align to?** (if yes, ask for them)
- **What are the top 1-3 outcomes the team needs to move?** (metrics or qualitative goals)
- **What is currently being worked on?** (helps surface activity-based thinking to reframe)
- **Are there existing OKR drafts to review?** (if yes, run the diagnostic first)
- **How many objectives?** (1-3 is ideal for a product team; 1 for an individual PM)
- **What metrics does the team own?** (helps identify the right KR candidates)

---

## Step 2: OKR Diagnostic (for existing drafts)

If the user provides existing OKRs, run this diagnostic before rewriting:

For each Objective:
- [ ] Is it qualitative and aspirational? (not a metric, not a project name)
- [ ] Is it specific enough to give the team direction? (not "be great at X")
- [ ] Would it motivate someone to come to work? (the "rallying cry" test)

For each Key Result:
- [ ] Is it an outcome, not an activity? (no verbs: "launch," "build," "ship," "create")
- [ ] Does it have a baseline and a target? (from X to Y, not "increase by Z%")
- [ ] Is it time-bound to the quarter?
- [ ] Is it directly connected to its Objective? (if you hit this KR, does it prove the O was achieved?)
- [ ] Can it be scored 0.0-1.0 at quarter-end?
- [ ] Is the target ambitious but achievable? (60-70% confidence of hitting is the Google benchmark)

Report the diagnostic findings before rewriting. Name specific failure modes per KR.

---

## Step 3: OKR Writing Framework

### Writing the Objective

Use this formula as a starting point, then make it human:

> **[Aspirational verb] + [what we're changing or building] + [who benefits or why it matters]**

Examples:
- "Become the go-to platform for mid-market operations teams"
- "Unlock enterprise growth by proving platform reliability at scale"
- "Make activation so fast that new users see value before their trial ends"
- "Establish AI-assisted triage as a core workflow for our clinical users"

**Objective quality tests:**
- Can you say it without reading from a doc?
- Would a new team member know what to work on after hearing it?
- Is it specific to this quarter, or is it something that's always true?

---

### Writing Key Results

**The KR formula:**

> **[Metric] [moves] from [baseline] to [target] by [end of quarter]**

**Metric selection guidance — pick KRs at the right level:**

| Level | Example | When to use |
|---|---|---|
| Outcome metric | "30-day retention improves from 41% to 52%" | When the team has clear influence over the metric |
| Leading indicator | "% of new users completing setup in <10 min increases from 28% to 55%" | When the lagging metric won't move within the quarter |
| Input metric | "12 discovery interviews completed with mid-market ops buyers" | Only for early-stage work where no product metrics exist yet |

**Prefer outcome metrics.** Use leading indicators when the lag is too long. Use input metrics only as a last resort and only for a research or discovery objective.

---

### KR Calibration: Setting the Right Target

Targets should be set so there's approximately a 60-70% chance of hitting them. Targets that are always hit signal sandbagging. Targets that are never hit signal poor goal-setting or misaligned investment.

Use this calibration framework:

| Confidence level | Implication |
|---|---|
| >90% confident | Too easy — raise the bar |
| 60-70% confident | Right tension — ambitious but achievable |
| <40% confident | Too aggressive — or under-resourced |

When setting targets, ask: "If we execute well and nothing goes wrong, where do we land?" That's the upper bound. "What's a realistic outcome given normal friction?" That's the target.

---

## Step 4: OKR Output Format

Produce OKRs in this structure:

---

### Q[N] [Year] OKRs — [Team or Product Area]

*Aligned to: [Company or org-level OKR this supports, if provided]*

---

**O1: [Objective statement]**

| # | Key Result | Baseline | Target | Owner | Confidence |
|---|---|---|---|---|---|
| KR1 | [Outcome metric] | [Current value] | [Q-end target] | [Name] | [%] |
| KR2 | [Outcome metric] | [Current value] | [Q-end target] | [Name] | [%] |
| KR3 | [Outcome metric] | [Current value] | [Q-end target] | [Name] | [%] |

**What this objective requires:**
- [Top 1-2 initiatives or focus areas needed to achieve this]

**What we're not doing to achieve this:**
- [Explicit tradeoffs — what the team will deprioritize to focus here]

---

*(Repeat for O2, O3 if applicable)*

---

### OKR Health Summary

After drafting, produce a quick health check:

| Check | Status | Notes |
|---|---|---|
| All KRs are outcomes, not activities | ✅ / ⚠️ / ❌ | |
| All KRs have baselines | ✅ / ⚠️ / ❌ | |
| All KRs connect directly to their Objective | ✅ / ⚠️ / ❌ | |
| Target confidence is 60-70% range | ✅ / ⚠️ / ❌ | |
| KR count per objective is 2-4 | ✅ / ⚠️ / ❌ | |
| Objectives align to company or org OKRs | ✅ / ⚠️ / ❌ | |

---

## Step 5: Common Rewrites Reference

Use these before/after patterns when coaching the user through rewrites:

| Before (broken) | After (fixed) | Failure mode fixed |
|---|---|---|
| "Ship the new dashboard" | "Increase weekly active use of dashboards from 18% to 35% of accounts" | Activity → Outcome |
| "Improve developer experience" | "Reduce median API integration time from 4 days to 1 day" | Unmeasurable → Metric |
| "Increase NPS by 15 points" | "Increase NPS from 22 to 37 among mid-market accounts" | Missing baseline |
| "Support 10 enterprise deals" | "Sales-assisted pipeline from platform tier increases from $0 to $400K" | Activity → Outcome |
| "Launch AI feature" | "30% of active users adopt AI-assisted triage within 60 days of launch" | Activity → Adoption outcome |
| "Reduce churn" | "Monthly logo churn rate decreases from 3.2% to 2.0% among SMB segment" | Unmeasurable → Specific metric |
| "Complete discovery for X initiative" | "12 customer interviews completed; OST for X initiative reviewed and approved by leadership" | Input KR done right |

---

## Step 6: OKR Alignment Check

If company or org OKRs are provided, run an alignment check:

For each team OKR, ask:
- Which company/org OKR does this directly support?
- If this team hits all its KRs, does it meaningfully move the parent OKR?
- Is there any team KR that doesn't connect to any company objective? (flag for removal or reconsideration)

Produce a simple alignment map:

```
Company O1: [Statement]
  └── Team O1: [Statement] — supports via [metric/mechanism]
  └── Team O2: [Statement] — supports via [metric/mechanism]

Company O2: [Statement]
  └── Team O3: [Statement] — supports via [metric/mechanism]

⚠️ Not aligned to any company OKR:
  └── [Any team OKR that doesn't map up]
```

---

## Step 7: Mid-Quarter Check-In Template

Offer to produce a mid-quarter check-in format after the OKRs are drafted:

**Q[N] Mid-Quarter OKR Check-In**

| KR | Baseline | Current | Target | Score | Status | Notes |
|---|---|---|---|---|---|---|
| [KR1] | | | | [0.0-1.0] | 🟢 On track / 🟡 At risk / 🔴 Off track | |

**At-risk KRs — mitigation actions:**
- [KR at risk]: [What's happening, what we're doing about it, revised forecast]

**Learnings so far:**
- [What the data is telling us that's changing how we think about the quarter]

---

## Output Format

- Default to producing full OKRs in the table format with the health summary
- If the user pastes existing OKRs, run the diagnostic first, report findings, then offer to rewrite
- Always include the "what we're not doing" note under each objective — this is what makes OKRs real
- Flag any KR where the baseline is unknown — it must be sourced before the OKR is finalized
- Offer to produce the mid-quarter check-in template after the OKRs are set
- Cross-reference with the product-strategy-doc skill: each objective should map to a strategic bet
