---
name: competitive-analysis
description: Generate a structured competitive analysis, competitor teardown, or competitive landscape document. Use this skill whenever the user asks to write a competitive analysis, comp analysis, competitor comparison, market landscape, or competitive matrix. Also trigger when someone says "how do we stack up against competitors," "help me analyze our competition," "I need a battlecard," "who are the players in this space," "help me understand the competitive landscape," or "compare us to [competitor]." Produces a full competitive analysis with market map, feature matrix, positioning teardown, strategic implications, and recommended responses — written at the altitude of a PM presenting to product and sales leadership.
---

# Competitive Analysis Skill

## Purpose
Produce a rigorous, strategically useful competitive analysis that goes beyond feature comparison to surface positioning, moats, vulnerabilities, and actionable implications for product strategy and go-to-market — not just a spreadsheet of checkboxes.

---

## Background: What a Good Comp Analysis Does

Most competitive analyses fail because they answer the wrong question. A feature checklist tells you what competitors have built. A good competitive analysis tells you why they built it, who they're targeting, and where the strategic openings are.

**The three questions a competitive analysis must answer:**
1. **Who are we really competing with?** (the answer is often not who you think)
2. **What is each competitor's theory of winning?** (their bet on how the market will unfold)
3. **Where is the exploitable whitespace?** (what no one is doing well for a specific segment)

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What is the product or feature area being analyzed?**
- **Who are the known competitors?** (list them; Claude will also suggest additions)
- **What is the intended use of this analysis?** (product strategy, sales battlecard, exec briefing, pricing decision, roadmap input)
- **Who is the target customer segment for this analysis?** (the comp landscape looks different for SMB vs. enterprise, or for a specific vertical)
- **What dimensions matter most?** (features, pricing, positioning, GTM, integrations, AI capabilities, etc.)
- **How deep should this go?** (quick landscape scan vs. deep teardown on 1-2 competitors)
- **What do you already know or believe?** (existing hypotheses to pressure-test)
- **Is a sales battlecard format needed?** (changes the output structure significantly)

---

## Step 2: Competitor Taxonomy

Before building the matrix, categorize competitors correctly. Not all competition is created equal.

### Four Types of Competitors

**Direct competitors:** Same customer, same job, similar solution. These are the ones sales deals are lost to.

**Indirect competitors:** Same job, different solution type. Often the incumbent the customer is replacing (spreadsheet, manual process, legacy tool, internal build).

**Adjacent competitors:** Different primary job, but overlapping use cases or buyer. Risk of platform expansion into your space.

**Emerging competitors:** Early-stage or recently funded players. Not a current threat but worth monitoring — they reveal where the market thinks value is moving.

Build the matrix with all four types represented, but depth-weight it toward direct and indirect.

---

## Step 3: Competitive Analysis Structure

---

### Competitive Analysis — [Product Area / Feature]

**Author:** [Name]  
**Date:** [Date]  
**Scope:** [Customer segment and use case being analyzed]  
**Competitors covered:** [List]

---

#### 1. Market Map

Before the matrix, orient the reader with a market map that shows how competitors are positioned relative to each other on two dimensions. Choose dimensions that reveal strategic differentiation -- not obvious ones like "price" vs. "features."

**Good dimension pairs:**
- Breadth of platform vs. depth of specialization
- Self-serve / SMB-focused vs. sales-led / enterprise-focused
- Point solution vs. workflow platform
- AI-native vs. AI-augmented vs. traditional
- Open / extensible vs. closed / opinionated

**Market map format (text-based):**

```
                    ENTERPRISE-FOCUSED
                           │
    Deep/Specialized ──────┼────── Broad/Platform
                           │
                    SMB-FOCUSED

  [Competitor A] ········ upper-left
  [Competitor B] ········ upper-right
  [Us]           ········ [position]
  [Competitor C] ········ lower-right
```

Label where you sit and where the whitespace is.

---

#### 2. Competitor Profiles

For each direct and indirect competitor, produce a profile. Depth scales with how often you compete with them.

---

**[Competitor Name]**

