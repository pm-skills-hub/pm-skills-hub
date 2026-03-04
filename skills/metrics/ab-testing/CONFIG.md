# Customizing This Skill

## Quick Start

This skill works out of the box for any PM designing A/B tests. However, you'll get more value by customizing a few elements to match your team's infrastructure, tooling, and conventions.

## What to Customize

### 1. Database Connections in Scripts

**What to look for:** The `metric_check.sh` script uses `psql $DATABASE_URL` to query experiment data.

**Why customize:** Your team likely uses a different data warehouse (BigQuery, Snowflake, Redshift) or has a different connection pattern.

**Example:**
- **Generic:** `psql $DATABASE_URL -c "SELECT...`
- **Your version:** `bq query --use_legacy_sql=false "SELECT...` or `snowsql -q "SELECT...`

### 2. Event Schema and Table Names

**What to look for:** The instrumentation scripts reference tables like `experiment_assignments`, `primary_metric_events`, and columns like `user_id`, `variant`, `event_date`.

**Why customize:** Your data warehouse likely has different table and column names.

**Example:**
- **Generic:** `FROM experiment_assignments`
- **Your version:** `FROM analytics.experiments.assignment_events` or `FROM prod.experiment_exposure`

### 3. Experiment Naming Convention

**What to look for:** The design doc template uses `[exp_feature_name_v1]` as a placeholder experiment ID.

**Why customize:** Your team may have a standard naming pattern (e.g., `exp-2024-q1-onboarding-progress`, `EXP_001_PRICING`).

**Example:**
- **Generic:** `exp_feature_name_v1`
- **Your version:** Match your experiment tracking system's format

### 4. Owner Role Labels

**What to look for:** The doc template lists "PM Owner" and "Eng Owner".

**Why customize:** Your team might use different role titles (Product Lead, Tech Lead, Data Scientist, etc.).

**Example:**
- **Generic:** PM Owner / Eng Owner
- **Your version:** Product Lead / Engineering DRI / Analytics Partner

### 5. Decision Framework Thresholds

**What to look for:** The decision framework uses `p < 0.05` and generic guardrail thresholds.

**Why customize:** Your team may have different significance thresholds or stricter guardrail standards.

**Example:**
- **Generic:** "must not drop more than 2%"
- **Your version:** Align with your team's risk tolerance and guardrail policy

## Tips

- **Keep customizations in comments:** When you modify scripts, add a comment like `# Modified for BigQuery` so you remember what changed when updating the skill later.
- **Create a local config file:** For database connections and table schemas, consider maintaining a separate `.env` or config file that the scripts source, rather than hardcoding credentials.
- **Version your experiment IDs:** If your team's experiment naming evolves, document the pattern in the design doc template itself so future experiments stay consistent.