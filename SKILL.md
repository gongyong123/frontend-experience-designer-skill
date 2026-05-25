---
name: frontend-experience-designer
description: "Project-aware frontend experience and motion design for websites, admin systems, dashboards, WebGL/digital twins, tools, and landing pages. Use when Codex needs to classify the frontend project type, choose matching UI/UX rules, choose a suitable frontend architecture for non-frontend users, improve visual quality, add suitable motion, or help teams build pages with the right style: SEO-friendly official sites, premium marketing pages, Vue3 admin systems, BI dashboards, Babylon.js digital twins, editors, and developer portals."
---

# Frontend Experience Designer

Act as a project-aware frontend experience director. First identify what kind of product is being built and where the technical architecture should come from, then apply the right visual density, layout rules, interaction patterns, and motion intensity.

This skill exists to help mixed-role teams, especially backend or full-stack developers, avoid using the wrong frontend style for the wrong project. A marketing site should feel memorable and premium. An admin system should feel efficient and stable. A dashboard should make status readable. A digital twin should support spatial understanding.

## Core Workflow

1. Classify the project type before designing:
   - `marketing-site`: official website, product launch, landing page, brand page
   - `admin-system`: backend management, CRUD, permissions, tables, forms
   - `dashboard`: BI, monitoring, metrics, command center, data overview
   - `digital-twin`: WebGL, Babylon.js, 3D scene, equipment, spatial data, simulation
   - `tool-editor`: editor, canvas, workflow builder, configuration workbench
   - `developer-portal`: docs, API reference, SDK, integration guide

2. Decide the architecture source before choosing libraries:
   - Existing project or reference folder: inspect it and follow its stack, routing, styling, state, UI library, and file conventions.
   - User specified stack: respect it unless it conflicts with the existing project; if they only name a framework, complete the missing companion choices from `references/architecture-defaults.md`.
   - Empty folder plus long-lived app/framework request: ask one concise stack question with mainstream options.
   - Empty folder plus simple test/demo page: take the shortest path, usually vanilla HTML/CSS/JS.
   - User says "you decide", "anything is fine", or "I don't know frontend": use the organization defaults in `references/architecture-defaults.md`.

3. Choose the correct experience mode:
   - Marketing sites optimize for desire, clarity, brand, story, conversion.
   - Admin systems optimize for speed, predictability, scanability, low cognitive load.
   - Dashboards optimize for hierarchy, anomaly detection, trend reading, live status.
   - Digital twins optimize for spatial understanding, selection, camera motion, data overlays.
   - Tool/editors optimize for continuous work, stable controls, precise feedback.
   - Developer portals optimize for readability, navigation, code clarity, trust.

4. Set motion intensity:
   - `low`: admin systems, forms, dense tables, tools during active work
   - `medium`: dashboards, docs, SaaS product UI, onboarding flows
   - `high`: marketing sites, product launches, portfolios, immersive WebGL pages
   - `situational`: digital twins use strong motion only for camera, selection, alerts, simulation

5. Apply type-specific rules from references.

6. Verify:
   - The page type is visually recognizable.
   - The layout helps the target user finish the job.
   - Motion supports comprehension or brand, not noise.
   - Text, controls, and data stay readable on desktop and mobile.
   - Reduced-motion and performance constraints are respected.

## Reference Selection

Read only the relevant reference file after classifying the project:

- `references/project-classifier.md`: use when the project type is ambiguous.
- `references/architecture-defaults.md`: use when selecting a framework/library stack, especially for empty folders, large projects, non-frontend users, or "you decide" requests.
- `references/marketing-site.md`: official websites, landing pages, product launch pages, Apple-like premium sites.
- `references/admin-system.md`: management systems, CRUD, tables, permissions, forms, enterprise software.
- `references/dashboard.md`: BI dashboards, monitoring, command centers, data-heavy overview pages.
- `references/digital-twin.md`: Babylon.js, WebGL, 3D, digital twin, equipment selection, alarms, simulation.
- `references/tool-editor.md`: canvas editors, workflow builders, configuration tools, creation surfaces.
- `references/developer-portal.md`: docs, API reference, SDK pages, integration portals.
- `references/library-selection.md`: choose CSS, JS, GSAP, Babylon.js/WebGL, video, or framework animation.
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
