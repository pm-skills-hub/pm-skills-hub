# Customizing This Skill

## Quick Start

This skill works out of the box with sensible defaults for PRD review. However, you can customize it to match your team's specific processes, tooling, and organizational structure.

## What to Customize

### 1. Directory Structure

**What to look for:** References to `prd/` and `prd_reviews/` directories

**Why customize:** Your team may use a different directory structure or naming convention for storing PRDs and reviews.

**Example:**
- Generic: `prd/` directory
- Personalized: `docs/product-requirements/` or `product-specs/`

### 2. Review Personas

**What to look for:** The four default personas (Director of Product, Director of Engineering, Engineering Tech Lead, Lead Designer)

**Why customize:** Your organization may have different titles or additional reviewers (e.g., Head of Data, Security Lead, Customer Success Manager).

**Example:**
- Generic: "Director of Product"
- Personalized: "VP of Product" or "Product Lead"
- Add: "Data Architect" for data-heavy features

### 3. Severity Levels and Categories

**What to look for:** The severity levels (Critical/Major/Minor/Question/Praise) and feedback categories

**Why customize:** Your team may use different prioritization frameworks or labels.

**Example:**
- Generic: "Critical/Major/Minor"
- Personalized: "P0/P1/P2" or "Blocker/High/Medium/Low"

### 4. Review Criteria and Evaluation Points

**What to look for:** Specific checklist items under each persona (e.g., "Problem-First Thinking", "Acceptance Criteria")

**Why customize:** Add or remove evaluation criteria based on your team's definition of a good PRD.

**Example:**
- Add: "Legal/Compliance Review" section for regulated industries
- Add: "Customer Impact Assessment" for customer-facing features
- Remove: Sections that don't apply to your product domain

### 5. Output Template

**What to look for:** The markdown template structure in the "Output: Write Consolidated Review" section

**Why customize:** Match your team's existing documentation format or integrate with your issue tracker.

**Example:**
- Add: Links to Jira tickets or Linear issues
- Add: Sign-off section with reviewer names and dates
- Add: "Related PRDs" or "Dependencies" section

## Tips

1. **Keep a local copy:** Make your customizations in a separate file (e.g., `SKILL_CUSTOMIZATIONS.md`) so you can easily reapply them if the base skill is updated.

2. **Start small:** Begin by customizing just the directory paths and persona titles, then iterate based on team feedback.

3. **Document your changes:** Keep a changelog of what you've customized and why, so new team members understand your process.

4. **Review regularly:** As your team evolves, revisit your customizations quarterly to ensure they still match your needs.