| Field | Details |
|---|---|
| Founded / Stage | [Year] / [Series X, Public, Bootstrapped] |
| Estimated ARR | [Range or public figure if available] |
| Primary customer | [Segment, size, vertical] |
| Core use case | [The job they're primarily hired to do] |
| Pricing model | [Per seat / usage / platform fee / freemium] |
| GTM motion | [Self-serve / sales-led / PLG / channel] |
| Key investors | [Notable backers if relevant] |

**Their theory of winning:**
> [1-2 sentences on what they believe about the market and how they're positioning to win it. This is the most important thing to get right — it reveals their strategic logic, not just their features.]

**What they're great at:**
- [Specific strength 1 — be concrete, not generic]
- [Specific strength 2]
- [Specific strength 3]

**Where they're weak:**
- [Specific gap 1 — grounded in evidence: customer reviews, lost deal feedback, product gaps]
- [Specific gap 2]

**Recent moves:**
- [Latest product launches, pricing changes, acquisitions, funding, or GTM pivots — with dates]

**Moat assessment:**
- [What makes them hard to displace once adopted? Data network effects, switching costs, integrations, brand, regulatory, etc.]

**Who they beat us with and why:**
- [Honest assessment of the deal types and segments where they win]

---

*(Repeat for each competitor)*

---

#### 3. Feature Comparison Matrix

Keep this focused on the dimensions that matter for the target segment. A 40-column matrix with mostly checkmarks tells you nothing strategically useful.

**Rules for the matrix:**
- Max 15-20 dimensions
- Use nuanced ratings, not binary yes/no: ✅ Strong / ⚡ Partial / ❌ Missing / 🔄 In progress
- Group dimensions by category (Core, Advanced, Platform, Integrations, AI/ML, Security/Compliance)
- Add a "Why it matters" column for the top 5-6 dimensions

| Capability | Us | Competitor A | Competitor B | Competitor C | Why it matters |
|---|---|---|---|---|---|
| **Core** | | | | | |
| [Dimension 1] | ✅ | ✅ | ⚡ | ❌ | [Customer impact] |
| [Dimension 2] | ⚡ | ✅ | ✅ | ✅ | [Customer impact] |
| **Advanced** | | | | | |
| [Dimension 3] | ✅ | ❌ | ⚡ | ❌ | [Customer impact] |
| **Platform & Integrations** | | | | | |
| [Dimension 4] | ✅ | ✅ | ❌ | ⚡ | [Customer impact] |
| **AI / ML** | | | | | |
| [Dimension 5] | ⚡ | ✅ | ❌ | ❌ | [Customer impact] |
| **Security & Compliance** | | | | | |
| [Dimension 6] | ✅ | ✅ | ⚡ | ❌ | [Customer impact] |

**Legend:** ✅ Strong / ⚡ Partial or limited / ❌ Not available / 🔄 On roadmap (claimed)

---

#### 4. Positioning Teardown

For each competitor, analyze how they position themselves — not what they claim, but what they're actually communicating to the market.

| Competitor | Target persona | Core claim | Proof points used | Emotional hook | What they avoid saying |
|---|---|---|---|---|---|
| [Comp A] | | | | | |
| [Comp B] | | | | | |
| Us | | | | | |

**Positioning whitespace:**
- What positioning territory is no one occupying?
- What customer pain point is being underserved in the messaging landscape?
- Where is there over-crowding? (where everyone says the same thing)

---

#### 5. Pricing & Packaging Comparison

| Competitor | Model | Entry price | Mid-tier | Enterprise | Free tier | Key packaging differentiator |
|---|---|---|---|---|---|---|
| [Comp A] | | | | | | |
| [Comp B] | | | | | | |
| Us | | | | | | |

**Pricing observations:**
- Who is competing on price and why?
- Who is anchoring on value and what proof points do they use?
- Where are we over- or under-priced relative to perceived value?
- What packaging decisions are creating switching friction for customers?

---

#### 6. Win / Loss Patterns

Synthesize patterns from deal data, sales feedback, or customer interviews:

**Where we consistently win:**
- [Segment / deal type / use case] — [reason we win here]
- [Segment / deal type / use case] — [reason]

**Where we consistently lose:**
- [Segment / deal type / use case] — [which competitor and why they win]
- [Segment / deal type / use case] — [which competitor and why]

**The deals we should stop chasing:**
- [Customer profile that selects for competitor strengths and against ours — not our ICP]

---

#### 7. Competitive Moat Assessment

For our own product, honestly assess the durability of our competitive position:

| Moat type | Strength (1-5) | Evidence | Trend |
|---|---|---|---|
| Switching costs | | | Strengthening / Stable / Eroding |
| Data / network effects | | | |
| Integration ecosystem | | | |
| Brand / trust | | | |
| Proprietary technology | | | |
| Regulatory / compliance | | | |
| Pricing / cost structure | | | |

**Honest verdict:** Where are we genuinely hard to displace? Where are we more substitutable than we'd like to admit?

---

#### 8. Strategic Implications

This is the section that makes the analysis actionable. Every insight should connect to a product, GTM, or positioning decision.

**Immediate implications (next quarter):**
- [Insight → Recommended action]
- [Insight → Recommended action]

**Medium-term implications (6-18 months):**
- [Competitive move we should anticipate and prepare for]
- [Market segment that is underserved and within reach]
- [Capability gap we need to close before it becomes a liability]

**Threats to monitor:**
- [Competitor move or market shift that would require us to update our strategy]
- [Emerging player or adjacent platform that could enter our space]

**Opportunities to act on:**
- [Where a competitor's weakness creates an opening we can exploit in positioning or product]

---

#### 9. Recommended Responses

Produce 3-5 specific, concrete recommended actions organized by function:

**Product:**
- [Specific recommendation with rationale]

**Positioning / Marketing:**
- [Specific recommendation with rationale]

**Sales:**
- [Specific recommendation with rationale — e.g., objection handling, segment targeting, proof points]

**Roadmap:**
- [Specific capability investment recommendation tied to competitive gap or opportunity]

---

## Step 4: Sales Battlecard Format

If the intended output is a sales battlecard (shorter, more tactical, designed for a sales rep to use in a deal), restructure as:

---

**[Competitor Name] — Battlecard**  
*For: Sales / CS | Updated: [Date]*

**When you're in a deal against them:**
> [1-sentence summary of their positioning and who they target]

**Why customers choose them:**
- [Honest top 3 reasons]

**Why customers choose us:**
- [Top 3 differentiators that matter in this deal type]

**Their weaknesses to probe:**
- [Questions to ask that surface their gaps: "How do you handle X?" "What happens when Y?"]

**Objection handling:**
| Their claim | Our response |
|---|---|
| "[Their common claim]" | "[Factual, confident rebuttal + proof point]" |
| "[Their common claim]" | "[Response]" |

**Landmines to plant:**
- [Questions that make the buyer think about gaps they haven't considered]

**Proof points to use:**
- [Customer quote, case study, or stat that directly counters their positioning]

**When to walk away:**
- [Deal profile where they're likely to win and we shouldn't over-invest in the pursuit]

---

## Step 5: Quality Checklist

- [ ] Competitors are categorized (direct / indirect / adjacent / emerging)
- [ ] Each competitor profile includes their theory of winning — not just their features
- [ ] Feature matrix uses nuanced ratings, not binary checkmarks
- [ ] Win/loss patterns are grounded in data or structured feedback, not assumptions
- [ ] Moat assessment is honest — including where we're substitutable
- [ ] Strategic implications connect to specific product or GTM decisions
- [ ] Battlecard (if produced) is short enough for a sales rep to use in a meeting

---

## Output Format

- Default to the full competitive analysis structure
- Produce the battlecard format if the user specifies sales use, deal support, or "battlecard"
- Offer both formats from the same input when the use case warrants it
- Flag any section where the user needs to supply deal data, customer feedback, or pricing intel
- Cross-reference with the product-strategy-doc skill: competitive whitespace should inform strategic bets
- Cross-reference with the exec-product-summary skill: the "Threats to monitor" section feeds directly into executive risk reporting
