---
name: prd
description: Generate a complete, structured Product Requirements Document (PRD) for any feature, product, or initiative. Use this skill whenever the user asks to write a PRD, product spec, requirements doc, feature spec, or product brief — even if they just say "write up the requirements for X" or "spec this out". Also trigger when the user says things like "I need to document what we're building" or "help me write the requirements." Produces a full PRD with problem framing, goals, user stories, requirements, success metrics, edge cases, and open questions.
---

# PRD Skill

## Purpose
Generate a complete, high-quality Product Requirements Document that gives engineering, design, and stakeholders a shared understanding of what to build, why, and how success is defined.

---

## Step 1: Gather Context

Before writing, identify the following. If the user hasn't provided them, ask (batch your questions):

- **What is the feature or initiative?** (name, one-line description)
- **Who are the target users?** (persona, segment, or role)
- **What problem does it solve?** (the pain point or opportunity)
- **What is the desired outcome?** (the metric or behavior change you're targeting)
- **Are there known constraints?** (technical, timeline, compliance, budget)
- **What integrations or dependencies exist?**
- **Is there existing context?** (prior research, related docs, stakeholder decisions already made)

If the user provides a rough brief or notes, extract as much of this as possible before asking clarifying questions.

---

## Step 2: PRD Structure

Produce the PRD using this structure. All sections are required unless explicitly excluded.

---

### `[Feature Name]` — Product Requirements Document

**Status:** Draft | In Review | Approved  
**Author:** [Name]  
**Last Updated:** [Date]  
**Target Release:** [Quarter or Sprint]

---

#### 1. Overview

Write 2-4 sentences that summarize what this document covers, for whom, and why it matters. This section should be readable by a non-technical stakeholder in under 60 seconds.

---

#### 2. Problem Statement

Answer:
- What problem are we solving?
- Who experiences this problem?
- What is the impact if we don't solve it? (quantify where possible)
- What evidence supports this problem existing? (research, data, customer quotes)

Format as a narrative paragraph. Do not use bullet points in this section.

---

#### 3. Goals & Non-Goals

**Goals** (what success looks like):
- Use specific, measurable statements where possible
- Distinguish between launch goals and longer-term goals if relevant

**Non-Goals** (what this does NOT include):
- Be explicit about scope boundaries to prevent scope creep
- Include things that are tempting but out of scope for this version

---

#### 4. User Stories

Format as: `As a [persona], I want to [action] so that [outcome].`

Group by persona if multiple user types are involved. Include:
- Primary happy-path stories (P0)
- Secondary/edge case stories (P1)
- Admin or internal user stories if applicable

---

#### 5. Functional Requirements

List what the system must do. Use the MoSCoW format:

- **Must Have (M):** Core functionality required for launch
- **Should Have (S):** Important but not launch-blocking
- **Could Have (C):** Nice-to-have, consider for v2
- **Won't Have (W):** Explicitly descoped

Write requirements in declarative form: "The system shall..." or "Users must be able to..."

---

#### 6. Non-Functional Requirements

Cover the following where relevant:
- **Performance:** Load time targets, throughput, latency
- **Security & Compliance:** Data handling, access controls, regulatory requirements
- **Accessibility:** WCAG standards, screen reader support
- **Scalability:** Expected load, growth assumptions
- **Availability & Reliability:** Uptime SLA, error rate tolerance

---

#### 7. UX / Design Considerations

- Describe the expected user flow at a high level (numbered steps)
- Note any design principles or constraints (brand, accessibility, platform consistency)
- Reference any existing design system components to leverage
- Link to Figma/mockups if available, or note that designs are pending

---

#### 8. Technical Considerations

Note known technical decisions, constraints, or risks. This is not an engineering spec — surface the signal, not the solution:
- Data model implications
- API changes or new endpoints needed
- Third-party dependencies
- Migration or backward-compatibility concerns
- Performance implications

---

#### 9. Success Metrics

Define how you will know this feature succeeded. Include:
- **Primary metric:** The single most important metric (tie to goal)
- **Secondary metrics:** Supporting indicators
- **Guardrail metrics:** Metrics that must not regress
- **Measurement timeline:** When will you evaluate? (7-day, 30-day, 90-day)

---

#### 10. Edge Cases & Error States

List scenarios the implementation must handle gracefully:
- Empty states (no data, new user)
- Error states (network failure, invalid input)
- Permission edge cases
- Concurrent user scenarios
- Degraded or offline states

---

#### 11. Open Questions

Track unresolved decisions here. For each question, note:
- The question
- Who owns the decision
- Target resolution date

| # | Question | Owner | Due |
|---|----------|-------|-----|
| 1 | | | |

---

#### 12. Out of Scope / Future Considerations

Document things explicitly deferred to a future version. This prevents revisiting scope debates.

---

#### 13. Appendix

Include any supporting materials:
- Links to user research or data
- Competitive analysis references
- Related RFCs or design docs
- Glossary of terms

---

## Step 3: Quality Checklist

Before finalizing, verify:
- [ ] Problem statement is grounded in evidence, not assumptions
- [ ] Every goal has a corresponding success metric
- [ ] Non-goals are explicit
- [ ] User stories cover at least one edge case or error scenario
- [ ] Open questions have owners and due dates
- [ ] Technical considerations have been flagged (not solved)

---

## Output Format

- Produce the PRD as a well-formatted Markdown document
- Use headers, tables, and bullet points for scannability
- Keep language precise and declarative
- Avoid passive voice in requirements ("Users can..." not "It should be possible for users to...")
- Target length: 800-1500 words for a standard feature PRD; adjust for scope
- If the user asks for a "lightweight" or "one-page" PRD, condense to sections 1, 2, 3, 4, 5, 9, and 11 only
