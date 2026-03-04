# Customizing This Skill

## Quick Start

This skill works out of the box for reviewing code files, but you'll get better results by pointing it to your team's documentation and customizing the review checklist for your tech stack.

## What to Customize

### 1. Documentation Paths

**What to look for:** References to "your architecture documentation", "your getting started guide", "your feature documentation directory", and "your application documentation".

**Why customize:** The skill needs to know where your project's design docs, feature specs, and architecture decisions live to verify completeness.

**Example:**
- Generic: "Read your architecture documentation"
- Customized: "Read docs/architecture/system-design.md"

### 2. Framework-Specific Checklist

**What to look for:** The "Framework Best Practices" section (formerly Django-specific).

**Why customize:** Different tech stacks have different review concerns. Tailor this section to match your team's frameworks and standards.

**Example:**
- Generic: "For web frameworks (Django, Rails, etc.): Models/ORMs use appropriate field types..."
- Customized for React/Node: "React components use hooks appropriately; Express routes have proper middleware; API endpoints follow REST conventions"

### 3. Comment Syntax

If your codebase uses languages not covered in the "Comment Syntax by File Type" section, add them. For example:
- **TypeScript** (`.ts`, `.tsx`): `// TODO(review): message`
- **Go** (`.go`): `// TODO(review): message`

## Tips

- Keep your customizations in a clearly marked section of SKILL.md so you can easily reapply them if the skill template updates
- If your team uses a design doc template, reference its specific sections in the Completeness checklist
- Consider adding language-specific linting rules to the review checklist (e.g., "ESLint passes with no errors")