---
name: weekly-product-email
description: Generate a polished weekly product team email for company-wide or customer distribution. Use this skill whenever the user asks to write a product update email, weekly PM email, roadmap update, product newsletter, or team digest. Also trigger when someone says "write our weekly update," "draft the product email," "send out what we shipped this week," or "write the roadmap highlights email." Produces a structured, engaging email covering roadmap highlights, feature spotlights, trends being watched, and team wins.
---

# Weekly Product Email Skill

## Purpose
Generate a well-structured, engaging weekly product email that keeps stakeholders informed, builds product culture, and spotlights the team's work — without sounding like a status report.

---

## Step 1: Gather Context

Before writing, collect the following. Ask in a single batch if not provided:

- **Audience:** Internal (company) or external (customers/prospects)? Or both?
- **Cadence name:** Does the team have a name for this email? (e.g., "The Weekly Build", "Product Pulse", "Ship It")
- **This week's highlights:** What shipped, launched, or hit a milestone?
- **Feature spotlight:** Is there a lesser-known or underutilized feature worth surfacing?
- **Trends / what we're watching:** Any market moves, competitive signals, or industry news relevant to your product area?
- **Team shoutouts:** Any individuals or teams to celebrate?
- **Upcoming:** What's coming next week or in the near term?
- **Tone:** Professional/buttoned-up? Conversational and fun? Something in between?
- **Approximate length:** Short (300-400 words) or full-length (600-900 words)?

If the user provides raw notes or a brain dump, extract structure from those before asking follow-up questions.

---

## Step 2: Email Structure

Produce the email using this structure. Adjust sections based on audience (internal vs. external) and available content.

---

### Subject Line Options

Provide 3 subject line options with different energy levels:
- **Direct:** Clear and informative ("Product Update — Week of [Date]")
- **Intriguing:** A hook that creates curiosity
- **Conversational:** Warm and approachable

---

### Email Body

---

**[NEWSLETTER NAME] | [Week of Date]**

---

#### 👋 Opening (2-4 sentences)

Set the tone with a brief, human opener. Options:
- Reference something timely (a season, a company moment, an industry news item)
- Open with a provocative question or insight
- Open with a short reflection on the theme of this week's work

Avoid: "Hi team, hope everyone is doing well." Start with something memorable.

---

#### 🚀 Roadmap Highlights

Cover the most important shipped work or upcoming milestone. Structure:

**[Feature or Initiative Name]**
- What it is (one sentence, plain language — no jargon)
- Why it matters (user benefit or business impact)
- Status: Shipped / In Progress / Coming Soon
- Link or screenshot if available

Repeat for 2-4 items. Lead with the highest-impact item.

**Internal version:** Can include WIP items, metrics, and internal context.  
**External version:** Only include shipped or announced items. Frame around customer value, not internal process.

---

#### 💡 Feature Spotlight

Surface one underutilized or lesser-known feature. This section builds product literacy and drives adoption.

Structure:
- **Feature name** and where to find it
- The problem it solves (1-2 sentences)
- A concrete use case or example ("Try it when you need to...")
- Optional: A stat showing usage or impact

Write this in the second person, directly to the reader ("You can use X to...")

---

#### 📡 Trends We're Watching

Share 1-3 signals from the market, industry, or competitive landscape that are relevant to your product space. This positions the PM team as strategically aware and builds context for stakeholders.

For each trend:
- Name the signal clearly
- Explain why it matters for your product or customers
- Note what (if anything) you're doing about it

**Tone guidance:** Analytical but accessible. Not alarmist. Not navel-gazing. Show thinking, not just information.

---

#### 🎉 Team Wins & Shoutouts (Optional)

Celebrate specific people or teams. Be specific — name names and name the contribution.

Avoid generic praise like "great work everyone." Instead: "Shoutout to [Name] for shipping [X] ahead of schedule and writing the best release notes we've seen this quarter."

---

#### 🗓️ Coming Up

2-4 bullets on what to expect next week or in the next sprint. Keep it brief. Use:
- "[Feature] enters beta next week"
- "[Team] is presenting [X] to leadership on [Day]"
- "We're kicking off discovery for [Initiative]"

---

#### ✉️ Closing

End with something human:
- A question that invites a reply ("What feature would you love to see spotlighted next week?")
- A relevant quote or observation
- A brief note of appreciation for the team

Sign off with the PM or team name.

---

## Step 3: Tone & Style Guidelines

- **Voice:** First-person plural ("we shipped," "we're watching") unless it's signed by one person
- **Jargon:** Minimize. If unavoidable, define it
- **Sentence length:** Vary it. Mix short punchy sentences with longer explanatory ones
- **Emoji:** Use sparingly as section headers only (not mid-sentence), unless the brand is casual
- **Links:** Anchor text over raw URLs. ("See the release notes" not "https://...")
- **Length:** Respect reader time. Every sentence should earn its place

---

## Step 4: Internal vs. External Variants

| Element | Internal | External |
|---|---|---|
| WIP items | ✅ Include | ❌ Exclude |
| Internal metrics | ✅ Include | ❌ Exclude |
| Team shoutouts | ✅ Include | Optional |
| Competitive mentions | ✅ Direct | ⚠️ Careful framing |
| Tone | More candid | More polished |
| Feature spotlight | Any feature | Launched features only |

If both versions are needed, produce internal first, then adapt.

---

## Output Format

- Produce as a clean, copy-paste ready email in Markdown
- Include 3 subject line options at the top
- Use section headers and light formatting
- Flag any sections where the user should fill in specifics (e.g., "[Add screenshot here]" or "[Insert metric]")
- Offer a short version on request (subject, opening, highlights only, closing)
