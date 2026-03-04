---
name: exec-product-summary
description: Generate a concise, high-altitude executive or board-level product summary. Use this skill whenever the user needs to communicate product progress, strategy, or decisions to senior leadership, executives, or a board. Trigger when someone asks for an "exec summary," "board update," "leadership update," "product summary for leadership," "QBR product section," or says "I need to present this to the exec team" or "help me write the product section of the board deck." Also trigger when someone says "how do I explain this to leadership" or "I need to go up a level." Produces an outcome-framed, appropriately brief summary that speaks the language of business impact, risk, and strategy — not features and tasks.
---

# Executive / Board-Level Product Summary Skill

## Purpose
Produce a tight, outcome-focused product summary written at the altitude executives and board members actually operate at — surfacing business impact, strategic progress, risks, and decisions needed, without feature-level detail or internal process narrative.

---

## Step 1: The Altitude Problem

The most common failure mode in exec-level product communication is writing at the wrong altitude. Before drafting, internalize these distinctions:

| ❌ Wrong altitude | ✅ Right altitude |
|---|---|
| "We shipped the new onboarding flow" | "30-day activation improved 12% — on track to hit Q2 goal" |
| "We're working on the reporting module" | "Reporting gaps were cited in 3 of our last 5 churn conversations; fix in progress" |
| "The team had a strong sprint" | "We're one sprint ahead of plan for the platform migration" |
| "We're exploring AI features" | "AI-assisted triage is in beta with 8 accounts; early signal shows 20% time savings" |
| "There are some technical debt concerns" | "Infra risk: current architecture limits scale past 500 concurrent users; decision needed on mitigation approach by [date]" |

Executives want to know: **Are we on track? What's at risk? What do you need from me?**

---

## Step 2: Gather Context

Ask in a single batch if not provided:

- **What is the audience?** (CEO/C-suite, board of directors, investors, cross-functional leadership, steering committee)
- **What is the occasion?** (QBR, board meeting, monthly business review, ad hoc update, fundraising deck section)
- **What time period does this cover?** (quarter, month, since last update)
- **What are the top 2-3 product priorities or bets right now?**
- **What metrics matter most to this audience?** (ARR, activation, retention, NPS, usage, platform health)
- **What's going well?** (wins to highlight)
- **What's at risk or behind?** (be honest — execs hate surprises more than bad news)
- **Are there decisions or asks for the audience?** (approvals, resources, strategic alignment)
- **What is the desired length / format?** (5 bullets, 1-page narrative, slide structure, spoken talking points)

---

## Step 3: Summary Formats

Produce the appropriate format based on audience and occasion.

---

### Format A: 5-Bullet Executive Snapshot

For Slack updates, email summaries, or pre-reads. Maximum signal, minimum words.

---

**Product Update — [Month/Quarter]**

