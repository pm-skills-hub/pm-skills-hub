---
name: prd_rodeo
description: Comprehensive PRD review by multiple personas (Director of Product, Director of Engineering, Engineering Tech Lead, Lead Designer). Use when the user asks to "review my prd" or mentions reviewing a product requirements document. Can also be invoked for a single persona (e.g. "just have the tech lead review" or "designer review only").
---

# PRD Review - Multi-Persona PRD Review

Performs a comprehensive review of a Product Requirements Document (PRD) through four distinct personas, each providing feedback from their unique perspective. All findings are written to a single review file in the `prd_reviews/` directory.

**Important:** After completing all review rounds, you must **write the consolidated findings to `prd_reviews/{prd_name}_review.md`**. Do not only print the review in chat.

---

## Overview

This skill performs four sequential review rounds (or a single targeted round):

1. **Director of Product** - Business case, user stories, requirements clarity, phasing
2. **Director of Engineering** - Technical feasibility, overlap with existing functionality, assumptions
3. **Engineering Tech Lead** - Requirement details, implementation clarity, edge cases
4. **Lead Designer** - UX/UI quality, mockup/prototype feedback, interaction patterns, accessibility

Each persona reviews the **entire PRD** but focuses on their area of expertise. Stop the review and log the findings if any critical or major feedback is found.

**Codebase Reference:** The Director of Engineering and Engineering Tech Lead should actively reference the codebase (if available) to:

- Find existing functionality and patterns
- Review architectural guidelines in codebase
- Understand domain patterns in codebase
- Cite specific files, patterns, and examples in their feedback

---

## Step 0 - Setup

1. **Identify the PRD to review:**
   - The user should provide a PRD name/path from the `prd/` directory
   - If not provided, list available PRDs and ask the user to select one

2. **Read the PRD:**
   - Read the entire PRD document
   - Note its structure, sections, and overall organization

3. **Prepare output location:**
   - Ensure `prd_reviews/` directory exists (create if needed)
   - Prepare to write findings to `prd_reviews/{prd_name}_review.md`

4. **Determine review scope:**
   - Check whether the user requested a **specific persona** (e.g. "just the tech lead", "designer review only", "product review")
   - **Full review on a new file:** Run all four rounds in sequence and create `prd_reviews/{prd_name}_review.md` with the complete review.
   - **Full review on an existing partial file:** Read the file first. Check each persona section — if it contains `> _Review pending_`, run that round and replace the placeholder with the full review. Skip any section that already has content unless the user explicitly asks to re-review that persona. Update the Executive Summary after all new sections are filled in.
   - **Full review on an existing complete file:** All four sections are already populated. Re-run all rounds and overwrite the file only if the user explicitly confirms they want to redo the full review.
   - **Single-persona review:** Run only the requested round.
     - If the review file **already exists**: read it first, then update only that persona's section in place (replace the existing section or append it if not yet present). Also update the Executive Summary to reflect the new findings.
     - If the review file **does not exist**: create it with the requested persona's section fully populated and all other persona sections marked as `> _Review pending_`.
   - In all cases, the output file is always `prd_reviews/{prd_name}_review.md` — never a separate file.

---

## Round 1 - Director of Product Review

The Director of Product focuses on ensuring the PRD clearly articulates the business value, customer problem, and product requirements without over-specifying implementation. Key evaluation criteria:

- **Tactical and Strategic Balance**: Right blend of immediate execution details and long-term vision
- **Problem-First Thinking**: Clear understanding of the problem before jumping to solutions
- **Solution Alignment**: Proposed solution directly addresses the stated problem
- **Evidence-Based**: Claims supported by data, user research, or concrete examples
- **Explicit Tradeoffs**: Clear acknowledgment of what we're choosing and what we're not

### 1.1 Problem Understanding (Highest Priority)

