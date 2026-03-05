# Customizing This Skill

## Quick Start

This architect review skill works out of the box for any project, but you'll get better results by aligning it with your team's documentation structure and terminology.

## What to Customize

### 1. Documentation Paths

**What to look for:** Generic references like "your project overview document", "your architecture documentation", "your feature checklists".

**Why customize:** The skill needs to know where your team keeps planning docs, checklists, and technical debt tracking.

**Example:**
- Before: "Read your project overview document"
- After: "Read `docs/README.md`" or "Read `docs/project-brief.md`"

### 2. Project Structure

**What to look for:** Generic references to "modules", "data models", "application logic", "routing configuration".

**Why customize:** Align the review targets with your actual codebase structure (Django apps vs. Next.js routes vs. microservices).

**Example:**
- Before: "Your data models"
- After: "Your Prisma schemas in `prisma/schema.prisma`" or "Your SQLAlchemy models in `src/models/`"

### 3. Technology Stack

**What to look for:** Generic terms like "view layer", "templates/components", "handlers/controllers".

**Why customize:** Swap in your framework's terminology so the review targets the right files.

**Example:**
- Before: "Your view layer — do templates/components exist"
- After: "Your React components — do `.tsx` files exist" or "Your Django templates — do `.html` files exist"

### 4. Review Output Locations

**What to look for:** References to "your project roadmap document", "your technical debt tracking document", "your post-MVP tracking document".

**Why customize:** Tell the skill exactly where to write its findings so they integrate with your existing workflow.

**Example:**
- Before: "Add it to your technical debt tracking document"
- After: "Add it to `docs/tech-debt.md`" or "Create a GitHub issue with label `tech-debt`"

## Tips

- **Keep path changes in the Step 1 and Step 3 sections** — this makes it easier to update the skill when you reorganize docs.
- **Use consistent naming** — if you call them "features" in one place and "modules" in another, pick one term and use it everywhere.
- **Test the skill on a small module first** — run it on one component to verify it's targeting the right files before running a full project review.