- **On track:** [The most important thing going well, stated as an outcome or metric]
- **Shipped:** [What launched and why it matters — 1 sentence, business impact framing]
- **At risk:** [What's behind, uncertain, or concerning — with a date or decision point]
- **Watching:** [A trend, market signal, or early indicator worth flagging]
- **Need from you:** [A specific ask, decision, or awareness item — or "No action needed"]

---

### Format B: One-Page Narrative Summary

For monthly business reviews, QBR decks, or board pre-reads.

---

**Product Summary — [Quarter / Month]**  
*Author: [Name] | Date: [Date]*

---

#### Strategic Progress

Write 2-3 sentences on whether product is executing against the stated strategy or roadmap bets. Reference the goals the audience already knows about — don't re-explain strategy from scratch.

- Are the big bets on track?
- Has anything changed about the strategic direction and why?
- What's the one thing that happened this period that matters most strategically?

---

#### Key Outcomes & Metrics

Present 3-5 metrics that matter to this audience. Use a simple table or tight list:

| Metric | Last Period | This Period | Target | Trend |
|---|---|---|---|---|
| [Metric 1] | | | | 🟢 / 🟡 / 🔴 |
| [Metric 2] | | | | |
| [Metric 3] | | | | |

Add 1-2 sentences of interpretation — don't make the audience draw their own conclusions from raw numbers.

---

#### What We Shipped

Limit to 2-4 items. For each, write one sentence on **what it does** and one sentence on **why it matters to the business or customers.** Do not list every ticket or improvement.

- **[Feature/Initiative]:** [Business impact statement]
- **[Feature/Initiative]:** [Business impact statement]

---

#### What's At Risk

This is the most important section for building executive trust. Be direct.

For each risk:
- Name it clearly (not "there are some challenges")
- State the business impact if it materializes
- State what you're doing about it
- State if you need anything from the audience

**Risk format:**
> **[Risk name]:** [What it is and why it matters]. [Current mitigation or status]. [Ask, if any.]

---

#### Decisions Needed

If the audience needs to make or ratify a decision, surface it explicitly:

| Decision | Context | Options | Recommendation | Owner | Due |
|---|---|---|---|---|---|
| [Decision 1] | [1-line context] | [A / B / C] | [Your recommendation] | | |

If no decisions are needed: *"No decisions required this period — provided for awareness."*

---

#### Looking Ahead

2-3 bullets on what to expect next period:
- What will ship or reach a milestone
- What decisions or risks will crystallize
- What you'll be watching

---

### Format C: Board-Level Product Slide Structure

For investors or board members who see the product section of a deck quarterly.

Organize as 4-5 slides (or sections of a single summary page):

1. **Product strategy reminder (1 slide):** The 3 bets or themes the board already knows — just restated for continuity. No changes unless there are changes.
2. **Progress against plan (1 slide):** Key milestones — hit, in progress, or missed. Be visual if possible (timeline or RAG status table).
3. **Key metric trends (1 slide):** 2-3 charts or metric callouts. Lead with the metric that best represents product-market fit or growth health.
4. **Risks and mitigations (1 slide):** Top 2-3 risks. Boards respect honesty about risk far more than false confidence.
5. **Asks and upcoming decisions (1 slide):** What you need from the board — budget, intro, strategic input, or just awareness.

---

### Format D: Spoken Talking Points

For live presentations where the PM is speaking, not the document.

Structure as:
- **Opening hook (30 seconds):** Lead with the most important thing — a number, a customer story, or a strategic signal
- **3 main points (2-3 minutes each):** Progress, risks, and what's next
- **Close with the ask (30 seconds):** Always end with what you need

Produce as bullet-point talking points, not a script. Include transition phrases between sections.

---

## Step 4: Tone & Language Guide

| Use this | Avoid this |
|---|---|
| "Activation improved 12%, driven by..." | "We worked hard on onboarding this quarter" |
| "At risk of missing Q3 target by ~10%" | "Things are a little behind but we're working on it" |
| "Three enterprise accounts cited X as a reason to expand" | "Customers seem to like the new feature" |
| "Decision needed: prioritize A or B for Q3" | "We have some things to figure out" |
| "Competitive risk: [Competitor] launched Y last month" | "The market is moving fast" |
| Numbers with context | Numbers without interpretation |

**Voice:** Confident, direct, and honest. Never defensive. Never over-positive. Executives are pattern-matching for whether you have a clear-eyed view of reality.

---

## Step 5: The "So What" Test

Before finalizing, apply the "so what" test to every sentence:

- Does this sentence tell the audience something that changes how they think about the business or product?
- If not — cut it or elevate it to the insight level

The goal is zero filler sentences. Every line should either report a result, surface a risk, or prompt a decision.

---

## Step 6: Quality Checklist

- [ ] Every metric includes baseline, current, and target (not just "improved")
- [ ] Risks are named directly — not softened into "areas of focus"
- [ ] Decisions needed are explicit with options and a recommendation
- [ ] No feature-level detail that belongs in a sprint review, not a leadership update
- [ ] Length matches the format (5-bullet snapshot is not a page; one-pager is not a deck)
- [ ] "Looking ahead" section is specific (not "we'll continue to execute")

---

## Output Format

- Match the format to the audience and occasion (ask if unclear)
- Default to Format B (one-page narrative) if no specific format is requested
- Keep language concise — if a sentence can be cut without losing meaning, cut it
- Offer to produce multiple formats from the same input (e.g., one-pager + 5-bullet snapshot) on request
- Flag any sections where the user needs to supply data or metrics
