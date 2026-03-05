# Customizing This Skill

## Quick Start

This skill works out of the box for backend stubbing, but personalizing it for your team's codebase structure and conventions will make it significantly more useful.

## What to Customize

### 1. Documentation Paths

**What to look for:** References to `devdocs/architecture.md`, `devdocs/appdocs/<app>.md`, and other documentation paths.

**Why customize:** These paths assume a specific documentation structure. Your team likely organizes docs differently.

**Example:**
- Generic: "Read your architecture documentation"
- Personalized: "Read `docs/system-design/architecture.md`" or "Read the Architecture section in your team wiki"

### 2. Code Organization Patterns

**What to look for:** References to `apps/<app>/` directory structure and file paths.

**Why customize:** Different codebases organize modules differently (apps/, services/, modules/, src/, etc.).

**Example:**
- Generic: "Your data model definitions"
- Personalized: "Read `src/models/<module>/schema.py`" or "Read `app/models/<module>.rb`"

### 3. Framework-Specific Patterns

**What to look for:** The skill uses Django as its primary example framework. Look for sections mentioning Django-specific concepts.

**Why customize:** If you use a different framework (Rails, FastAPI, Express), replace Django examples with equivalent patterns from your framework.

**Example:**
- Generic: "Reference specific framework patterns (e.g., Django patterns, Rails callbacks, FastAPI dependencies)"
- Personalized: "Reference FastAPI dependency injection patterns and Pydantic models" or "Reference Rails ActiveRecord callbacks and concerns"

### 4. Middleware Registration

**What to look for:** References to middleware configuration and authentication middleware.

**Why customize:** The specific configuration file and middleware names vary by framework.

**Example:**
- Generic: "Register in your middleware configuration after authentication middleware"
- Personalized: "Add to `MIDDLEWARE` in `settings.py` after `django.contrib.auth.middleware.AuthenticationMiddleware`"

### 5. Template Conventions

**What to look for:** References to template organization and rendering.

**Why customize:** Template directory structures vary widely between projects.

**Example:**
- Generic: "Using your project's template organization convention"
- Personalized: "Using the `templates/<app>/` convention" or "Using the `views/<module>/` convention for React components"

## Tips

- Keep your customizations in a commented section at the top of SKILL.md labeled "Team Conventions" so they're easy to find when the base skill updates.
- If your team uses multiple frameworks or languages, create separate variants of this skill (e.g., stub-backend-django, stub-backend-rails) rather than trying to maintain one universal version.
- Update the "File Type Skeletons" section to match your team's actual file types — remove types you don't use and add types that are common in your codebase.