- **Check** that the PRD **clearly defines the problem BEFORE presenting the solution**
- **Verify** problem statement comes early and is distinct from solution sections
- **Assess** whether the problem is:
  - Clearly defined and specific (not vague or assumed)
  - Customer-focused (describes user pain, not technical gaps)
  - Measurable or observable (can we see/measure the problem today?)
  - **Evidence-backed**: Supported by data, user research, support tickets, or concrete examples
- **Flag** if solution is presented before problem is established
- **Record findings:**
  - Critical: Problem is missing, vague, technology-focused, or solution jumps ahead of problem definition
  - Critical: Problem lacks evidence or supporting data
  - Suggestion: Problem could be sharper, more specific, or better evidenced
  - Praise: Problem is well-articulated with clear evidence

### 1.2 User Stories and Use Cases

- **Check** that user stories follow the format: "As a [user type], I want [goal] so that [benefit]"
- **Assess** whether use cases cover:
  - Primary happy path
  - Key alternative flows
  - Different user personas/roles
- **Look for** gaps in user journeys or missing personas
- **Record findings:**
  - Critical: Missing essential user stories or personas
  - Suggestion: Additional user stories that should be included

### 1.3 Business Case and Success Metrics

- **Verify** the PRD includes:
  - Why we're building this (business justification)
  - Success metrics or KPIs
  - Expected impact on users/business
  - **Evidence**: Data, research, or examples supporting the business case
- **Assess** whether success criteria are:
  - Measurable and specific
  - Achievable within the proposed scope
  - Aligned with the stated problem
- **Record findings:**
  - Critical: Missing success metrics, unclear business case, or unsupported claims
  - Suggestion: Sharpen metrics, add missing measurements, or strengthen evidence
  - Praise: Strong business case with compelling evidence

### 1.4 Tactical and Strategic Balance

- **Assess** whether the PRD strikes the **right blend of tactical and strategic** thinking:
  - **Tactical (Execution)**: Near-term implementation details, specific requirements, immediate user needs, clear acceptance criteria
  - **Strategic (Vision)**: Long-term direction, scalability considerations, how this fits into broader product roadmap, future extensibility
- **Check** for tactical/strategic balance:
  - Too tactical: Overly prescriptive, no future vision, misses the "why" and broader context
  - Too strategic: Vague hand-waving, lacks concrete requirements, not actionable
  - Well-balanced: Clear immediate requirements + context for future evolution
- **Assess** whether the PRD explains:
  - Why this approach positions us well for future needs
  - How this fits into the longer-term product vision
  - What doors this opens (or closes) for future capabilities
- **Record findings:**
  - Critical: Severely imbalanced (all tactics/no strategy or all vision/no details)
  - Suggestion: Add strategic context or concrete tactical details
  - Praise: Excellent balance of immediate execution and long-term thinking

### 1.5 Product vs Technical Scope

- **Ensure** the PRD focuses on **product requirements** (what, who, when, why)
- **Flag** sections that prescribe **technical implementation** (how: APIs, database schema, specific technologies)
- **Note** where technical details should be left to engineering
- **Record findings:**
  - Suggestion: Sections that over-specify implementation
  - Praise: Good separation of product and technical concerns

### 1.6 Requirements Completeness and Phasing

- **Check** that all requirements are documented:
  - Functional requirements (features, capabilities)
  - Non-functional requirements (performance, accessibility, security considerations at product level)
  - Dependencies on other features/systems
- **Assess** phasing strategy:
  - Is there a clear MVP or Phase 1?
  - Are phases logically sequenced?
  - Are dependencies between phases called out?
- **Record findings:**
  - Critical: Missing essential requirements or unclear phasing
  - Suggestion: Additional requirements or phase refinements

### 1.7 Consistency Across Sections

- **Check** that solution details are **consistent across all sections**
- **Flag** contradictions:
  - User roles/permissions mentioned differently in different sections
  - Scope described differently in overview vs requirements
  - Success metrics that don't align with stated problem
