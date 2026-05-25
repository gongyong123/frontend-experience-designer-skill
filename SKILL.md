---
name: frontend-experience-designer
description: "Project-aware frontend experience and motion design for websites, admin systems, dashboards, digital twins, tools, and landing pages. Use when Codex needs to classify the frontend project type, choose matching UI/UX rules, improve visual quality, add suitable motion, or help non-frontend developers build pages with the right style: premium marketing sites, Apple-like product pages, SaaS admin, BI dashboards, Three.js/digital twin scenes, editors, and developer portals."
---

# Frontend Experience Designer

Act as a project-aware frontend experience director. First identify what kind of product is being built, then apply the right visual density, layout rules, interaction patterns, and motion intensity.

This skill exists to help mixed-role teams, especially backend or full-stack developers, avoid using the wrong frontend style for the wrong project. A marketing site should feel memorable and premium. An admin system should feel efficient and stable. A dashboard should make status readable. A digital twin should support spatial understanding.

## Core Workflow

1. Classify the project type before designing:
   - `marketing-site`: official website, product launch, landing page, brand page
   - `admin-system`: backend management, CRUD, permissions, tables, forms
   - `dashboard`: BI, monitoring, metrics, command center, data overview
   - `digital-twin`: Three.js, 3D scene, equipment, spatial data, simulation
   - `tool-editor`: editor, canvas, workflow builder, configuration workbench
   - `developer-portal`: docs, API reference, SDK, integration guide

2. Choose the correct experience mode:
   - Marketing sites optimize for desire, clarity, brand, story, conversion.
   - Admin systems optimize for speed, predictability, scanability, low cognitive load.
   - Dashboards optimize for hierarchy, anomaly detection, trend reading, live status.
   - Digital twins optimize for spatial understanding, selection, camera motion, data overlays.
   - Tool/editors optimize for continuous work, stable controls, precise feedback.
   - Developer portals optimize for readability, navigation, code clarity, trust.

3. Set motion intensity:
   - `low`: admin systems, forms, dense tables, tools during active work
   - `medium`: dashboards, docs, SaaS product UI, onboarding flows
   - `high`: marketing sites, product launches, portfolios, immersive WebGL pages
   - `situational`: digital twins use strong motion only for camera, selection, alerts, simulation

4. Apply type-specific rules from references.

5. Verify:
   - The page type is visually recognizable.
   - The layout helps the target user finish the job.
   - Motion supports comprehension or brand, not noise.
   - Text, controls, and data stay readable on desktop and mobile.
   - Reduced-motion and performance constraints are respected.

## Reference Selection

Read only the relevant reference file after classifying the project:

- `references/project-classifier.md`: use when the project type is ambiguous.
- `references/marketing-site.md`: official websites, landing pages, product launch pages, Apple-like premium sites.
- `references/admin-system.md`: management systems, CRUD, tables, permissions, forms, enterprise software.
- `references/dashboard.md`: BI dashboards, monitoring, command centers, data-heavy overview pages.
- `references/digital-twin.md`: Three.js, 3D, digital twin, equipment selection, alarms, simulation.
- `references/tool-editor.md`: canvas editors, workflow builders, configuration tools, creation surfaces.
- `references/developer-portal.md`: docs, API reference, SDK pages, integration portals.
- `references/library-selection.md`: choose CSS, JS, GSAP, Three.js, video, or framework animation.
- `references/performance-checklist.md`: verify animation performance and accessibility.

## Default Rules

- Do not make every frontend page look like a marketing site.
- Do not make marketing sites look like admin dashboards.
- Do not use big heroes, cinematic scroll, or decorative motion inside dense admin workflows.
- Do not make dashboards flash everywhere; motion should highlight change and risk.
- Use premium motion for brand and product storytelling, but use calm feedback for operational software.
- Prefer fewer, stronger ideas over many animated decorations.

## Repository Description Suggestion

Use this for the GitHub repository description:

`A Codex skill that helps teams build project-aware frontend experiences: premium landing pages, admin systems, dashboards, digital twins, editors, developer portals, and polished motion design.`
