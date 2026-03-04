---
name: launch-plan
description: Generate a comprehensive product launch plan or go-to-market (GTM) brief for a feature, product, or initiative. Use this skill whenever the user asks to write a launch plan, GTM plan, go-to-market brief, launch checklist, or launch strategy. Also trigger when someone says "help me plan the launch," "what do we need to do to ship this," "write up our GTM," or "help me coordinate the release." Produces a structured launch plan covering audience, messaging, channels, stakeholder actions, timing, and success metrics.
---

# Launch Plan Skill

## Purpose
Produce a structured, actionable product launch plan that coordinates across PM, Marketing, Sales, CS, Engineering, and Leadership — covering everything from messaging to metrics to post-launch review.

---

## Step 1: Gather Context

Before writing, collect the following. Ask in a single batch if not provided:

- **What is launching?** (feature name, brief description)
- **Who is the target audience?** (customer segment, user persona, or market)
- **What is the launch type?** (see tier definitions below)
- **What is the target launch date or window?**
- **What channels do you use?** (email, in-app, blog, social, sales outreach, etc.)
- **Who are the key stakeholders?** (teams or individuals who need to act)
- **Is this a beta/early access launch or full GA?**
- **What is the headline value prop?** (one sentence: what does this do for customers?)
- **Are there any constraints?** (legal review needed, embargo, competitive sensitivity)
- **What does success look like?** (metrics, adoption targets, revenue)

---

## Step 2: Launch Tier Framework

Help the user identify the right scope of launch:

| Tier | What It Is | Typical Activities |
|---|---|---|
| **Tier 1 — Major Launch** | New product, platform, or flagship feature | Press, analyst briefings, sales enablement, full marketing campaign, executive involvement |
| **Tier 2 — Significant Feature** | High-impact feature for a key segment | Email campaign, in-app announcement, blog post, CS enablement, internal comms |
| **Tier 3 — Minor Feature / Improvement** | Quality of life improvement, smaller scope | Release notes, in-app tooltip, internal Slack announcement |
| **Tier 4 — Internal / Silent** | Bug fix, infra change, beta with no announcement | Internal release notes only |

If the user isn't sure, ask them to describe the feature's expected customer impact and help them select the right tier.

---

## Step 3: Launch Plan Structure

---

### [Feature/Product Name] — Launch Plan

**Launch Tier:** [1 / 2 / 3 / 4]  
**Target Launch Date:** [Date or Sprint]  
**PM Owner:** [Name]  
**Status:** Planning / In Progress / Launched

---

#### 1. Overview

Write 2-3 sentences describing:
- What is launching
- Why it matters to customers
- What the business outcome is

---

#### 2. Target Audience

Define who this launch is for:
- **Primary segment:** [Who is most affected or most likely to adopt]
- **Secondary segment:** [Adjacent users who may benefit]
- **Not the audience:** [Who this is not designed for — prevents messaging drift]

For B2B products, distinguish between:
- **Economic buyer** (who approves it)
- **End user** (who uses it)
- **Champion** (who advocates for it internally)

---

#### 3. Positioning & Messaging

**Headline (one sentence):**  
> [Product/Feature] helps [persona] [do X] so they can [achieve Y].

**Supporting messages (3 max):**
1. [Benefit statement 1]
2. [Benefit statement 2]
3. [Benefit statement 3]

**Proof points:**
- Data, customer quotes, beta results, or case study snippets that support the messaging

**Messaging don'ts:**
- What NOT to say (common mistakes, overpromises, out-of-scope claims)

---

#### 4. Launch Timeline

Map activities to a pre/launch/post structure:

**Pre-Launch (T-4 to T-1 weeks)**
| Task | Owner | Due Date | Status |
|---|---|---|---|
| Finalize messaging and copy | PM + Marketing | | |
| Complete QA and testing | Engineering | | |
| Legal / compliance review | Legal | | |
| Write release notes | PM | | |
| Create customer-facing docs | Docs / CS | | |
| Sales enablement deck and training | PM + Sales | | |
| Prepare CS talking points | PM + CS | | |
| Prepare in-app announcement copy | PM + Marketing | | |
| Set up feature flag / rollout config | Engineering | | |
| Internal announcement draft | PM | | |

