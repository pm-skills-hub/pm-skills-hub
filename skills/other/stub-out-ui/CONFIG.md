# Customizing This Skill

## Quick Start

This skill works out of the box for any web application that uses HTML templates. However, it becomes more effective when customized to match your project's specific documentation structure, template engine, and frontend stack.

## What to Customize

### 1. Documentation Paths

**What to look for:** Generic references like "Your architecture documentation", "Your getting started guide", "Your UI documentation"

**Why customize:** Pointing to your actual documentation files helps the skill understand your app's structure and requirements before stubbing.

**Example:**
- Generic: "Your architecture documentation — overall app structure and features"
- Customized: "`docs/architecture/overview.md` — overall app structure and features"

### 2. Base Template Reference

**What to look for:** "your base template file"

**Why customize:** Specifying your actual base template path ensures the skill reads the correct blocks and structure.

**Example:**
- Generic: "Read your base template file to understand what blocks are available"
- Customized: "Read `templates/base.html` to understand what blocks are available" (Django) or "Read `views/layouts/application.html.erb` to understand what blocks are available" (Rails)

### 3. Template Engine and Framework

**What to look for:** Generic references to "template syntax", "template engine", "framework docs"

**Why customize:** Specifying your actual stack (Django, Rails, React, etc.) helps generate more accurate TODO comments.

**Example:**
- Generic: "Reference specific template syntax... (e.g., Django template tags, Jinja macros)"
- Customized: "Reference specific Jinja2 template tags and macros"

### 4. CSS Framework

**What to look for:** "CSS framework classes" with examples like Tailwind

**Why customize:** If your team uses a different CSS approach (Bootstrap, custom classes, CSS modules), update the examples.

**Example:**
- Generic: "CSS framework classes... (e.g., Django template tags, Jinja macros, Tailwind classes)"
- Customized: "Bootstrap utility classes" or "our custom design system classes from `styles/components/`"

## Tips

- Keep your customizations in the "Before Stubbing" section to make it easy to update the skill when new versions are released
- If you add project-specific documentation paths, maintain a comment listing what each doc contains so future team members understand why they're referenced
- Consider creating a skill variant for each major app or template type if your project has very different patterns across different sections