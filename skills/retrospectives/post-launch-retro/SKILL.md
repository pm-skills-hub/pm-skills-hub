---
name: post-launch-retro
description: Generate a structured post-launch retrospective document to evaluate what shipped, how the launch went, and what to carry forward. Use this skill whenever the user asks to write a post-launch retro, launch retrospective, post-mortem, ship review, or post-launch review. Also trigger when someone says "let's review how the launch went," "write up our learnings from the release," "what did we ship vs. plan," or "help me close out this launch." Produces a complete retrospective covering metric outcomes, qualitative feedback synthesis, process learnings, and v2 backlog inputs. Pairs with the launch-plan skill.
---

# Post-Launch Retrospective Skill

## Purpose
Produce a structured post-launch retrospective that honestly evaluates what was shipped vs. planned, whether the launch succeeded on its metrics, what customers and the team are saying, and what should change in the next cycle — making the learning durable, not just conversational.

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What launched?** (feature name, brief description, launch date)
- **How long ago did it launch?** (determines which data is available: day-1, week-1, 30-day)
- **What were the original success metrics and targets?** (from the launch plan or PRD)
- **What actually happened to those metrics?** (share numbers if available)
- **What qualitative feedback exists?** (support tickets, NPS comments, CSM notes, sales calls, user interviews)
- **Were there any notable incidents or surprises?** (bugs, unexpected usage patterns, scope that slipped)
- **What did the launch process feel like?** (rushed? smooth? gaps in coordination?)
- **Who should be included in this retro?** (PM only, or cross-functional with Eng/Design/CS/Marketing?)
- **What's the intended use of this doc?** (internal learning, leadership review, feeding v2 planning)

---

## Step 2: Retro Cadence Guidance

Help the user run retros at the right intervals:

| Timing | Focus | Who |
|---|---|---|
| **T+1 (Day 1 check-in)** | Incident detection, early adoption signal, go/no-go for broader rollout | PM + Eng |
| **T+7 (Week 1 review)** | Early metric trends, support ticket volume, first customer reactions | PM + CS + Eng |
| **T+30 (Primary retro)** | Full metric assessment, qualitative synthesis, process retro, v2 inputs | Full cross-functional team |
| **T+90 (Long-tail review)** | Retention of usage, downstream impact on business metrics, strategic learnings | PM + Leadership |

Default to the **T+30 retro** format unless the user specifies otherwise. Note which sections to skip for earlier check-ins.

---

## Step 3: Retro Structure

---

### [Feature Name] — Post-Launch Retrospective

**Launch Date:** [Date]  
**Retro Date:** [Date]  
**Retro Type:** T+7 / T+30 / T+90  
**PM:** [Name]  
**Participants:** [Teams or names]

---

#### 1. Launch Summary

Write 2-3 sentences covering:
- What launched and for whom
- The original goal or hypothesis
- One-line verdict on how it went (honest, not spin)

Example: *"We launched contextual onboarding tooltips for new users in late January targeting a 15% improvement in 30-day activation. Early signals are positive but the metric hasn't fully moved yet — we're still within the measurement window. The launch itself was smooth operationally, though we identified a gap in CS readiness."*

---

#### 2. What We Shipped vs. What We Planned

Be explicit about scope accuracy. This builds planning credibility over time.

| Item | Planned | Shipped | Notes |
|---|---|---|---|
| [Feature component 1] | ✅ | ✅ | |
| [Feature component 2] | ✅ | ✅ | |
| [Feature component 3] | ✅ | ❌ Descoped | Moved to v2 — [reason] |
| [Unplanned addition] | ❌ | ✅ | Added due to [reason] |

**Scope delta summary:** What was descoped and why? What was added? What does this tell us about our estimation or prioritization process?

---

#### 3. Metric Outcomes

Present results clearly, including context for why a metric moved or didn't.

| Metric | Baseline | Target | Actual | Status |
|---|---|---|---|---|
| [Primary metric] | | | | 🟢 Hit / 🟡 Partial / 🔴 Missed |
| [Secondary metric] | | | | |
| [Guardrail metric] | | | | |

**Measurement notes:**
- Specify measurement window (are we still in it?)
- Note any confounds (other launches, seasonality, data anomalies)
- Flag if a metric can't be measured yet and when it will be

