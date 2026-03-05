---
name: product-strategy-doc
description: Generate a complete, structured product strategy document that articulates vision, market context, strategic bets, and how the team will win. Use this skill whenever the user asks to write a product strategy, strategy doc, strategic plan, product vision doc, or product direction document. Also trigger when someone says "help me articulate our strategy," "I need to write up our product direction," "help me explain where we're taking the product," "write our product vision," or "I need to present our bets to leadership." Produces a full strategy doc with market framing, vision, strategic bets, investment logic, and what we're not doing — written at the altitude of a senior PM or GPM presenting to an executive audience.
---

# Product Strategy Doc Skill

## Purpose
Produce a rigorous, compelling product strategy document that gives the organization a shared understanding of where the product is going, why, and how it will get there — without devolving into a roadmap or a list of features.

---

## Background: What a Strategy Doc Is (and Isn't)

The most common failure mode is writing a strategy that is actually a roadmap in disguise. Before drafting, internalize this distinction:

| ❌ Not strategy | ✅ Strategy |
|---|---|
| "We will build X, Y, and Z" | "We will win by doing X better than anyone else in the market" |
| "Our roadmap for Q3 is..." | "Our theory of how the market will shift over 3 years is..." |
| "We're focused on growth" | "We will grow by expanding our footprint in mid-market accounts before moving upmarket" |
| "We'll improve the platform" | "Platform reliability is a prerequisite for our enterprise bet — we invest there first" |
| A list of initiatives | A set of choices about where to compete and how to win |

