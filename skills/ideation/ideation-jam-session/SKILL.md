---
name: idea-jam-session
description: Run a live, back-and-forth creative brainstorming session to generate wild, unexpected, and differentiated product ideas. Use this skill whenever the user wants to ideate freely, explore out-of-the-box concepts, run a creative jam, or asks "what if we did something completely different." Also trigger when someone says "let's brainstorm," "give me some wild ideas," "what would this look like if we thought bigger," "I want to think outside the box," or "let's do a jam session on X." Pulls inspiration from adjacent and completely unrelated markets to cross-pollinate concepts. Designed for back-and-forth dialogue, not one-shot output — the agent actively builds on user reactions, challenges assumptions, and escalates ideas across multiple rounds.
---

# Idea Jam Session Skill

## Purpose
Run a generative, collaborative ideation session where Claude acts as a creative partner — not a template filler. This skill is conversational, iterative, and deliberately provocative. The goal is to get somewhere neither party would have reached alone.

---

## The Jam Session Mindset

This is not a feature prioritization exercise. It is not a PRD. It is not a roadmap planning session.

**The rules of a good jam:**
- No idea is too weird in the opening rounds
- Build on ideas before critiquing them
- "Yes, and..." before "but have you considered..."
- Cross-market inspiration is a feature, not a distraction
- The best idea in the session is often the third evolution of the first wild one
- Quantity of divergence first, convergence later

Claude's role is to be an **energetic, opinionated creative partner** — not a neutral assistant. Push back, escalate, combine, flip assumptions, and bring outside references aggressively.

---

## Step 1: Session Setup

Before the first idea drops, quickly establish:

**Ask in a single message (keep it light — this is a jam, not a requirements gathering session):**

> "Before we start riffing — give me a quick read on:
> 1. What's the product and its core loop?
> 2. Any area of the product you want to focus on, or totally open?
> 3. Any markets or industries you want to pull inspiration from — or should I go rogue?
> 4. Wildness dial: *Grounded* (adjacent, buildable soon), *Stretched* (ambitious, 12-18 months), or *Unhinged* (no constraints, pure imagination)?
>
> We can always adjust as we go."

If the user says "just go" or "surprise me" — default to Stretched, pick a focus area from context, and pull inspiration from 2-3 markets the user would not expect.

---

## Step 2: Cross-Market Inspiration Engine

Before generating ideas, load the mental model with cross-market patterns. The best product ideas come from mechanisms that already work brilliantly somewhere else.

**Markets to always consider pulling from (rotate across sessions):**

| Market | Transferable mechanic |
|---|---|
| Gaming | Progression systems, streaks, unlocks, leaderboards, multiplayer collaboration, world-building |
| Finance / Fintech | Real-time signals, risk scoring, portfolio views, automated rules, threshold alerts |
| Healthcare | Care pathways, triage logic, outcomes tracking, longitudinal records, second opinions |
| E-commerce | Recommendations, wishlists, social proof, scarcity signals, cart abandonment recovery |
| Creator economy | Monetization of expertise, audience building, remix culture, tipping, subscriber tiers |
| Logistics | Status tracking, route optimization, SLA monitoring, exception handling |
| Consumer social | Reactions, threads, presence indicators, stories/ephemeral content, following graphs |
| Sports analytics | Performance baselines, benchmarking, replay, pattern detection, scouting |
| Education / EdTech | Spaced repetition, mastery levels, cohort learning, certificates, peer review |
| News / Media | Briefings, digests, trending signals, editorial curation, reader-supported models |
| Marketplaces | Two-sided matching, reputation systems, escrow, supply/demand signals |
| B2B SaaS (adjacent) | Seat-based collaboration, workspace hierarchy, audit logs, SSO, admin controls |

**Cross-market technique — pick a mechanic, ask: "What if this product worked like [market]?"**

Examples:
- "What if your analytics product had a progression system like Duolingo?"
- "What if your project management tool had a fantasy sports draft mechanic for task assignment?"
- "What if your B2B SaaS had a creator monetization layer?"

Use at least 2 cross-market pulls per session. The more unexpected the pairing, the better.

---

## Step 3: The Jam Structure

Run the session in rounds. Each round has a different creative mode. Move through them based on energy and user engagement — don't rigidly announce each phase.

---

### Round 1 — Wild Opens (Divergence)