**Verdict:** Did the launch achieve its primary goal? Be direct. Avoid hedging language like "it's too early to tell" without a clear date for when you will tell.

---

#### 4. Qualitative Feedback Synthesis

Synthesize signal from all available feedback sources. Organize by theme, not source.

**Themes from customers / users:**
- **[Theme 1]:** [Summary of what you heard, approximate frequency, representative quote if available]
- **[Theme 2]:** [Summary]
- **[Theme 3]:** [Summary]

**Themes from internal teams (CS, Sales, Support):**
- **[Theme 1]:** [What the team observed or reported]
- **[Theme 2]:** [Summary]

**What surprised us:**
- Things we didn't expect — positive or negative

**What validated our assumptions:**
- Where the pre-launch hypotheses proved correct

---

#### 5. Launch Process Retro

Evaluate the launch execution itself, separate from the feature outcomes. Use a structured Start/Stop/Continue format:

**Start doing:**
- [Things we should add to our launch process]

**Stop doing:**
- [Things that created friction, confusion, or risk]

**Continue doing:**
- [Things that worked well and should be preserved]

**Key process gaps identified:**
- CS enablement readiness
- Communication timing (internal vs. external)
- QA coverage
- Metric instrumentation completeness
- Rollout sequencing

Rate the overall launch process: 🟢 Smooth / 🟡 Mostly smooth with gaps / 🔴 Significant friction

---

#### 6. What We Learned

Distill the most important learnings into durable, reusable statements. These should be specific enough to change future behavior.

Format each learning as:
> **Learning:** [What we now know that we didn't before]  
> **Evidence:** [What told us this]  
> **Implication:** [What we'll do differently because of it]

Aim for 3-5 learnings. Avoid vague statements like "communicate earlier" — make them specific: "CS needs the talking points doc 5 business days before launch, not 2."

---

#### 7. v2 Backlog Inputs

Capture everything that emerged from this launch that should feed the next iteration. Categorize explicitly:

**Descoped from v1 (already planned):**
- [Item] — reason it was cut, priority for v2

**New requests from customers:**
- [Item] — frequency/source of the request

**Bugs or quality issues to address:**
- [Item] — severity, affected users

**Ideas surfaced during launch:**
- [Item] — brief rationale

**Not pursuing (and why):**
- [Item] — document what you're explicitly not doing to prevent it from resurfacing

---

#### 8. Recommendations & Next Steps

What should happen as a result of this retro?

| Action | Owner | Due Date |
|---|---|---|
| [Metric follow-up review at T+90] | PM | |
| [File v2 tickets for descoped items] | PM | |
| [Share customer feedback themes with Design] | PM | |
| [Update launch checklist with process learnings] | PM | |
| [Brief leadership on metric status] | PM | |

---

## Step 4: Facilitation Guide (for live retro sessions)

If the user is running this as a team meeting rather than a written document, provide a facilitation agenda:

**Post-Launch Retro Meeting (60 min)**

| Time | Activity | Facilitator |
|---|---|---|
| 0-5 min | Context setting — what we're reviewing and why | PM |
| 5-15 min | Walk through metric outcomes (no editorializing yet) | PM |
| 15-25 min | Qualitative feedback themes (CS/Support leads) | CS lead |
| 25-40 min | Start/Stop/Continue on the launch process (silent brainstorm → discuss) | PM |
| 40-50 min | What we learned — generate and cluster | All |
| 50-60 min | v2 inputs + next steps + owners | PM |

**Pre-reads to circulate 48 hours before:**
- Metrics summary (even if preliminary)
- Support ticket themes
- Any NPS verbatims tied to the feature

---

## Step 5: Quality Checklist

- [ ] Metric outcomes include baseline, target, AND actual (not just "improved")
- [ ] Scope delta is documented (what shipped vs. planned)
- [ ] Learnings are specific enough to change future behavior
- [ ] v2 backlog distinguishes between descoped items, new requests, and bugs
- [ ] Process retro is honest about gaps (not just celebrating what went well)
- [ ] Next steps have owners and dates

---

## Output Format

- Produce as a complete Markdown document, structured for Notion, Confluence, or Google Docs
- Default to the T+30 full retro format
- For T+7 check-ins, include only sections 1, 3, 4, and 8
- Flag sections where the user needs to fill in data (e.g., "[Insert metric actuals]")
- Offer to produce a 1-page executive summary version of the retro on request
