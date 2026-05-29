# Frontend Experience Designer Skill

A Codex skill for generating frontend work that respects product type, engineering boundaries, interaction quality, and modern visual standards.

It helps mixed-role teams use AI for frontend tasks without accidentally producing the wrong kind of UI: marketing pages that look like admin dashboards, admin systems that look like old templates, dashboards without data hierarchy, or WebGL/digital-twin screens that treat 3D as decoration.

## What It Does

- Infers the current collaboration mode from the user's request instead of asking for a job title.
- Classifies the product type before designing or scaffolding.
- Resolves architecture boundaries for mixed products, such as official website plus admin app.
- Chooses sensible frontend stack defaults when the user does not care about the stack.
- Applies type-specific UX, visual density, layout, and motion rules.
- Enforces runtime preflight checks before using modern frontend tooling.
- Keeps TypeScript projects TypeScript-first, including `vite.config.ts` for new Vite TS projects.
- Uses color tokens consistently across buttons, navigation, focus states, forms, charts, and selections.
- Avoids legacy admin templates such as black sidebars, flat gray backgrounds, and disconnected white cards.

## Product Types

The skill currently covers:

- Marketing sites and official websites
- Admin systems and CRUD back offices
- Dashboards and monitoring views
- Digital twins and WebGL spatial interfaces
- Tool/editor interfaces
- Developer portals and API documentation

## Key Design Principles

- Do not ask unnecessary questions when frontend defaults are enough.
- Ask only about decisions that affect architecture, tooling, or long-lived project boundaries.
- Follow existing project conventions before introducing new ones.
- Treat user role as a temporary collaboration mode, not a fixed identity.
- Do not infer business logic that belongs outside frontend engineering.
- Make product UI feel interactive and complete, even with mock data.
- Prefer cohesive design tokens over scattered one-off visual values.

## Repository Structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── admin-system.md
    ├── architecture-defaults.md
    ├── dashboard.md
    ├── developer-portal.md
    ├── digital-twin.md
    ├── library-selection.md
    ├── marketing-site.md
    ├── motion-patterns.md
    ├── performance-checklist.md
    ├── premium-website-motion.md
    ├── project-classifier.md
    └── tool-editor.md
```

## Local Development

This repository is the development workspace for the skill. To make changes take effect in Codex, sync the updated files into the local Codex skills directory:

```bash
cp SKILL.md ~/.codex/skills/frontend-experience-designer/SKILL.md
cp agents/openai.yaml ~/.codex/skills/frontend-experience-designer/agents/openai.yaml
cp references/*.md ~/.codex/skills/frontend-experience-designer/references/
```

Then restart Codex so the updated skill metadata and instructions are loaded.

## Current Focus

The skill is being tuned through practical frontend generation tests. Recent improvements include:

- Dynamic collaboration mode inference
- Node.js and package-manager preflight checks
- TypeScript project consistency rules
- Color token defaults
- Modern admin visual baseline rules

Future tuning will focus on stronger UI and interaction specifications while keeping the skill scoped to frontend engineering and experience quality.
