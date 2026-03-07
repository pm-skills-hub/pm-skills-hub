# Customizing This Skill

## Quick Start

This skill works out of the box and is designed to be universally applicable to any product manager running creative brainstorming sessions. However, you can personalize it to make it even more effective for your specific product, team, and industry context.

## What to Customize

### 1. Cross-Market Inspiration Sources

**What to look for:** The table in Step 2 lists 12 markets to pull inspiration from (Gaming, Finance, Healthcare, etc.).

**Why customize:** Your product may sit in or adjacent to specific industries where certain markets are more relevant than others. You might also have direct experience with particular markets that make certain analogies more actionable.

**Example:**
- Generic: "Markets to always consider pulling from (rotate across sessions)"
- Personalized: Add a 13th row for your industry (e.g., "Real Estate Tech — virtual tours, bidding systems, comparable analysis, mortgage calculators") or mark 2-3 markets as "primary inspiration sources" for your domain.

### 2. Default Wildness Dial Setting

**What to look for:** Step 1 mentions defaulting to "Stretched" if the user doesn't specify a wildness level.

**Why customize:** Different team cultures and product stages call for different default ambition levels. Early-stage startups might default to "Unhinged," while enterprise products might prefer "Grounded."

**Example:**
- Generic: "default to Stretched"
- Personalized: "default to Grounded for our established B2B product" or "default to Unhinged for our innovation lab initiatives"

### 3. Output File Path

**What to look for:** Step 5 specifies saving session summaries to `./jam-session-[product]-[date].md`

**Why customize:** Your team may have specific conventions for where ideation artifacts live.

**Example:**
- Generic: `./jam-session-[product]-[date].md`
- Personalized: `./docs/ideation/jam-session-[product]-[date].md` or `./discovery/brainstorms/[date]-jam-session.md`

### 4. Cross-Reference Skills

**What to look for:** The final line mentions flowing ideas into "feature-ticket-writer, feature-ideation, or opportunity-solution-tree skills."

**Why customize:** Add any custom skills you've created or remove references to skills you don't use.

**Example:**
- Generic: "feature-ticket-writer, feature-ideation, or opportunity-solution-tree skills"
- Personalized: "our product-brief-template, the design-sprint-kickoff skill, or the bet-validation skill"

## Tips

**Keep customizations in comments:** When you personalize the cross-market table or contrarian flip prompts, consider adding your customizations as additional rows/bullets with a comment like `<!-- custom for [your product] -->`. This makes it easier to merge future skill updates.

**Maintain a team-specific flip list:** The Contrarian Flip round (Step 4) works best when flips challenge your product's actual sacred cows. Keep a running list of your product's most deeply held assumptions and add them as additional flip prompts.

**Archive your sessions:** The summary output in Step 5 is designed to be lightweight. Consider keeping an `ideation-archive/` folder and reviewing past sessions quarterly — patterns often emerge across multiple jam sessions that point to deeper strategic opportunities.