- **Record findings:**
  - Critical: Major contradictions that would cause confusion
  - Suggestion: Minor inconsistencies to clean up

### 1.8 Solution-Problem Alignment and Tradeoffs

- **Verify** the proposed solution **directly addresses the stated problem**
  - Does each major feature/capability map back to a specific aspect of the problem?
  - Are we solving the actual problem or a related but different problem?
  - Would solving this problem using this solution achieve the stated goals?
- **Check** that **tradeoffs are explicitly called out**:
  - What are we choosing NOT to do?
  - What alternatives were considered and why were they rejected?
  - What are the downsides or limitations of the chosen approach?
  - What are we prioritizing (speed vs completeness, simplicity vs flexibility, etc.)?
  - What future flexibility might we be constraining?
- **Consider** whether there are simpler approaches:
  - Smaller scope that still solves the core problem
  - Reuse of existing workflows/patterns
  - Iterative approach vs big-bang launch
- **Record findings:**
  - Critical: Solution doesn't clearly address the stated problem or missing tradeoff discussion
  - Suggestion: Strengthen solution-problem mapping or make tradeoffs more explicit
  - Question: Why was this approach chosen over alternatives?
  - Praise: Clear alignment between problem and solution with explicit tradeoffs

---

## Round 2 - Director of Engineering Review

The Director of Engineering focuses on technical feasibility, architectural alignment, and ensuring assumptions are validated before development begins.

### 2.1 High-Level Business Need Alignment

- **Assess** whether the proposed solution aligns with:
  - Current product architecture and patterns
  - Strategic technical direction
  - Existing technical capabilities
- **Consider** technical implications:
  - Are there architectural improvements embedded in this work?
  - Will the feature be disruptive to existing features?
  - Does the feature have an undue level of complexity that will make building and maintenance difficult?
  - What existing features do we have that already serve the need? Should we build on those instead of something new? Are we sure we cant use existing functionality?
- **Record findings:**
  - Critical: Misalignment with technical strategy
  - Question: Clarifications needed about strategic fit

### 2.2 Assumptions and Unknowns

- **Identify** technical assumptions in the PRD:
  - Data availability assumptions
  - Performance assumptions
  - Integration assumptions (third-party services, APIs)
  - User behavior assumptions
- **Flag** assumptions that need validation:
  - Can we actually get the data we need?
  - Will the outbound team be able to configure what you proposing to build easily and repeatably across clients?
  - Do the product requirements lend to the support team being able to support this new feature 24/7?
  - Do external dependencies support what we need?
  - What are acceptable service degradations for the new feature? What are critical degradations that must be responded to?
- **Call out** unknowns that must be resolved before development:
  - Technical spike needed?
  - Proof of concept required?
  - External vendor confirmation needed?
- **Record findings:**
  - Critical: Major assumptions that must be validated first
  - Question: Assumptions that need clarification or validation
  - Suggestion: Spikes or POCs to de-risk the work

### 2.3 Technical Feasibility and Risk

- **Assess** high-level technical risks:
  - Third-party integration reliability
  - Assess feature dependencies in both directions, what features feed this feature, and what downstream features will use outputs of this feature?
- **Consider** resource implications:
  - Estimated engineering effort (T-shirt size: S/M/L/XL)
  - Specialized skills required; does our team composition align with what we are trying to build
  - Timeline feasibility
- **Record findings:**
  - Critical: High-risk areas that need mitigation plans
  - Question: Feasibility concerns that need investigation

---

## Round 3 - Engineering Tech Lead Review

The Engineering Tech Lead focuses on ensuring requirements are clear, specific, and actionable enough for engineers to implement without ambiguity.

### 3.1 Requirement Clarity and Specificity

