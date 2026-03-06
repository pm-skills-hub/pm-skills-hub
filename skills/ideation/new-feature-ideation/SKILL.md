---
name: feature-ideation
description: Analyze a codebase to generate ranked feature ideas that would make the product more differentiated and valuable. Use this skill whenever the user asks to brainstorm features, generate product ideas from a codebase, ideate on what to build next, or wants to explore what their product could become. Also trigger when someone says "look at my code and suggest features," "what should we build next," "give me ideas based on the codebase," "brainstorm differentiated features," or "help me find product opportunities in my product." Reads the codebase structure, models, routes, and dependencies to generate grounded, technically-aware feature ideas with prioritized rankings. Outputs a formatted Markdown file.
---

# Feature Ideation Skill

## Purpose
Analyze a real codebase to generate 10 grounded, differentiated feature ideas — not generic suggestions, but ideas that are specifically informed by what is already built, what the architecture supports, and where the meaningful product gaps are.

---

## Step 1: Gather Context

Before touching the codebase, ask in a single batch if not provided:

- **Where is the codebase?** (path, GitHub URL, or confirm it's the current working directory)
- **What is the product?** (1-2 sentence description of what it does and who it's for)
- **Are there focus areas?** (specific parts of the product, user flows, or modules to prioritize)
- **Are there target domains or market segments?** (e.g., "enterprise buyers," "developers," "healthcare ops," "growth/activation")
- **What is the competitive context?** (who are they trying to differentiate from, if known)
- **Any ideas already being considered?** (avoid duplicating what's already on the roadmap)
- **Output location?** (where to save the Markdown file — default to `./feature-ideas.md`)

---

## Step 2: Codebase Analysis

Work through these phases in order. The goal is to build a mental model of the product's current shape, capabilities, and boundaries before generating a single idea.

---

### Phase 1: Orient

Start with the high-level structure. Understand what kind of product this is and what stack it runs on.

```bash
# Get top-level directory structure
find . -maxdepth 2 \
  -not -path '*/node_modules/*' \
  -not -path '*/.git/*' \
  -not -path '*/__pycache__/*' \
  -not -path '*/dist/*' \
  -not -path '*/.next/*' \
  | sort

# Read the primary project manifest (pick whichever exists)
cat package.json 2>/dev/null || cat pyproject.toml 2>/dev/null || cat Cargo.toml 2>/dev/null || cat go.mod 2>/dev/null

# Read README for product intent
cat README.md 2>/dev/null || cat README.rst 2>/dev/null | head -100
```

**What to extract:**
- Tech stack (framework, language, major dependencies)
- Product type (web app, API, CLI, mobile backend, etc.)
- Notable third-party integrations (auth, payments, AI, analytics, messaging, etc.)
- Any stated product goals or user-facing descriptions

---

### Phase 2: Map the Domain Model

The data model is the most reliable signal for what the product actually does. Read it carefully.

```bash
# Django / SQLAlchemy models
find . -name "models.py" -not -path "*/node_modules/*" | head -10
find . -name "models/*.py" -not -path "*/node_modules/*" | head -10

# Prisma schema
find . -name "schema.prisma" | head -5

# Rails models
find . -path "*/app/models/*.rb" | head -20

# TypeORM / Drizzle / Sequelize entities
find . -name "*.entity.ts" -o -name "*.model.ts" | grep -v node_modules | head -20

# GraphQL schema
find . -name "*.graphql" -o -name "schema.gql" | grep -v node_modules | head -10

# OpenAPI / Swagger
find . -name "openapi.yaml" -o -name "swagger.yaml" -o -name "openapi.json" | head -5
```

Then read the most relevant files found above. Extract:
- Core entities and their relationships
- Fields that hint at user intent (e.g., a `last_reminded_at` field implies a notification system)
- Enum values (these reveal the full state space of a model)
- Soft-delete patterns, audit fields, or versioning hints
- Any entities that seem underdeveloped relative to others

---

### Phase 3: Map the Surface Area

Read routes and API endpoints to understand what the product exposes today.

```bash
# Express / Next.js / Fastify routes
find . -path "*/routes/*.ts" -o -path "*/routes/*.js" -o -path "*/api/*route*" | grep -v node_modules | head -20

# Next.js App Router pages
find . -path "*/app/**/*.tsx" -not -path "*/node_modules/*" -name "page.tsx" | head -20

# FastAPI / Flask routes
grep -r "@router\|@app.route\|@app.get\|@app.post" --include="*.py" -l | grep -v node_modules | head -10

# Django URL patterns
find . -name "urls.py" -not -path "*/node_modules/*" | head -10

# Rails routes
cat config/routes.rb 2>/dev/null | head -80
```

**What to extract:**
- Major feature areas (groups of routes reveal product sections)
- CRUD patterns vs. action-oriented endpoints (actions reveal product intent)
- Endpoints that exist but seem thin or incomplete relative to peers
- Any admin-only or internal-only routes (hidden functionality)
- Missing standard patterns (e.g., a resource that has GET but no bulk operations)

---

### Phase 4: Read the Integration Layer

Third-party integrations are the richest source of ideation signal. They reveal what the team has already invested in connecting — and what's being underutilized.

```bash
# Find integration / service files
find . \( -path "*/integrations/*" -o -path "*/services/*" -o -path "*/connectors/*" \) \
  -not -path "*/node_modules/*" | head -30

# Look for named third-party clients
grep -r "stripe\|twilio\|sendgrid\|openai\|anthropic\|segment\|mixpanel\|intercom\|hubspot\|salesforce\|slack\|notion\|linear\|github" \
  --include="*.ts" --include="*.py" --include="*.js" --include="*.rb" \
  -l 2>/dev/null | grep -v node_modules | head -20

# Check environment variable names (reveals what's connected)
cat .env.example 2>/dev/null || cat .env.sample 2>/dev/null || grep -r "process.env\." --include="*.ts" -h | sort -u | head -40
```

**What to extract:**
- Which integrations are present but may be underutilized (e.g., Stripe installed but only used for basic billing)
- Integrations that are partially implemented
- Patterns in the integration choices (all communication tools? all dev tools? all data tools?)
- What's notably absent given the product type

---

### Phase 5: Read the Frontend Surface

If a frontend exists, scan it for UX patterns and empty states that reveal gaps.

```bash
# Find major page/view components
find . \( -path "*/pages/*" -o -path "*/views/*" -o -path "*/screens/*" \) \
  -not -path "*/node_modules/*" \
  \( -name "*.tsx" -o -name "*.jsx" -o -name "*.vue" -o -name "*.svelte" \) | head -30

# Look for TODO/FIXME/HACK comments — these are honest product notes
grep -r "TODO\|FIXME\|HACK\|XXX\|PLACEHOLDER\|coming soon\|not implemented" \
  --include="*.tsx" --include="*.ts" --include="*.py" --include="*.jsx" \
  -n 2>/dev/null | grep -v node_modules | head -30

# Find any feature flag or toggle definitions
grep -r "featureFlag\|feature_flag\|isEnabled\|FEATURE_\|flags\." \
  --include="*.ts" --include="*.py" --include="*.js" -l 2>/dev/null | grep -v node_modules | head -10
```

**What to extract:**
- Pages that exist but have thin content relative to others
- TODO/FIXME comments that reveal known gaps
- Feature flags that hint at in-progress or paused work
- UI patterns that suggest an incomplete user journey

---

### Phase 6: Focus Area Deep Dive (if specified)

If the user specified a product area, domain, or market segment to focus on, do a targeted read of that area before generating ideas.

```bash
# Example: if user says "focus on the reporting module"
find . -path "*report*" -not -path "*/node_modules/*" | head -20
grep -r "report\|analytics\|dashboard\|metric\|chart" \
  --include="*.ts" --include="*.py" -l 2>/dev/null | grep -v node_modules | head -15
```

Adapt the search terms to the stated focus area.

---

## Step 3: Synthesis Before Ideation

Before generating ideas, synthesize observations into a brief internal model:

**Answer these questions from your codebase reading:**
1. What is this product's core loop? (the primary action users repeat)
2. What has the team invested in heavily? (the most developed areas)
3. What is notably thin or absent? (gaps relative to the product's apparent ambition)
4. What integrations are underutilized? (connected but not deeply leveraged)
5. What does the data model support that the UI doesn't expose?
6. What do the TODO comments reveal about known gaps?
7. What would the next natural layer of value be, given what's already built?

This synthesis drives idea quality. Generic ideas come from not reading the codebase carefully enough.

---

## Step 4: Idea Generation Framework

Generate exactly 10 ideas. For each idea, apply these filters before including it:

**Quality filters:**
- Is this grounded in something specific found in the codebase? (not a generic suggestion)
- Is this differentiated from obvious/commodity features?
- Is there a clear user benefit — not just a technical capability?
- Is it buildable given the current stack and integrations?
- Is it meaningfully distinct from the other 9 ideas?

**Idea variety targets across the 10:**
- At least 2 ideas that leverage an existing integration more deeply
- At least 2 ideas that address an obvious gap in the data model or routes
- At least 1 idea that is AI/ML-powered (if the stack supports it)
- At least 1 idea that improves an existing workflow rather than adding a new one
- At least 1 idea that opens a new market segment or buyer type
- At least 1 "ambitious" idea that would require meaningful new investment

---

## Step 5: Prioritization Framework

Rank all 10 ideas using this scoring rubric. Score each on 1-5, then sum:

| Dimension | What it measures |
|---|---|
| **User Impact** | How meaningfully does this improve the experience for the target user? |
| **Differentiation** | How much does this set the product apart from alternatives? |
| **Buildability** | How well does the current stack and architecture support this? |
| **Strategic Fit** | How well does this align with the stated product direction or market focus? |
| **Effort Efficiency** | How much value per unit of engineering investment? |

Rank #1 = highest total score. Break ties by weighting User Impact and Differentiation.

---

## Step 6: Output — feature-ideas.md

Write the output as a complete Markdown file to the specified path (default: `./feature-ideas.md`).

---

```markdown
# Feature Ideas — [Product Name]
*Generated: [Date]*
*Codebase analyzed: [path or repo name]*
*Focus areas: [stated focus, or "General — full product"]*
*Target segment: [stated segment, or "General"]*

---

## Codebase Summary

> Brief 3-5 sentence summary of what the codebase reveals about the product: 
> its core loop, tech stack, major integrations, and most developed areas. 
> This grounds the reader before the ideas.

---

## Feature Ideas (Ranked by Priority)

---

### #1 — [Feature Name]

**Priority rank:** 1 of 10  
**Category:** [Workflow improvement / New capability / Integration depth / Market expansion / AI-powered / etc.]  
**Effort estimate:** Small / Medium / Large  

**What it is:**  
2-3 sentences describing the feature in plain product language. What does the user experience? What can they do that they couldn't before?

**Why it makes sense:**  
2-4 sentences grounded in codebase evidence. Reference specific models, routes, integrations, or TODO comments that support this idea. Explain the user problem it solves and why this product is well-positioned to solve it.

**Why it differentiates:**  
1-2 sentences on how this sets the product apart — from competitors, from the status quo, or from generic alternatives.

**Codebase signal:**  
> Specific file, model, integration, or pattern observed that grounds this idea.  
> e.g., "`/models/user.py` has a `last_active_at` field with no corresponding UI surface — suggesting retention tooling is possible without new data infrastructure."

**Prioritization scores:**

| Dimension | Score (1-5) |
|---|---|
| User Impact | |
| Differentiation | |
| Buildability | |
| Strategic Fit | |
| Effort Efficiency | |
| **Total** | **/25** |

---

[Repeat for ideas #2 through #10, with rank and total score decreasing]

---

## Prioritization Summary

| Rank | Feature | Total Score | Effort | Category |
|---|---|---|---|---|
| 1 | [Name] | /25 | S/M/L | |
| 2 | [Name] | /25 | S/M/L | |
| 3 | [Name] | /25 | S/M/L | |
| 4 | [Name] | /25 | S/M/L | |
| 5 | [Name] | /25 | S/M/L | |
| 6 | [Name] | /25 | S/M/L | |
| 7 | [Name] | /25 | S/M/L | |
| 8 | [Name] | /25 | S/M/L | |
| 9 | [Name] | /25 | S/M/L | |
| 10 | [Name] | /25 | S/M/L | |

---

## Quick Wins (High score, Small effort)

Call out any ideas that scored well AND are estimated Small effort — these are the candidates to slot into the next sprint without a major planning discussion.

---

## Notes on What Was Not Generated

Brief note on ideas that came close but were excluded, and why. This shows the thinking and prevents the same ideas from being re-suggested next time.

---

*To turn any of these into a full ticket, use the feature-ticket-writer skill.*  
*To evaluate these against strategic priorities, use the product-strategy-doc skill.*
```

---

## Step 7: Quality Check Before Writing the File

Before saving, verify:

- [ ] All 10 ideas cite specific codebase evidence — no generic suggestions
- [ ] Ideas are meaningfully distinct from each other (no variations of the same concept)
- [ ] At least one idea is ambitious and pushes the product's current boundaries
- [ ] Prioritization scores are differentiated (not all clustered at the same total)
- [ ] The codebase summary accurately reflects what was found
- [ ] Focus area or market segment constraints were honored if specified

---

## Output Format

- Save the file to the specified path using the `create_file` tool
- Present the file to the user using `present_files`
- After presenting, offer two follow-ups:
  - Write a ticket for any of the top ideas using the feature-ticket-writer skill
  - Map the top 3 ideas into an OST using the opportunity-solution-tree skill
