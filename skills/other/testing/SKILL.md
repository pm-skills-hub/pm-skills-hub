---
name: feature-ticket-writer
description: Generate well-structured feature tickets, user stories, and tasks for your project management tool (your issue tracking tool, etc.). Use this skill whenever the user asks to write a ticket, user story, feature card, Linear issue, Jira story, or task. Also trigger when someone says "write this up as a ticket," "turn this into a story," "break this into tickets," "help me write acceptance criteria," or "I need to spec out this feature for the dev team." Produces properly structured tickets with context, user story, acceptance criteria, edge cases, and sizing notes — small enough to be actionable, detailed enough to build from without a follow-up meeting.
---

# Feature Ticket Writer Skill

## Purpose
Produce clear, complete, build-ready feature tickets that give engineers and designers everything they need to execute without a follow-up Slack thread — and nothing they don't need.

---

## Step 1: Gather Context

Ask in a single batch if not provided:

- **What is the feature or change?** (brief description)
- **What problem does it solve for the user?** (the why)
- **Who is the user?** (persona or role)
- **What tool?** (your issue tracking tool — affects formatting conventions)
- **Ticket type?** (feature story, task, bug, spike/research — default to feature story)
- **Are there designs?** (link if available, or note that designs are pending)
- **Any known edge cases or constraints?** (technical, UX, permissions-related)
- **Does this need to be broken into sub-tasks?** (for larger features)

---

## Step 2: Ticket Size Guidance

Before writing, confirm the ticket is the right size. A good ticket is completable in 1-3 days by one person.

| Signal | Action |
|---|---|
| "Build the entire onboarding flow" | Break into multiple tickets first |
| "Add a tooltip to the setup step" | Single ticket, small |
| "Redesign the settings page" | Epic + child tickets |
| "Update copy on the confirmation screen" | Single task ticket |

If the feature is too large, offer to produce an **epic** + a set of **child tickets** instead.

---

## Step 3: Ticket Formats

### Format A: Feature Story (default)

Use for any user-facing change or new capability.

---

**[Ticket Title]**
`[Label: Feature]` `[Label: Area]` `[Priority: P0/P1/P2]`

---

**User Story**
> As a [persona], I want to [action], so that [outcome].

---

**Context**
2-4 sentences of background. Why does this ticket exist? What user problem or product goal does it serve? Link to your product spec, project document, or parent epic if relevant.

---

**Acceptance Criteria**
Written in Given/When/Then format. Each criterion should be independently verifiable.

- **Given** [precondition], **when** [action], **then** [expected result]
- **Given** [precondition], **when** [action], **then** [expected result]
- **Given** [precondition], **when** [action], **then** [expected result]

Include criteria for:
- The happy path (primary use case)
- At least one edge case or error state
- Any permission or role-based behavior
- Empty state (if UI is involved)

---

**Edge Cases & Error States**
- [Scenario]: [Expected behavior]
- [Scenario]: [Expected behavior]

---

**Design**
- [ ] Designs attached / linked: [Design file link or "pending"]
- [ ] Existing component to use: [Your design system reference if applicable]
- [ ] New component needed: [Yes / No]

---

**Out of Scope**
Explicitly state what this ticket does NOT include. Prevents scope creep mid-sprint.
- [Thing that is tempting but not part of this ticket]
- [Related work that belongs in a separate ticket]

---

