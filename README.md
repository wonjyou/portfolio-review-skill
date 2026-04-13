# portfolio-review

A Claude Code skill that conducts comprehensive design portfolio reviews from a hiring manager perspective. Created by Won J. You.

## What it does

When triggered, this skill opens with two clarifying questions (goal and scope), then evaluates the portfolio and produces a structured annotated report with severity-coded issues and a prioritized action plan. Reports can be exported as a self-contained HTML file.

## Triggers

The skill activates when someone:

- Shares a portfolio URL or PDF and asks for feedback, critique, or review
- Mentions seniority levels (junior, mid, senior, staff, lead, director) alongside a portfolio
- Says things like "roast my portfolio", "is my portfolio ready for [role]", or "what's wrong with my portfolio"

## Evaluation dimensions

| Dimension | What's assessed |
|---|---|
| **Copy & Writing** | Headlines, body copy, typos, grammar, witty/distinctive copy, micro-copy |
| **Information Architecture** | Work visibility, structure, navigation, responsiveness |
| **Positioning, Brand & Originality** | Market fit, positioning coherence, specialization, personality, creative distinctiveness |
| **Skills Demonstrated** | Evidenced vs. claimed competencies |
| **Case Studies** | Client/context/users/problem space foundations, process proportion, design clarity, rationale, live links/prototypes/demos, image legibility |
| **Call-to-Actions** | Contact discoverability, resume link, social profiles |
| **About Me & Essential Info** | Who/what/strengths/impact checklist, narrative, voice |
| **Visual Design Quality** | Gestalt principles, Dieter Rams principles, typography, color, spacing |
| **Portfolio Usability** | Scannability, wayfinding, labeling, cognitive load, performance, craft details and delight |
| **Positioning Coherence** | Whether the portfolio actually supports the target role |
| **Leadership Signal Evaluation** | Contribution vs. team outcomes, leadership vs. execution, cross-functional influence *(Lead+ only)* |

## Report structure

- **Executive Summary** with overall readiness score (X/10)
- **Issue Log** — all findings with severity codes (🔴 Critical / 🟡 Major / 🟢 Minor)
- **Section-by-Section Analysis** — detailed, referenced feedback per dimension
- **Level Assessment** — does the portfolio read at the target seniority level?
- **Priority Action Plan** — top 5 fixes in order of impact
- **What's Working** — genuine strengths to preserve
- **Hiring Manager Verdict** — candid debrief as if briefing a recruiter
- **Optional HTML export** — self-contained file with styled layout, color-coded severity, and checklist rendering

## Example use cases

### Full portfolio review before a job search

> "I'm applying for senior product designer roles at mid-size startups. Here's my portfolio: https://yourname.com — can you do a full review?"

Claude opens with two clarifying questions, then delivers a scored report across all dimensions with severity-coded issues and a prioritized top-5 fix list.

---

### Readiness check for a specific company tier

> "Is my portfolio ready for a FAANG-level senior IC role? PDF attached."

Claude calibrates the review against Senior/Staff-level expectations — emphasizing systems thinking, measurable outcomes, and cross-functional influence signals — and gives a candid hiring-manager verdict.

---

### Single case study deep dive

> "I want feedback only on my checkout redesign case study: https://yourname.com/checkout. I'm targeting a lead role."

Claude scopes the review to that case study and evaluates problem framing, role clarity, process documentation, decision rationale, and outcome evidence at lead-level bar.

---

### First portfolio out of bootcamp

> "I just finished a UX bootcamp and built my first portfolio. Roast it: https://yourname.com"

Claude applies the junior-level rubric, flags the most common entry-level mistakes (assertion-without-evidence, missing context, weak CTAs), and outputs a prioritized action plan.

---

### Freelance / agency positioning

> "I do brand and web design for agencies. Here's my site: https://yourname.com — does it position me well for B2B agency clients?"

Claude evaluates positioning coherence, specialization clarity, and whether the work speaks to the right buyer — not just general design quality.

---

### Export report as HTML

> "Review my portfolio at https://yourname.com and export the report as an HTML file I can share with my mentor."

Claude runs the full review and writes a self-contained `.html` file with styled severity badges, a collapsible issue log, and checklist rendering.

---

### Targeted section fix

> "My About page feels weak. Can you review just that section? https://yourname.com/about"

Claude evaluates the About page against the who/what/strengths/impact checklist and narrative criteria, without scoring the rest of the portfolio.

---

## Installation

### Manual (local)

The plugin structure is already in place. To install manually, copy the plugin cache entry and register it:

```bash
# 1. Copy to plugin cache
mkdir -p ~/.claude/plugins/cache/portfolio-review-skill/portfolio-review/1.0.0
cp -r .claude .claude-plugin README.md CLAUDE.md \
  ~/.claude/plugins/cache/portfolio-review-skill/portfolio-review/1.0.0/

# 2. Add to ~/.claude/settings.json under "enabledPlugins":
#    "portfolio-review@portfolio-review-skill": true

# 3. Add to ~/.claude/plugins/installed_plugins.json under "plugins":
#    "portfolio-review@portfolio-review-skill": [{ "scope": "user", "installPath": "...", "version": "1.0.0" }]
```

Then start a new Claude Code session — the skill will be available immediately.

## Repository structure

```
portfolio-review/
├── .claude/
│   └── skills/
│       └── portfolio-review/
│           └── SKILL.md          # The skill definition
├── .claude-plugin/
│   ├── marketplace.json          # Plugin marketplace manifest
│   └── plugin.json               # Plugin metadata and skill paths
├── CLAUDE.md                     # Guidance for Claude Code
├── README.md                     # This file
└── SKILL.md                      # Canonical source (kept in sync with .claude/skills/)
```
