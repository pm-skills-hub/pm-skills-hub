# PM Skills Hub — Skills Repository

A collection of agent skills for product managers, designed for use with [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview).

Each skill is a structured set of instructions that teaches your AI agent how to perform a specific PM task — from writing PRDs to synthesizing user research.

## Downloading All Skills

### Option 1: Clone the repo

```bash
git clone https://github.com/YOUR_ORG/pm-skills-hub.git
```

All skills are in the `skills/` directory, organized by category.

### Option 2: Download as ZIP

Click the green **Code** button at the top of this page, then **Download ZIP**.

## Installing a Skill

1. Copy the skill folder (e.g. `skills/prd/enterprise-prd/`) into your agent's skills directory:
   - **Global**: `~/.claude/skills/`
   - **Per-project**: `your-project/.claude/skills/`
2. Open `CONFIG.md` inside the skill folder — it explains what to customize for your team.
3. Start Claude Code. The skill is automatically available.

## Skill Structure

Each skill folder contains three files:

| File | Purpose |
|------|---------|
| `SKILL.md` | The main instructions that teach the agent what to do |
| `CONFIG.md` | A customization guide — what to personalize for your team |
| `manifest.json` | Metadata (name, category, tags, version) |

## Categories

| Category | Folder | Description |
|----------|--------|-------------|
| PRDs | `skills/prd/` | Product requirements documents |
| Release Notes | `skills/release-notes/` | Changelog and release note generators |
| Ideation | `skills/ideation/` | Brainstorming and discovery frameworks |
| User Research | `skills/user-research/` | Interview synthesis and research tools |
| Strategy | `skills/strategy/` | Competitive analysis and positioning |
| Tech Specs | `skills/specs/` | API specs and technical documentation |
| Retros | `skills/retrospectives/` | Sprint retrospective facilitators |
| OKRs & Goals | `skills/okrs/` | OKR builders and goal tracking |
| Roadmaps | `skills/roadmaps/` | Roadmap planning and visualization |
| Prioritization | `skills/prioritization/` | Prioritization frameworks (RICE, MoSCoW, etc.) |
| Stakeholder Comms | `skills/stakeholder-comms/` | Status updates, exec summaries |
| Go-to-Market | `skills/go-to-market/` | Launch plans and GTM strategies |
| Metrics & Analytics | `skills/metrics/` | KPI dashboards and metrics frameworks |
| Customer Feedback | `skills/customer-feedback/` | Feedback loops, NPS, feature request triage |
| Other | `skills/other/` | Skills that don't fit the categories above |

## Submitting a Skill

Skills are submitted through the [PM Skills Hub](https://your-app-url.replit.app) web app, not directly via pull request. The app's AI automatically adapts your skill to work for any PM and generates a CONFIG.md — you just review and approve.

## License

MIT
