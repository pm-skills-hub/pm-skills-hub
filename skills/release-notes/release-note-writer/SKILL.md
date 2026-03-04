---
name: feature-release-notes
description: Generate polished, user-facing or internal feature release notes and changelogs. Use this skill whenever the user asks to write release notes, a changelog, ship notes, "what's new" content, or any documentation about what was released or shipped. Also trigger when someone says "write up what we shipped," "document this release," or "help me write the changelog." Produces both user-facing (benefit-led) and internal (detail-led) variants with consistent structure and appropriate tone for each.
---

# Feature Release Notes Skill

## Purpose
Produce clear, well-structured release notes that communicate what changed, why it matters, and how to use it — tailored to the audience (end users, internal teams, or developers).

---

## Step 1: Gather Context

Before writing, identify the following. Ask in a single batch if not provided:

- **What was released?** (feature name, brief description)
- **Who is the audience?** (end users, customers, internal team, developers/API consumers)
- **What problem does it solve?** (the user pain point addressed)
- **What changed specifically?** (new behaviors, UI changes, API changes, deprecations)
- **Is anything deprecated or breaking?** (critical to flag prominently)
- **Are there usage instructions or steps?** (how to access or enable the feature)
- **Are there known limitations?** (edge cases, rollout scope, beta caveats)
- **Release type:** Major feature / Minor improvement / Bug fix / Deprecation
- **Links to include?** (docs, changelog page, support article, demo)

---

## Step 2: Release Notes Structure

Produce the appropriate format based on audience. Default to both internal and external versions.

---

### External / User-Facing Release Notes

These should lead with value and be written for a non-technical audience (unless the product is developer-focused).

---

**[Feature Name]**  
*[Release Type] — [Date or Version]*

---

#### What's New

Write 2-4 sentences in plain language:
- What this feature does
- The user problem it solves
- Who benefits most from it

Lead with the benefit, not the mechanism. 

✅ "You can now export reports directly to PDF with one click — no more downloading CSV and reformatting."  
❌ "A PDF export function has been added to the reports module."

---

#### How to Use It

Step-by-step instructions if the feature requires user action to discover or enable:
1. Navigate to [location]
2. Click [action]
3. [Result]

If the feature is automatic or passive (e.g., a performance improvement or a bug fix), skip this section or replace with: "This improvement takes effect automatically — no action needed."

---

#### Availability

Specify scope of rollout:
- Available to: All users / Pro plan and above / Beta participants / Specific regions
- Rollout: Full / Gradual (X% of users) / Feature flag / Admin must enable

---

#### Learn More

- [Link to documentation]
- [Link to support article]
- [Link to demo video or walkthrough]

---

### Internal / Team-Facing Release Notes

These are more detailed, include technical context, and are used by CS, Sales, Support, and leadership.

---

**[Feature Name] — Internal Release Summary**  
*[Date] | PM: [Your Name] | Eng: [Team or Lead]*

---

#### Summary

One paragraph: What shipped, why, and what outcome we expect.

---

#### What Changed

Itemized list of all changes. Include:
- New UI components or flows
- New API endpoints or parameters
- Changed behavior (before → after)
- Removed or deprecated items (flag these clearly with ⚠️)
- Behind-the-scenes changes (logging, telemetry, performance)

---

#### Why We Built This

Reference the problem statement, user research, or ticket/initiative that drove this:
- Problem being solved
- Evidence (customer request volume, NPS feedback, support ticket trends)
- Link to discovery doc or PRD if available

---

#### Known Limitations

Be honest about what isn't covered yet:
- Unsupported edge cases
- Rollout exclusions
- Performance caveats
- Things in the backlog for v2

---

#### Metrics & Success Criteria

How we'll know it's working:
- Primary metric and current baseline
- Measurement timeline
- Owner for post-launch review

---

#### Talking Points (for CS/Sales)

Help customer-facing teams discuss the feature:
- **Lead with:** [the top customer benefit in one sentence]
- **If asked about [common question]:** [suggested response]
- **Do not say:** [anything inaccurate, overpromised, or not yet shipped]

---

#### Deprecation Notice (if applicable)

⚠️ **Breaking Change / Deprecation**

If this release deprecates or breaks existing behavior:
- What is being deprecated
- Why
- Timeline (when it becomes unavailable)
- Migration path or alternative
- Who is affected and how to notify them

---

## Step 3: Changelog Entry Format

For teams maintaining a running changelog (Markdown, Notion, etc.), produce a compact entry:

```
## [Version or Date]

### ✨ New
- [Feature name]: [one-line description of the benefit]

### 🔧 Improved
- [Item]: [what changed and why it's better]

### 🐛 Fixed
- [Bug description]: [what was happening and what now happens]

### ⚠️ Deprecated / Breaking
- [Item]: [what changed, migration path, timeline]
```

---

## Step 4: Tone by Audience

| Audience | Tone | Language | Length |
|---|---|---|---|
| End users (B2C) | Friendly, benefit-led | Plain English | Short (100-200 words) |
| Business customers (B2B) | Professional, value-focused | Business language | Medium (200-400 words) |
| Developers / API | Precise, technical | Technical with examples | As long as needed |
| Internal team | Direct, complete | Internal jargon OK | Full detail |
| Executive summary | Concise, outcome-focused | Business impact only | 3-5 bullets |

---

## Step 5: Quality Checklist

- [ ] Leading with benefit, not feature mechanics
- [ ] No passive voice ("was added" → "you can now")
- [ ] Breaking changes flagged with ⚠️ prominently
- [ ] Rollout scope is specified (not assumed to be "everyone")
- [ ] Instructions are step-by-step if user action is required
- [ ] Internal version includes metrics and owner
- [ ] Talking points give CS/Sales a clear lead message

---

## Output Format

- Produce both external and internal versions by default (unless only one is requested)
- Format as clean Markdown, copy-paste ready
- Use headers, short paragraphs, and numbered steps
- Flag placeholders the user needs to fill in (e.g., "[link to docs]", "[metric baseline]")
- For bulk releases (multiple features), structure as a changelog with entries per feature