A strategy doc answers three questions:
1. **Where will we play?** (the market, segment, and use cases we're targeting)
2. **How will we win?** (the durable advantage we're building)
3. **What will we do — and not do?** (the choices that make the strategy real)

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What is the product or product area?** (scope of the strategy)
- **What is the time horizon?** (1 year, 3 years, 5 years — strategy should have a horizon)
- **Who is the audience?** (internal team, executive leadership, board, investors)
- **What is the current state of the product?** (early-stage, scaling, mature, turnaround)
- **Who is the customer?** (segment, persona, geography)
- **Who are the primary competitors?** (direct, indirect, and emerging)
- **What is the biggest open question about direction?** (what the strategy needs to resolve)
- **What strategic work already exists?** (prior strategy docs, OKRs, vision statements to build from)
- **What constraints shape the strategy?** (team size, platform dependencies, regulatory, market timing)
- **What does the business need from this product?** (revenue, retention, platform, expansion)

---

## Step 2: Strategy Doc Structure

---

### [Product Name] — Product Strategy

**Author:** [Name]  
**Date:** [Date]  
**Time Horizon:** [Year range, e.g., 2025-2027]  
**Status:** Draft / In Review / Approved  
**Audience:** [Team / Leadership / Board]

---

#### 1. Executive Summary

Write 3-5 sentences that a busy executive can read in 60 seconds and walk away with:
- The core strategic direction
- The primary market opportunity
- The one or two bets that define the strategy
- The expected outcome if successful

This is written last but appears first. Do not start with background or history. Start with the most important thing.

---

#### 2. Context & Market Framing

Set the strategic context before stating any direction. A strategy that isn't grounded in market reality isn't a strategy — it's a wish list.

**Market landscape:**
- Who are the customers, and what jobs are they trying to do?
- How is the market structured today? (fragmented, consolidated, platform-dependent, etc.)
- What are the macro trends reshaping this space? (regulatory, technological, behavioral)

**Competitive dynamics:**
- Who are the primary competitors and what is their theory of winning?
- Where are they strong? Where are they vulnerable?
- What would it take for a new entrant to disrupt this market?
- What is the competitive moat (if any) that exists today?

**Where the market is going:**
- What will be true in 3 years that is not true today?
- What customer behaviors or expectations are shifting?
- Where are the emerging whitespace opportunities?

*Length guidance: 300-500 words. This is context, not strategy — be disciplined about not editorializing here. State what is true, not what you want to be true.*

---

#### 3. Our Current Position

Be honest about where the product stands today. An accurate self-assessment is a prerequisite for good strategy.

**Strengths to build from:**
- What do we do better than anyone else?
- What do customers consistently tell us is the reason they chose us?
- What assets (data, network, integrations, relationships) do we have that competitors don't?

**Weaknesses to address or accept:**
- Where are we clearly behind the market?
- What do churned customers or lost deals tell us?
- What does our product architecture or team structure make difficult to change?

**What the data tells us:**
- Key engagement, retention, and growth metrics
- Where users get the most value (and least)
- What the usage patterns reveal about the actual job being done

*Be specific. Vague self-assessments produce vague strategies.*

---

#### 4. Vision

The vision is the aspirational end state — what the world looks like if the strategy succeeds over the full time horizon.

**Vision statement:**
> In [time horizon], [product] will be [what it is for whom] — [the change it creates in the world or for customers].

**What success looks like for customers:**
- A concrete, vivid description of what a customer's life or work looks like when the product has fully delivered on its promise
- Written in customer language, not product language

**What success looks like for the business:**
- The business outcome that results from product success
- Metrics or milestones that mark arrival at the vision

*A good vision is specific enough to be falsifiable and ambitious enough to be motivating. If everyone would agree with it, it's not a vision — it's a platitude.*

---

#### 5. Strategic Bets

This is the heart of the document. Strategic bets are the 2-4 choices that define how you will achieve the vision. Each bet is a directional commitment that allocates attention and resources.

For each bet:

---

**Bet [#]: [Name]**

**The bet:**
> [One sentence statement of the directional choice — what you are committing to doing or building or winning]

**Why we believe this:**
- The market signal, customer evidence, or competitive logic that makes this bet credible
- What would have to be true for this bet to pay off
- What evidence already supports this direction

**What this unlocks:**
- The downstream outcomes this bet enables (revenue, retention, expansion, platform, moat)
- Why this bet now (timing logic — why is this the right window?)

**What this requires:**
- The investment, capability, or organizational change needed to execute
- The sequencing dependency if this bet relies on another bet being true first

**Key risks:**
- What could make this bet wrong
- How we will know if we need to update this view

---

*Repeat for each bet. Aim for 2-4 bets. More than 4 usually means the strategy hasn't made hard choices.*

---

#### 6. Investment Logic

Translate bets into resource allocation logic. This section answers: given our bets, how should we think about where to invest?

**Investment priorities (ranked):**
1. [Highest priority area] — [Why it gets the most investment relative to alternatives]
2. [Second priority] — [Rationale]
3. [Third priority] — [Rationale]

**Investment rationale framework:**

| Area | Investment Level | Rationale |
|---|---|---|
| [Strategic bet area 1] | High — primary investment | Core to winning; differentiates |
| [Strategic bet area 2] | Medium — sustained investment | Enables bet 1; table stakes for segment |
| [Platform / infra] | High — foundational | Prerequisite for enterprise expansion |
| [Adjacent opportunity] | Low — monitor only | Not the time; revisit in [year] |
| [Area we're deprioritizing] | Minimal — maintenance mode | Below the line until [condition changes] |

---

#### 7. What We Are Not Doing

Strategy is as much about what you choose not to do as what you commit to. This section makes the tradeoffs explicit and prevents scope creep from eroding the strategy.

Explicitly state and briefly explain:
- **Market segments we are not targeting** (and why — not "we'll get to them later" but a real reason)
- **Use cases we are not solving for**
- **Product areas we are deprioritizing or putting in maintenance mode**
- **Capabilities we will not build** (and what we'll rely on instead — partners, integrations, ecosystem)
- **Competitive dynamics we will not try to win** (e.g., "we will not compete on price")

*This section is often the most valuable for alignment. If the team argues about the not-doing list, the strategy is doing its job.*

---

#### 8. Assumptions & Risks

Every strategy rests on assumptions. Surface them explicitly so the team knows when to update the strategy.

**Critical assumptions (if any of these prove false, the strategy needs to change):**

| Assumption | Evidence supporting it | How we'll know if it's wrong | Owner to monitor |
|---|---|---|---|
| [Market assumption] | | | |
| [Customer assumption] | | | |
| [Competitive assumption] | | | |
| [Technology/timing assumption] | | | |

**Strategic risks:**

| Risk | Likelihood | Impact | Mitigation or response |
|---|---|---|---|
| [Competitor makes a move that undercuts bet X] | | | |
| [Market shifts faster/slower than assumed] | | | |
| [Internal execution risk] | | | |

---

#### 9. How We'll Measure Strategic Progress

Strategy-level metrics are distinct from feature metrics or OKR key results. They tell you whether the strategy is working at the level of the bets — not whether individual initiatives shipped.

**Leading indicators** (signal the strategy is gaining traction, observable in 6-12 months):
- [Indicator 1] — [What it measures and target]
- [Indicator 2]

**Lagging indicators** (confirm the strategy succeeded, observable in 12-36 months):
- [Indicator 1] — [What it measures and target]
- [Indicator 2]

**Strategy review cadence:**
- Monthly: Leading indicator check
- Quarterly: Assumptions review — has anything changed that requires updating the strategy?
- Annually: Full strategy refresh

---

#### 10. Open Questions & Decisions Needed

Flag unresolved questions that could materially affect the strategy:

| Question | Why it matters | Who decides | Target date |
|---|---|---|---|
| [Strategic question 1] | | | |
| [Strategic question 2] | | | |

---

## Step 3: Tone & Altitude Guide

**Write at the altitude of someone who has deeply thought about the market, made hard choices, and can defend them.**

| Use | Avoid |
|---|---|
| "We will win in mid-market by..." | "We plan to focus on growth" |
| "This bet requires us to stop doing X" | "We'll continue to invest across all areas" |
| "The market will shift because..." | "Things are changing fast" |
| Specific competitor names and moves | "The competitive landscape is intense" |
| Named tradeoffs with rationale | "We'll balance all priorities" |
| Time-bound commitments | Open-ended aspirations |

**Voice:** Confident and clear. A strategy doc that hedges everything signals that no real choices were made. Own the bets.

---

## Step 4: Format Variants

| Format | When to use | Length |
|---|---|---|
| **Full strategy doc** | Annual planning, new product area, major pivot | 1,500-3,000 words |
| **Strategy one-pager** | Team alignment, leadership preview, quick framing | 400-600 words (sections 1, 4, 5, 7 only) |
| **Strategy narrative (essay style)** | Board presentation, investor update, culture-building | 800-1,200 words, flowing prose |
| **Strategy slide structure** | Leadership deck, all-hands, QBR | Outline with 1-sentence bullets per section |

Default to the full strategy doc unless the user specifies otherwise.

---

## Step 5: Quality Checklist

- [ ] The vision is specific enough to be falsifiable — someone could disagree with it
- [ ] Each bet is a choice, not a goal ("win in X segment" not "grow revenue")
- [ ] The not-doing list has real things the team would want to do — not just obvious exclusions
- [ ] Assumptions are explicit and have named owners to monitor
- [ ] Strategy-level metrics are distinct from feature or sprint metrics
- [ ] The document makes clear what is decided vs. what is still open
- [ ] A new team member could read this and know what to say yes and no to

---

## Output Format

- Default to the full strategy doc in clean, structured Markdown
- Use the one-pager format if the user says "lightweight," "quick," or "one page"
- Flag any section where the user needs to supply market data, competitive intelligence, or internal metrics
- Offer to produce a companion executive summary or slide outline on request
- After producing the doc, offer to cross-reference it against the OST skill to ensure the opportunity space aligns with the stated bets