- **Review** each requirement for clarity:
  - Is it unambiguous? (Only one interpretation possible)
  - Is it specific? (Not vague like "fast", "intuitive", "simple")
  - Is it testable? (Can we verify when it's done?)
  - Is it complete? (All necessary details included)
- **Flag** vague or unclear requirements:
  - "The system should be fast" → How fast? What's the SLA?
  - "Users can filter data" → What fields? What operators? How is it displayed?
  - "Handle errors gracefully" → What errors? What's the user experience?
- **Record findings:**
  - Critical: Requirements too vague to implement
  - Suggestion: Ways to make requirements more specific
  - Question: Clarifications needed about requirement details

### 3.2 Edge Cases and Error Handling

- **Identify** missing edge cases:
  - Empty states (no data to display)
  - Error states (network failures, invalid data, conflicting configuration possibilities)
  - Boundary conditions (min/max values, date ranges)
  - Permission edge cases (what if user lacks permission mid-flow?)
  - Concurrent edit scenarios
- **Check** for error handling requirements:
  - What happens when external service is down? Is there a fallback set of behaviors for when a service is down/unavailable?
  - How do we handle invalid user input?
  - What's the user experience for errors?
- **Record findings:**
  - Critical: Missing essential edge cases
  - Suggestion: Additional edge cases to document

### 3.3 Acceptance Criteria

- **Verify** each requirement has clear acceptance criteria:
  - "When [condition], then [expected behavior]"
  - Specific enough to write tests against
  - Covers both happy path and error cases
- **Check** that acceptance criteria include:
  - Input conditions
  - Expected output/behavior
  - UI state changes
  - Data persistence expectations
  - Does this feature require an audit log
- **Record findings:**
  - Critical: Missing acceptance criteria for key requirements
  - Suggestion: Ways to strengthen acceptance criteria

### 3.4 Data Model and State Clarity

- **Review** how data is described:
  - Are state transitions documented (if applicable)?
  - Are data validation rules specified?
- **Check** for data-related gaps:
  - Where does the data come from?
  - How long is it cached/stored?
  - What happens to old data?
  - Are there data migration needs?
  - What is the upgrade path if altering an existing behavior?
- **Record findings:**
  - Critical: Unclear data model that would block implementation
  - Question: Data-related clarifications needed

### 3.5 User Interface and Interaction Details

- **Assess** UI requirement clarity:
  - Are interaction patterns specified (click, hover, drag, etc.)?
  - Are loading states defined?
  - Are responsive behavior requirements clear?
  - Are accessibility requirements included?
- **Check** for UI gaps:
  - What happens while data loads?
  - How are empty states displayed?
  - What's the mobile/tablet experience?
  - Are keyboard interactions defined?
- **Record findings:**
  - Suggestion: Missing UI/UX details
  - Question: UI behavior clarifications needed

### 3.6 Dependencies and Integration Points

- **Identify** all integration points:
  - Third-party services
  - Other features/modules in the app
  - External data sources
- **Check** that integration details are clear:
  - What data is sent/received?
  - What's the error handling for integration failures?
- **Record findings:**
  - Critical: Missing integration details needed for implementation
  - Question: Integration clarifications needed

### 3.7 Testing and Validation

- **Check** for testability:
  - Are there specific test scenarios called out?
  - How will we validate correctness?
- **Consider** test data needs:
  - Is the end to end flow of a new system level feature with all personas using it laid out clearly?
  - Are there specific scenarios to test?
  - Are there specific combinations of features/configuration that will prove challenging to implement this feature?
- **Record findings:**
  - Suggestion: Testing considerations
  - Question: How should we test scenario X?

---

## Round 4 - Lead Designer Review

The Lead Designer focuses on the user experience, visual design quality, interaction clarity, and whether the PRD gives design sufficient direction without over-constraining creative decisions. If mockups or prototypes are referenced or linked in the PRD, they should be evaluated directly.

- **UX-First Lens**: Does the PRD describe what users feel and experience, not just what they click?
- **Design Completeness**: Are enough constraints given that design can start without guessing?
- **Prototype Fidelity**: If mockups exist, do they accurately reflect the requirements?
- **Consistency**: Are design patterns, terminology, and interaction models consistent across the PRD?

### 4.1 User Experience and Flows

- **Assess** whether the PRD describes the user experience at a UX level:
  - Are user flows and journeys described from the user's perspective (not just system behavior)?
  - Are the entry and exit points of each flow clear?
  - Are transitions between states described (e.g. what happens after a user completes an action)?
- **Check** for experience gaps:
  - Are there moments in the flow where the user's next step is ambiguous?
  - Are success and failure states defined from the user's point of view?
  - Does the PRD account for first-time vs. returning user experiences?
- **Record findings:**
  - Critical: User flows are absent or so incomplete design cannot begin
  - Major: Key transitions or states are missing from the described flow
  - Suggestion: Ways to make the user journey more explicit
  - Praise: Clear, user-centered flow descriptions

### 4.2 Information Architecture

- **Review** how information and navigation are organized:
  - Is the hierarchy of content and features clear?
  - Does the proposed structure match how users would expect to find things?
  - Are labels, categories, and groupings consistent throughout the PRD?
- **Check** for IA issues:
  - Are there competing or overlapping navigation paths?
  - Does the PRD introduce new terminology without defining it?
  - Are progressive disclosure or drill-down patterns specified where appropriate?
- **Record findings:**
  - Critical: IA is contradictory or would require a major redesign to rationalize
  - Suggestion: Reorganize sections or clarify labeling and hierarchy
  - Question: IA decisions that need validation with user research

### 4.3 Mockup and Prototype Review

- **Check** whether the PRD references mockups, wireframes, or prototypes:
  - If yes: read or open each linked artifact and evaluate it against the requirements
  - If no: note that design artifacts are absent and flag if their absence is a blocker
- **Evaluate** any referenced design artifacts:
  - Do the mockups cover all the states described in the requirements (loading, empty, error, success)?
  - Are the mockups consistent with each other (same components, labels, spacing patterns)?
  - Do the mockups reflect the described user flows end-to-end, or only happy-path screens?
  - Are there screens in the mockup that have no corresponding requirement (or vice versa)?
- **Assess** prototype fidelity:
  - Is the fidelity appropriate for the stage of the project (lo-fi for early exploration, hi-fi for handoff)?
  - Does the prototype demonstrate critical interactions (e.g. form validation, modal flows, drag-and-drop)?
- **Record findings:**
  - Critical: Mockups contradict requirements, or are required but entirely missing
  - Major: Significant states or flows are unrepresented in mockups
  - Minor: Small inconsistencies between mockups and requirements
  - Question: Clarify intent of specific design decisions in the mockup
  - Praise: Mockups are thorough, consistent, and well-annotated

### 4.4 Interaction Patterns and States

- **Verify** that all meaningful UI states are defined:
  - Loading / skeleton states
  - Empty states (no data, first-time use)
  - Error states (field validation, system errors, permission errors)
  - Success / confirmation states
  - Disabled / read-only states
- **Assess** interaction pattern specificity:
  - Are hover, focus, active, and disabled styles mentioned where they matter?
  - Are animation or transition expectations called out (or explicitly left to design)?
  - Are complex interactions (drag, multi-select, inline edit) described clearly enough to design?
- **Record findings:**
  - Critical: A major interaction pattern is completely undefined, blocking design
  - Major: Several UI states are missing and would require assumptions
  - Suggestion: Add definitions for specific interaction patterns or states
  - Question: Clarify expected behavior for a specific interaction

### 4.5 Accessibility and Inclusive Design

- **Check** whether accessibility is addressed at the product level:
  - Are WCAG compliance expectations stated (e.g. AA)?
  - Are there requirements for keyboard navigation, screen reader support, or focus management?
  - Are color contrast or text size constraints mentioned?
- **Assess** inclusive design considerations:
  - Does the PRD account for users with varying technical proficiency?
  - Are there internationalization or localization requirements (date formats, RTL text, character limits)?
  - Are there mobile or touch interaction requirements?
- **Record findings:**
  - Critical: Feature is inaccessible by design (e.g. color-only indicators with no alternative)
  - Major: Accessibility requirements are absent when the feature clearly needs them
  - Suggestion: Add explicit a11y acceptance criteria or inclusive design notes
  - Praise: Accessibility is proactively addressed

### 4.6 Content and Copy Strategy

- **Review** the copy and content expectations in the PRD:
  - Are UI labels, button text, and headings specified or left entirely to engineering?
  - Is the tone and voice consistent with the rest of the product?
  - Are error messages and empty state copy described?
- **Flag** copy-related gaps:
  - Placeholder text like "Lorem ipsum" or "TBD" that must be resolved before design handoff
  - Labels that are ambiguous or inconsistent with existing product terminology
  - Missing guidance on character limits or truncation behavior
- **Record findings:**
  - Major: Critical copy is missing or contradicts established terminology
  - Suggestion: Define or refine copy for specific elements
  - Question: Confirm tone, label choices, or character limit expectations

### 4.7 Design-Development Handoff Readiness

- **Assess** whether the PRD gives design enough to produce handoff-ready specs:
  - Are component reuse expectations stated (use existing design system components vs. design new ones)?
  - Are responsive breakpoints or layout constraints mentioned?
  - Is the target platform(s) clear (web, mobile web, native app)?
- **Consider** handoff risks:
  - Are there any requirements that would require building net-new design system components?
  - Are there any platform constraints that would make the described design difficult to implement?
- **Record findings:**
  - Critical: Requirements would require significant net-new design work with no guidance
  - Suggestion: Clarify component reuse expectations or platform constraints
  - Praise: PRD is well-scoped for design to begin immediately

---

## Output: Write Consolidated Review

Write findings to **`prd_reviews/{prd_name}_review.md`**. Use clear sections, severity levels (Critical/Major/Minor/Question/Praise), and checkboxes for tracking.

- **Full review:** create or overwrite the file with all four persona sections populated.
- **Single-persona review on existing file:** read the file, replace only that persona's section (or append it if absent), and refresh the Executive Summary. Leave all other persona sections untouched.
- **Single-persona review on new file:** create the file with the reviewed persona's section fully populated. For each unreviewed persona section, insert a single line: `> _Review pending._`

**Template:**

```markdown
# PRD Review: {PRD Title}

| Property    | Value                                                                              |
| ----------- | ---------------------------------------------------------------------------------- |
| PRD Source  | `{path/to/prd.md}`                                                                 |
| Review Date | {YYYY-MM-DD}                                                                       |
| Reviewers   | {Comma-separated list of personas who have reviewed, e.g. "Engineering Tech Lead"} |

---

## Executive Summary

[2-3 sentence summary of overall PRD quality and key takeaways]

**Overall Assessment:** [Ready for implementation / Needs minor clarifications / Needs significant work]

**Key Blockers:** [Number] critical items must be resolved before development
**Major Items:** [Number] items should be addressed
**Questions:** [Number] clarifications needed

---

## 🎯 Director of Product Review

### 🚫 Critical Issues

- [ ] **[Customer Problem]** {description of issue}. **Fix:** {specific recommendation}
- [ ] **[Section Name]** {description of issue}. **Fix:** {specific recommendation}

### ⚠️ Major Suggestions

- [ ] **[Section Name]** {description}. **Recommendation:** {specific recommendation}

### 💡 Minor Suggestions

- [ ] **[Section Name]** {description}. **Recommendation:** {specific recommendation}

### ❓ Questions

- [ ] **[Section Name]** {question that needs clarification}

### 👍 Highlights

- **[Section Name]** {what was done well}

---

## 🏗️ Director of Engineering Review

### 🚫 Critical Issues

- [ ] **[Overlap/Assumptions/Risk]** {description of issue}. **Action:** {what needs to happen before development}

### ⚠️ Major Suggestions

- [ ] **[Architectural/Integration]** {description}. **Recommendation:** {specific recommendation}

### 💡 Minor Suggestions

- [ ] **[Pattern Alignment]** {description}. **Recommendation:** {specific recommendation}

### ❓ Questions

- [ ] **[Assumptions/Feasibility]** {question that needs validation or clarification}

### 👍 Highlights

- **[Pattern/Architecture]** {what was done well}

---

## 🔧 Engineering Tech Lead Review

### 🚫 Critical Issues

- [ ] **[Requirement: {name}]** Too vague to implement. **Details needed:** {specific questions}

### ⚠️ Major Suggestions

- [ ] **[Requirement: {name}]** {description}. **Recommendation:** {how to make more specific}
- [ ] **[Edge Case]** Missing scenario: {description}. **Add:** {what should be documented}

### 💡 Minor Suggestions

- [ ] **[Acceptance Criteria]** {description}. **Recommendation:** {improvement}
- [ ] **[Testing]** Consider adding {test scenario}

### ❓ Questions

- [ ] **[Requirement: {name}]** {implementation clarification needed}
- [ ] **[Integration]** {integration detail that needs specification}

### 👍 Highlights

- **[Requirement/Section]** {what was done well}

---

## 🎨 Lead Designer Review

### 🚫 Critical Issues

- [ ] **[UX Flow/Mockup/Accessibility]** {description of issue}. **Fix:** {specific recommendation}

### ⚠️ Major Suggestions

- [ ] **[Section/State/Pattern]** {description}. **Recommendation:** {specific recommendation}

### 💡 Minor Suggestions

- [ ] **[Copy/Interaction/IA]** {description}. **Recommendation:** {specific recommendation}

### ❓ Questions

- [ ] **[Section/Mockup]** {design decision or intent that needs clarification}

### 👍 Highlights

- **[Section/Mockup]** {what was done well from a design perspective}

---

## Next Steps

1. **Immediate Actions** (must resolve before development):
   - {List critical blockers from all personas that have reviewed}

2. **Before Kickoff** (should resolve):
   - {List major items that would help implementation}

3. **During Implementation** (can be refined):
   - {List minor items that can be addressed as we go}

---

## Additional Resources

- Related features: [List existing features to reference]
```

### Severity Guidelines

- **🚫 Critical**: Must be fixed before development starts (missing problem statement, major contradictions, unvalidated assumptions, requirements too vague to implement)
- **⚠️ Major**: Should be addressed to ensure smooth implementation (missing use cases, unclear phasing, architectural questions, important edge cases)
- **💡 Minor**: Nice to have, improves quality (additional details, minor inconsistencies, testing suggestions)
- **❓ Question**: Needs clarification from PRD author or stakeholders
- **👍 Praise**: Highlight good practices to reinforce

---

## Tips for Effective Review

1. **Read the entire PRD first** before starting persona reviews to understand full context
2. **Be specific in feedback** - always include the section/requirement name and specific recommendation
3. **Be constructive** - focus on improving the PRD, not criticizing the author
4. **Consider the audience** - engineers need different details than product managers
5. **Look for patterns** - if one requirement is vague, others probably are too
6. **Cross-reference codebase** - understand what exists before suggesting new work
7. **Think about the developer experience** - will an engineer have what they need to start coding?

---

## Process Checklist

- [ ] Step 0: Setup - PRD identified, read, and review scope determined (full or single persona)
- [ ] Round 1: Director of Product review completed _(skip if not in scope)_
- [ ] Round 2: Director of Engineering review completed _(skip if not in scope)_
- [ ] Round 3: Engineering Tech Lead review completed _(skip if not in scope)_
- [ ] Round 4: Lead Designer review completed _(skip if not in scope)_
- [ ] Output written to `prd_reviews/{prd_name}_review.md` (created or updated as appropriate)
- [ ] Summary provided to user with key takeaways and count of critical/major items