**Dependencies**
- Blocked by: [Ticket # or "none"]
- Blocks: [Ticket # or "none"]
- Requires: [API, backend work, design, data, or other prerequisite]

---

**Sizing Notes**
- Estimated effort: [XS / S / M / L / XL] or [story points if team uses them]
- Complexity drivers: [What makes this harder or easier than it looks]

---

### Format B: Task (non-user-facing)

Use for engineering tasks, refactors, infra work, or internal tooling.

---

**[Task Title]**
`[Label: Task]` `[Label: Area]` `[Priority]`

---

**What & Why**
2-3 sentences. What needs to be done and why it matters now.

---

**Definition of Done**
A checklist of what "complete" means for this task:
- [ ] [Specific deliverable or behavior]
- [ ] [Test coverage requirement]
- [ ] [Documentation updated if applicable]
- [ ] [Reviewed / merged / deployed]

---

**Technical Notes**
Any context the engineer needs: relevant files, prior decisions, constraints, or references to architecture docs.

---

**Dependencies & Sizing**
- Blocked by / Blocks: [Ticket #]
- Estimated effort: [XS / S / M / L]

---

### Format C: Spike / Research Ticket

Use when the work is exploratory and the output is a decision or recommendation, not shipped code.

---

**[Spike Title]**
`[Label: Spike]` `[Time-box: X days]`

---

**Question to Answer**
> [The specific question this spike must answer — one sentence, falsifiable]

---

**Why This Matters Now**
What decision is blocked until this is answered? What is the cost of not knowing?

---

**Scope of Investigation**
What should be explored? What is explicitly out of scope for this spike?

---

**Definition of Done**
- [ ] Question answered with a clear recommendation
- [ ] Key tradeoffs documented
- [ ] Findings shared in [your team channel / doc / ticket comment] by [date]
- [ ] Follow-up tickets created if applicable

---

**Time-box**
This spike should not exceed [X days]. If more time is needed, escalate before the time-box expires.

---

### Format D: Epic

Use when a feature is too large for a single ticket. An epic groups related stories under a shared goal.

---

**[Epic Title]**
`[Label: Epic]`

---

**Goal**
One sentence: what outcome does completing this epic achieve?

---

**Background**
2-4 sentences of context. Link to your product spec or strategy doc.

---

**Success Criteria**
How will we know this epic is done and working? (Metric or observable outcome, not a task checklist)

---

**Child Tickets**
List the stories and tasks that make up this epic. Each should be independently shippable where possible:

- [ ] [Story 1 — title]
- [ ] [Story 2 — title]
- [ ] [Task 1 — title]
- [ ] [Spike — title if needed]

---

**Out of Scope**
What is explicitly not part of this epic?

---

## Step 4: Acceptance Criteria Patterns

Use these patterns when writing Given/When/Then criteria:

| Scenario type | Pattern |
|---|---|
| Happy path | Given [user is logged in and on X page], when [user does Y], then [Z happens] |
| Validation / error | Given [invalid input], when [user submits], then [specific error message is shown] |
| Empty state | Given [user has no data], when [user lands on X], then [empty state with CTA is shown] |
| Permission / role | Given [user is not an admin], when [user tries to access X], then [access is denied with message] |
| Loading state | Given [data is loading], when [user lands on X], then [skeleton/loader is shown] |
| Success state | Given [action completes], when [system responds], then [confirmation is shown and [downstream effect]] |

---

## Step 5: Ticket Title Conventions

Titles should be scannable in a backlog. Use the format:

> **[Verb] + [object] + [context if needed]**

| ✅ Good titles | ❌ Bad titles |
|---|---|
| "Add empty state to the reports list" | "Reports page" |
| "Show validation error on invalid email input" | "Fix email field" |
| "Enable CSV export for admin users" | "Export feature" |
| "Spike: evaluate pagination approaches for activity feed" | "Research pagination" |

---

## Step 6: Breaking Features into Tickets

If the user describes a large feature, offer to decompose it into a set of tickets. Use this sequencing logic:

1. **Data / API layer first** — backend tickets that unblock frontend
2. **Core happy path** — the minimum UI and logic to make the feature work
3. **Error and edge case handling** — validation, empty states, error messages
4. **Polish and refinement** — loading states, animations, copy, accessibility
5. **Analytics instrumentation** — event tracking for key actions

Produce each ticket in the Feature Story format and number them in recommended build order.

---

## Output Format

- Default to Format A (Feature Story) unless ticket type is specified
- Produce multiple tickets if the feature is too large for one
- Use clean Markdown formatted for copy-paste into your issue tracker
- Flag any acceptance criteria that require design decisions not yet made
- Keep language direct and specific -- engineers should never have to guess what "done" means
