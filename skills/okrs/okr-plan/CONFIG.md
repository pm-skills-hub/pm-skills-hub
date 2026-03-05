# Customizing This Skill

## Quick Start

This OKR drafting skill works out of the box and follows universally applicable OKR best practices. However, you can personalize it to match your team's specific planning cadence, metric definitions, and organizational conventions.

## What to Customize

### 1. OKR Scoring Conventions

**What to look for:** The skill uses Google's 60-70% confidence benchmark for target setting and 0.0-1.0 scoring.

**Why customize:** Some organizations use different scales (0-100, color codes only, or traffic lights without numerical scores) or different confidence thresholds.

**Example:**
- Generic: "Target confidence is 60-70% range"
- Your team: "Target confidence is 70-80% range per our planning guidelines" or "Use red/yellow/green only without numerical scores"

### 2. Alignment Terminology

**What to look for:** The skill refers to "company-level OKRs" and "org-level OKRs" generically.

**Why customize:** Your organization may use different terms like "corporate objectives," "divisional goals," "pillar OKRs," or specific tier names.

**Example:**
- Generic: "Aligned to: [Company or org-level OKR this supports]"
- Your team: "Aligned to: [Division OKR]" or "Supports: [Pillar 2: Platform Reliability]"

### 3. Metric Ownership Conventions

**What to look for:** The "Owner" column in the KR table.

**Why customize:** Some teams assign KRs to individuals, others to sub-teams, and some organizations don't formally assign ownership at all.

**Example:**
- Generic: Owner column with "[Name]"
- Your team: Replace with "DRI" (Directly Responsible Individual), "Squad," or remove the column entirely if your team doesn't assign individual ownership

### 4. Mid-Quarter Cadence

**What to look for:** The "Mid-Quarter Check-In Template" assumes a quarterly planning cycle with mid-quarter reviews.

**Why customize:** Adjust the timing if your team reviews more frequently (monthly, bi-weekly) or at different intervals.

**Example:**
- Generic: "Q[N] Mid-Quarter OKR Check-In"
- Your team: "Q[N] Month 2 Check-In" or "Sprint 6 OKR Review"

## Tips

- **Keep a separate config section:** Add a "Team Conventions" section at the top of your SKILL.md with your customizations documented, making it easier to merge upstream updates.
- **Version your baselines:** If your metrics have seasonal patterns, note that in the baseline guidance so teams don't set targets using anomalous data.
- **Link to your metric definitions:** Add a reference to wherever your team documents canonical metric definitions (data warehouse docs, Amplitude taxonomy, etc.) so people know where to source accurate baselines.