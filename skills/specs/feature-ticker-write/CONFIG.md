# Customizing This Skill

## Quick Start

This skill works out of the box for any PM using modern project management tools. However, personalizing it for your team's specific conventions will make tickets flow more smoothly into your existing workflow.

## What to Customize

### 1. Project Management Tool References

**What to look for:** Generic references to "your project management tool" and tool examples like "Jira, Linear, GitHub Issues"

**Why customize:** Your team likely standardizes on one tool with specific formatting conventions (custom fields, label formats, template structures)

**Example:**
- Before: "What tool? (your project management tool — Jira, Linear, GitHub Issues, etc.)"
- After: "What tool? (Linear — our team uses Linear for all feature work)"

### 2. Document and Process References

**What to look for:** Generic terms like "your product requirements document," "your product requirements or strategy document"

**Why customize:** Your organization has specific names for these artifacts (PRD, Product Spec, Feature Brief, RFC, etc.) and likely specific locations where they live

**Example:**
- Before: "Link to your product requirements document or parent epic if relevant"
- After: "Link to the PRD in Notion or parent epic in Linear if relevant"

### 3. Communication Channel References

**What to look for:** Generic references to "your team channel" or "conversation"

**Why customize:** Replace with your actual team communication tool and standard channels

**Example:**
- Before: "Findings shared in [your team channel / doc / ticket comment]"
- After: "Findings shared in [#product-engineering / Confluence / ticket comment]"

### 4. Design Tool References

**What to look for:** "Design file link" placeholder in the Design section

**Why customize:** Your team uses a specific design tool (Figma, Sketch, Adobe XD, etc.)

**Example:**
- Before: "Designs attached / linked: [Design file link or 'pending']"
- After: "Designs attached / linked: [Figma link or 'pending']"

### 5. Ticket Sizing Conventions

**What to look for:** The sizing options shown in "Sizing Notes" sections (XS/S/M/L/XL or story points)

**Why customize:** Teams use different sizing systems — t-shirt sizes, Fibonacci points, time estimates, or custom scales

**Example:**
- Before: "Estimated effort: [XS / S / M / L / XL] or [story points if team uses them]"
- After: "Estimated effort: [1 / 2 / 3 / 5 / 8 story points per team convention]"

## Tips

1. **Keep tool-specific customizations in one section:** Consider adding a "Team Conventions" section at the top of your customized SKILL.md that documents your specific tools, labels, and sizing scales. This makes it easy to update when practices change.

2. **Preserve generic examples:** When you customize tool names in questions and instructions, keep the generic examples in parentheses so the skill remains adaptable if your stack changes (e.g., "Link the PRD (usually in Notion or Confluence)").

3. **Version your customizations:** If you sync this skill across team members, note which sections you've customized in a comment at the top so others know what to keep vs. what might get overwritten in future skill updates.