Generate 3-5 ideas rapidly. Each should be:
- **Named** (a short, evocative label — not a feature description)
- **One-line pitch** (what it does in plain language)
- **Cross-market origin** (what it's inspired by)
- **The gut reaction question** (a single question that invites the user to react)

**Format:**

---

🎯 **[Idea Name]**
> [One-line pitch]
*Inspired by: [market/product]*
*"[Reaction question to prompt the user]"*

---

Example:

🎯 **The War Room**
> A real-time shared view that activates automatically when a metric crosses a threshold — showing who's online, what's being worked on, and a live feed of actions taken, like an incident dashboard crossed with a trading floor.
*Inspired by: Bloomberg Terminal + incident.io*
*"Does your team currently scramble in Slack when something goes wrong, or do you have a war room equivalent already?"*

---

End Round 1 with: *"Which of these has a pulse? Or tell me what's not in here that should be."*

---

### Round 2 — Build and Escalate (Development)

Take 1-2 ideas the user reacted to. Now escalate each one in two directions:

**Dial it down** — what's the smallest, shippable version that captures the core insight?
**Dial it up** — what's the version that would make a competitor panic?

For each escalation, add:
- A specific user story (who does this for, in what moment?)
- The "why now" signal (why is this idea's time coming?)
- One constraint or risk worth naming honestly

This is where ideas stop being concepts and start becoming product thinking.

---

### Round 3 — Collision Round (Cross-Pollination)

Take one element from two different ideas and smash them together. The goal is to find a combination that neither idea achieves alone.

**Format:**
> "[Idea A element] + [Idea B element] = [New concept name]"
> [Why this combination creates something more interesting than either part]

This round often produces the most unexpected ideas and the ones that are hardest to categorize — which is a good sign.

---

### Round 4 — The Contrarian Flip (Challenge Assumptions)

Pick the product's most deeply held assumption and invert it. What would the product look like if the opposite were true?

**Flip prompts:**
- "What if users didn't have to set anything up — the product configured itself?"
- "What if the product was designed for one user to use once, perfectly, instead of many users repeatedly?"
- "What if you charged for the thing you currently give away free, and gave away the thing you charge for?"
- "What if the product was async-first instead of real-time?"
- "What if the AI did the work and the human just approved it — not the other way around?"
- "What if your biggest competitor's strength became your moat instead?"

Pick 1-2 flips relevant to the product. Explore them earnestly, not dismissively.

---

### Round 5 — The Shortlist (Convergence)

Near the end of the session, synthesize the strongest ideas that emerged across all rounds. Don't summarize everything — curate ruthlessly.

**For each shortlisted idea, capture:**

```
💡 [Idea Name]
In one sentence: [What it is]
Why it's interesting: [The insight or mechanic that makes it worth pursuing]
The version we'd actually build: [Smallest believable form]
The version that would be a bet: [The ambitious form]
Next step if we wanted to explore it: [Discovery interview? Prototype? Competitive scan? Spike?]
```

Aim for 2-4 ideas on the shortlist. Quality over completeness.

---

## Step 4: Session Facilitation Principles

**Keep the energy up:**
- Use short paragraphs and white space — walls of text kill creative sessions
- React to what the user says before introducing new ideas
- Match the user's energy level — if they're excited, escalate; if they're skeptical, probe
- Name ideas with evocative labels, not feature descriptions

**When the user shoots an idea down:**
- Don't abandon it immediately — ask what specifically isn't working
- Often the mechanism is right but the framing is wrong
- "What if we kept the X part but dropped the Y?"

**When the user gets excited:**
- Build on it immediately before introducing something new
- Ask: "What's the version of this that would make you nervous to pitch?"
- Push toward the ambitious form before the comfortable one

**When the session stalls:**
- Change the cross-market lens — bring in an industry that hasn't appeared yet
- Try a contrarian flip
- Ask: "What's the thing you'd never do but secretly think might work?"

**Phrases that unlock creative sessions:**
- "What if the constraint didn't exist?"
- "Who else has solved a version of this problem in a completely different context?"
- "What's the dumbest version of this idea? And what's the version that could go on a pitch deck?"
- "If you had to launch something in this space in 90 days, what would it be?"
- "What would make a new PM joining the team think 'I can't believe nobody built this yet'?"

---

## Step 5: Optional Output — Jam Session Summary

If the user wants to capture the session, produce a lightweight Markdown summary file.

**Save to:** `./jam-session-[product]-[date].md`

```markdown
# Idea Jam Session — [Product Name]
*Date: [Date] | Wildness dial: [setting] | Focus: [area or "open"]*

---

## Cross-Market Lenses Used
- [Market 1] — [mechanic borrowed]
- [Market 2] — [mechanic borrowed]

---

## Ideas That Surfaced

### [Idea Name]
> [One-line pitch]
**Inspired by:** [market]
**Smallest version:** [description]
**Ambitious version:** [description]
**Worth exploring if:** [condition — e.g., "interviews confirm users are doing this manually"]

[Repeat for each idea worth capturing]

---

## The Shortlist
1. **[Top idea]** — [one sentence on why this is the most interesting]
2. **[Second idea]** — [one sentence]
3. **[Third idea]** — [one sentence]

---

## Discarded But Interesting
Ideas that didn't make the shortlist but had a useful insight worth preserving:
- [Idea]: [The part worth keeping]

---

## Suggested Next Steps
- [ ] [Idea #1]: [Recommended next action — interview, prototype, spike, competitive scan]
- [ ] [Idea #2]: [Next action]
```

---

## Output Format

- This skill is **conversational first** — the primary output is the live dialogue, not a document
- Keep individual messages punchy and energetic -- shorter than standard PM skill outputs
- Produce the summary file only when the user asks to capture the session or winds it down
- Always end rounds with a question or prompt that invites the user to react, build, or redirect
- Cross-reference at session close: top ideas can flow into feature-ticket-writer, feature-ideation, or opportunity-solution-tree skills
