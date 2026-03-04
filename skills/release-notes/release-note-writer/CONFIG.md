# Customizing This Skill

## Quick Start

This skill works out of the box to generate release notes for any product team. However, you can personalize it to match your team's specific workflows, documentation structure, and internal terminology. The more you customize, the more naturally it will fit your release process.

## What to Customize

### 1. Internal Documentation References

**What to look for:** The skill mentions "discovery doc or PRD" as generic planning documents.

**Why customize:** Your team may use different document types or naming conventions for planning artifacts.

**Example:**
- Generic: "Link to discovery doc or PRD if available"
- Personalized: "Link to RFC, Tech Spec, or Product Brief if available" (if your team uses RFCs and Tech Specs)
- Personalized: "Link to One-Pager or Design Doc if available" (if your team uses those terms)

### 2. Metrics & Success Criteria Defaults

**What to look for:** The "Metrics & Success Criteria" section uses generic placeholders.

**Why customize:** You can pre-populate common metrics your team tracks or reference your team's analytics tools.

**Example:**
- Generic: "Primary metric and current baseline"
- Personalized: "Primary metric in Mixpanel/Amplitude and current baseline" (specifying your analytics platform)
- Personalized: "OKR alignment and success threshold from [your planning doc]" (linking to your OKR framework)

### 3. Changelog Format

**What to look for:** The emoji-based changelog structure (✨ New, 🔧 Improved, etc.).

**Why customize:** Your team may already have an established changelog convention or prefer different categories.

**Example:**
- Generic: Uses ✨/🔧/🐛/⚠️ emoji categories
- Personalized: Replace with "Added / Changed / Fixed / Deprecated" if your team prefers text-only headings
- Personalized: Add your team's custom categories like "Performance" or "Security" if those are standard sections

### 4. Internal Roles & Stakeholders

**What to look for:** References to "CS/Sales" and "customer-facing teams."

**Why customize:** Your organization may have different team structures or names.

**Example:**
- Generic: "Talking Points (for CS/Sales)"
- Personalized: "Talking Points (for Customer Success and Account Management)" (if those are your team names)
- Personalized: "Enablement Brief (for GTM Teams)" (if you have a consolidated GTM organization)

## Tips

- **Keep customizations in placeholders:** When you personalize links or tool names, use bracket placeholders like [your Confluence space] so future you remembers to fill them in per release.
- **Version your changelog format:** If you customize the changelog structure, document it in your team wiki so everyone writes releases consistently.
- **Test with a past release:** Try generating notes for something you already shipped to see how the customizations work in practice before using it for a live release.
