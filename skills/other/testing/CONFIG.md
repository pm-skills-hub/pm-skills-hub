# Customizing This Skill

## Quick Start

This skill works out of the box for any PM using issue tracking tools. However, personalizing it to match your team's conventions will make tickets feel native to your workflow and reduce friction during handoff.

## What to Customize

### 1. Issue Tracker Tool References

**What to look for:** Generic mentions of "your issue tracker" or "your project management tool"

**Why customize:** Your team uses a specific tool with its own conventions (labels, formatting, workflows). Hardcoding your tool name makes the skill feel tailored to your stack.

**Example:**
- Generic: "What tool? (your issue tracker — affects formatting conventions)"
- Personalized: "What tool? (Jira — affects formatting conventions)"

### 2. Document and Spec Links

**What to look for:** References to "your product spec" or "project document"

**Why customize:** Your team has standard document types (PRDs, Tech Specs, RFCs, Design Docs). Using your actual terminology makes tickets link correctly to your knowledge base.

**Example:**
- Generic: "Link to your product spec, project document, or parent epic"
- Personalized: "Link to the PRD, RFC, or parent epic in Notion"

### 3. Design Tool References

**What to look for:** "Design file link" in the Design section

**Why customize:** Replace with your actual design tool (Figma, Sketch, Adobe XD) so engineers know where to find mocks.

**Example:**
- Generic: "Designs attached / linked: [Design file link or 'pending']"
- Personalized: "Designs attached / linked: [Figma link or 'pending']"

### 4. Communication Channels

**What to look for:** "Your team channel" in spike findings sharing

**Why customize:** Specify where findings should be posted so there's no ambiguity.

**Example:**
- Generic: "Findings shared in [your team channel / doc / ticket comment]"
- Personalized: "Findings shared in [#product-eng / Confluence / ticket comment]"

### 5. Design System References

**What to look for:** "Your design system reference"

**Why customize:** Link to your actual component library or design system (Material-UI, your internal DS, Storybook URL).

**Example:**
- Generic: "Existing component to use: [Your design system reference]"
- Personalized: "Existing component to use: [Acme Design System / Storybook]"

## Tips

1. **Keep tool-specific customizations in a single section:** If your team switches from Jira to Linear later, you'll know exactly where to update references.

2. **Version control your customized skill:** Store your personalized SKILL.md in your team's wiki or repo so new PMs get the right conventions automatically.

3. **Update labels and priority schemes:** The skill uses generic P0/P1/P2 labels — align these with your team's actual priority levels (Critical/High/Medium or SEV levels).