**Launch Day (T-0)**
| Task | Owner | Time | Status |
|---|---|---|---|
| Enable feature flag / deploy | Engineering | | |
| Send customer-facing email | Marketing | | |
| Publish in-app announcement | PM | | |
| Post blog article (if applicable) | Marketing | | |
| Post internal Slack announcement | PM | | |
| Alert CS / Support team | PM | | |
| Monitor error rates and adoption | PM + Eng | | |

**Post-Launch (T+1 to T+30)**
| Task | Owner | Due Date | Status |
|---|---|---|---|
| Day 1 health check | PM + Eng | T+1 | |
| Week 1 adoption review | PM | T+7 | |
| Customer feedback collection | CS + PM | T+14 | |
| 30-day post-launch retro | PM | T+30 | |

---

#### 5. Channel Plan

For each channel, specify what content runs and who owns it:

| Channel | Content | Audience | Owner | Date |
|---|---|---|---|---|
| In-app notification | | End users | | |
| Email (customer) | | Target segment | | |
| Blog post | | Public / SEO | | |
| Social media | | Followers / prospects | | |
| Sales outreach | | Target accounts | | |
| Internal Slack | | Company | | |
| Help center / docs | | All users | | |
| Press / analyst (Tier 1 only) | | Media | | |

---

#### 6. Stakeholder Enablement

List what each team needs to be prepared:

**Sales**
- [ ] Battlecard or one-pager
- [ ] Demo script or talking points
- [ ] Objection handling notes
- [ ] CRM update / tagging guidance

**Customer Success / Support**
- [ ] Feature overview and benefit summary
- [ ] FAQ document
- [ ] Escalation path for bugs or complaints
- [ ] How to identify customers who should adopt this

**Marketing**
- [ ] Approved messaging and copy
- [ ] Assets (screenshots, video, illustrations)
- [ ] Campaign brief or calendar entry

**Engineering**
- [ ] Rollout plan and feature flag configuration
- [ ] Rollback procedure
- [ ] Monitoring / alerting setup

---

#### 7. Rollout Strategy

Define how the feature reaches users:

- **Rollout approach:** Full GA / Gradual rollout / Beta / Admin opt-in / Feature flag
- **Rollout sequence:** (e.g., internal → beta users → 10% → 50% → 100%)
- **Rollout owner:** Who controls the flag or release cadence?
- **Kill switch:** Under what conditions do we pause or roll back?

---

#### 8. Success Metrics

| Metric | Baseline | Target | Measurement Date | Owner |
|---|---|---|---|---|
| [Primary metric] | | | T+30 | |
| [Secondary metric] | | | T+14 | |
| [Guardrail metric] | | | T+7 | |

**Leading indicators** (early signals before metrics mature):
- Day 1 activation rate
- Support ticket volume
- In-app announcement click-through

---

#### 9. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Low adoption from target segment | Medium | High | CS outreach campaign |
| Bug discovered post-launch | Low | High | Rollback plan in place |
| Messaging misalignment with Sales | Medium | Medium | Enablement session T-1 week |

---

#### 10. Post-Launch Review Plan

Schedule a retro at T+30. Review:
- Did we hit our success metrics?
- What did customers say? (NPS, support tickets, CSM feedback)
- What would we do differently in the launch process?
- What's in the backlog for v2?

---

## Step 4: Launch Brief (Lightweight Version)

If a full plan isn't needed, produce a concise launch brief (1 page):

1. **What:** [Feature name and one-line description]
2. **Who:** [Target audience]
3. **Why it matters:** [Customer benefit + business outcome]
4. **When:** [Launch date]
5. **Key actions by team:** [3-5 bullets with owner and deadline]
6. **Success looks like:** [Primary metric and target]
7. **Risks:** [Top 1-2 risks and mitigations]

---

## Output Format

- Default to the full launch plan structure for Tier 1-2 launches
- Use the lightweight brief for Tier 3-4 launches or when user asks for a "one-pager"
- Produce as clean, copy-paste ready Markdown with tables for timelines and metrics
- Flag placeholder items clearly (e.g., "[Date TBD]", "[PM to confirm]")
- Offer to expand any section or produce specific sub-artifacts (enablement deck outline, email copy, internal Slack post) on request
