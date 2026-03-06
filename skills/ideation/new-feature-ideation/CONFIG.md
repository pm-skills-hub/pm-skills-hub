# Customizing This Skill

## Quick Start

This skill works out of the box for any codebase and tech stack. It's designed to be framework-agnostic and will adapt its analysis based on what it finds in your project.

However, you can tune it to work better for your specific team, product domain, and strategic priorities.

## What to Customize

### 1. Codebase Search Patterns

**What to look for:** Step 2 contains bash commands that search for models, routes, and integrations using common file patterns.

**Why customize:** Your project may use non-standard file naming, a custom directory structure, or a newer framework not yet covered by the default patterns.

**Example:**
- Generic: `find . -name "models.py"` (assumes Django/Flask convention)
- Customized: `find . -path "*/domain/*.entity.ts"` (if your team uses a domain-driven design structure with TypeScript entities)

### 2. Strategic Dimensions in Prioritization

**What to look for:** Step 5 defines a 5-dimension scoring rubric (User Impact, Differentiation, Buildability, Strategic Fit, Effort Efficiency).

**Why customize:** You may want to weight certain dimensions differently, add your own strategic lens (e.g., "Revenue Potential"), or remove dimensions that don't matter for your product stage.

**Example:**
- Generic: Uses equal 1-5 weighting across all dimensions
- Customized: Add a 6th dimension "Enterprise Readiness" weighted 1-10 if selling to large buyers, or replace "Strategic Fit" with "Time to Value" for a PLG product

### 3. Integration Focus Areas

**What to look for:** Phase 4 searches for specific third-party services (Stripe, Twilio, OpenAI, etc.).

**Why customize:** If your team uses niche or industry-specific integrations, add them to the grep pattern so the skill detects underutilized connections.

**Example:**
- Generic: Searches for `stripe|twilio|sendgrid|openai`
- Customized: Add `|salesforce|workday|epic|cerner` if building healthcare software, or `|plaid|unit|marqeta` for fintech

### 4. Idea Variety Targets

**What to look for:** Step 4 specifies variety targets like "at least 2 ideas that leverage an existing integration" or "at least 1 that opens a new market segment."

**Why customize:** Adjust these targets to match your current product priorities. If you're in a consolidation phase, reduce the "new market" requirement. If you're pivoting, increase it.

**Example:**
- Generic: "At least 1 idea that opens a new market segment"
- Customized: "At least 3 ideas that deepen existing user workflows" (if focused on retention over acquisition)

## Tips

- **Keep customizations in a comment block at the top of SKILL.md** so you can easily reapply them when updating to a new version of this skill.
- **Version your scoring rubric** if you change it — note the date and why you adjusted weights, so future PMs understand the context.
- **Share your customized search patterns with the team** — if you discover a better way to find models or routes in your codebase, document it for others.