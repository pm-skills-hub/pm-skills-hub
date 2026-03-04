# Customizing This Skill

## Quick Start

This skill works out of the box to generate executive-level product summaries. However, you can customize it to align with your organization's specific reporting conventions, preferred metrics, and communication style.

## What to Customize

### 1. **Metric Priorities**

**What to look for:** The skill asks "What metrics matter most to this audience?" with examples like ARR, activation, retention, NPS.

**Why customize:** Your organization likely has its own north star metrics or KPIs that leadership tracks consistently.

**Example:**
- Generic: "What metrics matter most to this audience? (ARR, activation, retention, NPS, usage, platform health)"
- Customized: "What metrics matter most to this audience? (MRR, WAU/MAU ratio, customer health score, feature adoption rate, infrastructure uptime)"

### 2. **Risk Status Indicators**

**What to look for:** The skill uses emoji indicators like 🟢 / 🟡 / 🔴 in Format B's metric table.

**Why customize:** Your team may prefer RAG status, traffic lights, or numeric scores.

**Example:**
- Generic: "🟢 / 🟡 / 🔴"
- Customized: "On Track / At Risk / Off Track" or "Green / Yellow / Red" or a 1-5 score

### 3. **Reporting Cadence**

**What to look for:** Time periods mentioned like "quarter," "month," "QBR."

**Why customize:** Align with your actual reporting schedule.

**Example:**
- Generic: "What time period does this cover? (quarter, month, since last update)"
- Customized: "What time period does this cover? (bi-weekly sprint demo, monthly ELT meeting, quarterly board meeting)"

### 4. **Audience Roles**

**What to look for:** Audience examples like "CEO/C-suite, board of directors, investors."

**Why customize:** Add your specific leadership structure or committee names.

**Example:**
- Generic: "CEO/C-suite, board of directors, investors, cross-functional leadership, steering committee"
- Customized: "CEO/C-suite, Product Council, Advisory Board, Leadership Team (LT), Executive Steering Committee"

## Tips

- **Keep a separate section:** Add your customizations in a clearly marked section at the end of SKILL.md (under a "## Team Customizations" heading) so you can easily preserve them when updating the skill.
- **Document your metric definitions:** Create a quick reference table in your customization section that defines what each of your organization's key metrics means and how it's calculated.
- **Version your format preferences:** If your organization changes reporting templates, keep a changelog in your customization section noting when and why formats evolved.