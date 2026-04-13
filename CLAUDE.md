# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

This is a **Claude Code Superpowers skill** — a single-file skill definition that teaches Claude how to conduct structured design portfolio reviews from a hiring manager perspective.

The skill lives entirely in `SKILL.md`, which follows the superpowers frontmatter format (`name`, `description`) and contains the full behavioral specification for the skill.

## Skill Structure

`SKILL.md` defines a 5-step workflow:

1. **Step 0 — Context gathering**: Infer seniority target, input format, role type, and audience
2. **Step 1 — Content ingestion**: Fetch via URL (`WebFetch`) or read PDF; capture all case studies, About, and CTAs
3. **Step 2 — Level calibration**: Apply a 5-level rubric (junior → director) across 5 dimensions
4. **Step 3 — Evaluation**: Score 7 dimensions with severity codes (🔴 Critical / 🟡 Major / 🟢 Minor)
5. **Step 4 — Report generation**: Output a fixed-format annotated report with issue log, section analysis, level assessment, and hiring manager verdict
6. **Step 5 — Delivery notes + edge cases**: Behavior for password-protected, Dribbble-only, too many/few pieces, student portfolios

## Evaluated Dimensions (3A–3G)

- **3A Copy & Writing** — headlines, body copy, outcome language, typos
- **3B Information Architecture** — navigation depth, mobile, resume availability
- **3C Positioning & Personal Brand** — specialization, POV, visual identity
- **3D Skills Demonstrated** — evidence vs. assertion gap
- **3E Case Studies** — most weighted; assesses problem framing, role clarity, process, decisions, outcomes, narrative arc
- **3F CTAs** — contact discoverability, resume link, LinkedIn
- **3G About Me** — professional story, personality, CTA handoff

## Editing This Skill

- The frontmatter `description` field controls when the skill auto-triggers — keep it specific so it doesn't false-positive on general design questions
- The report template in Step 4 is intentionally rigid; preserve its structure when modifying
- Severity codes (🔴🟡🟢) must remain consistent throughout the skill for the issue log to make sense
- The level calibration table in Step 2 anchors all per-level assessments — if you add new dimensions, add them to this table first
