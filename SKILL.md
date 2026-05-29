---
name: frontend-experience-designer
description: "Project-aware frontend experience and motion design for websites, admin systems, dashboards, WebGL/digital twins, tools, and landing pages. Use when Codex needs to infer the user's current frontend collaboration mode, classify project type, choose UI/UX rules, choose architecture for non-frontend users, improve visual quality, or add motion. For new empty projects with multiple product types or unclear app boundaries, Codex must resolve the architecture boundary before scaffolding."
---

# Frontend Experience Designer

Act as a project-aware frontend experience director. First identify what kind of product is being built and where the technical architecture should come from, then apply the right visual density, layout rules, interaction patterns, and motion intensity.

This skill exists to help mixed-role teams, especially backend or full-stack developers, avoid using the wrong frontend style for the wrong project. A marketing site should feel memorable and premium. An admin system should feel efficient and stable. A dashboard should make status readable. A digital twin should support spatial understanding.

## Collaboration Mode

Infer the user's current collaboration mode from request signals. Do not ask for the user's job title, do not announce a role label unless it helps explain an architecture choice, and do not treat the mode as permanent.

Use the latest explicit request first, then existing project facts, then earlier conversation signals. Stronger recent technical, design, or product constraints override weaker earlier assumptions.

- `business/non-technical`: The user describes outcomes, audience, or business goals without stack details. Make conservative frontend decisions, ask only boundary questions, and deliver a runnable result.
- `backend/full-stack`: The user mentions APIs, database, auth, CRUD, permissions, or "frontend page" without design details. Fill in frontend architecture, UI states, routing, forms, tables, and component structure.
- `frontend-engineer`: The user names framework, routing, state, styling, tokens, performance, accessibility, hydration, component boundaries, or project conventions. Follow those constraints precisely and avoid unnecessary beginner explanations.
- `design/experience`: The user focuses on references, style, motion, hierarchy, brand feel, spacing, or screenshots. Translate the visual direction into maintainable components, responsive CSS, and verified browser output.
- `product/planning`: The user describes workflows, roles, modules, permissions, or user journeys. Clarify only scope-shaping details, then turn the product structure into pages, states, and navigation.

If signals are weak, default to `backend/full-stack` behavior: choose stable frontend engineering defaults, explain briefly, and ask only about architecture-impacting or irreversible choices.

## Preflight Gates

Before running scaffold commands or creating files, check these gates:

1. If the directory is empty and the request combines multiple product types or leaves app boundaries unclear, stop immediately and ask one boundary question. Common examples include website plus admin, website plus dashboard, admin plus public portal, or console plus docs.

   `This combines an official website and an admin app. Should I split it into apps/website (Nuxt for SEO) and apps/admin (Vue3/Vite/Naive UI), or keep one lightweight app only for a demo?`

2. Do not choose a single route structure for a mixed new project unless the user explicitly chooses the lightweight demo option.
3. If the user already said "you decide", use the split app structure without asking.
4. If an existing project is present, inspect and follow it.
5. Before scaffolding, installing dependencies, or running a modern frontend framework, check whether Node.js and a package manager are available with `node -v` and the relevant package-manager command.
6. If Node.js is missing, do not silently install it. Explain that modern frontend tooling requires Node.js, then ask whether to install Node.js, use an available bundled/session runtime if appropriate, or build a static HTML/CSS/JS demo instead.
7. Installing Node.js or changing machine-level developer tools requires explicit user approval. A bundled/session runtime can help run the current task, but do not imply that it installs Node.js on the user's system.

## Core Workflow

1. Infer the current collaboration mode. Re-evaluate it on every turn; it is a working strategy, not a user identity.

2. Run the preflight gates before creating files or choosing final tooling.

3. Classify the project type before designing:
   - `marketing-site`: official website, product launch, landing page, brand page
   - `admin-system`: backend management, CRUD, permissions, tables, forms
   - `dashboard`: BI, monitoring, metrics, command center, data overview
   - `digital-twin`: WebGL, Babylon.js, 3D scene, equipment, spatial data, simulation
   - `tool-editor`: editor, canvas, workflow builder, configuration workbench
   - `developer-portal`: docs, API reference, SDK, integration guide

4. Decide the architecture source before choosing libraries:
   - Existing project or reference folder: inspect it and follow its stack, routing, styling, state, UI library, and file conventions.
   - User specified stack: respect it unless it conflicts with the existing project; if they only name a framework, complete the missing companion choices from `references/architecture-defaults.md`.
   - Empty folder plus long-lived app/framework request: ask one concise stack question with mainstream options.
   - Mixed long-lived product types, such as official website plus admin: stop and confirm app separation before scaffolding; if the user says to decide, use the split-app defaults in `references/architecture-defaults.md`.
   - Empty folder plus simple test/demo page: take the shortest path, usually vanilla HTML/CSS/JS.
   - User says "you decide", "anything is fine", or "I don't know frontend": use the organization defaults in `references/architecture-defaults.md`.

5. Choose the correct experience mode:
   - Marketing sites optimize for desire, clarity, brand, story, conversion.
   - Admin systems optimize for speed, predictability, scanability, low cognitive load.
   - Dashboards optimize for hierarchy, anomaly detection, trend reading, live status.
   - Digital twins optimize for spatial understanding, selection, camera motion, data overlays.
   - Tool/editors optimize for continuous work, stable controls, precise feedback.
   - Developer portals optimize for readability, navigation, code clarity, trust.

6. Set motion intensity:
   - `low`: admin systems, forms, dense tables, tools during active work
   - `medium`: dashboards, docs, SaaS product UI, onboarding flows
   - `high`: marketing sites, product launches, portfolios, immersive WebGL pages
   - `situational`: digital twins use strong motion only for camera, selection, alerts, simulation

7. Apply type-specific rules from references.

8. Verify:
   - The page type is visually recognizable.
   - The layout helps the target user finish the job.
   - Motion supports comprehension or brand, not noise.
   - Text, controls, and data stay readable on desktop and mobile.
   - Reduced-motion and performance constraints are respected.

## Style System Inheritance

Before adding or modifying UI elements, identify the current style source of truth. Prefer project facts over conversation memory.

- Look for design tokens, CSS variables, Sass variables, theme providers, Tailwind config, global styles, shared components, component variants, and similar existing pages.
- New buttons, cards, forms, tables, modals, navigation items, charts, and page sections must inherit the system style by default.
- Do not introduce new radii, shadows, colors, gradients, spacing scales, typography scales, or component variants unless the existing system provides them or the user explicitly asks.
- Persist global style decisions in project files, not in memory. Future work should rediscover them from the codebase.
- If the user changes a global style token, future generated UI in that project must use the updated token rather than old visual assumptions.

When the user requests a style change, infer the intended scope:

- Global/system scope signals: `unified`, `global`, `all`, `every`, `whole project`, `system style`, `from now on`, `default`, or Chinese phrases such as `统一`, `全局`, `以后`, `所有`, `整个项目`, `系统风格`, `默认`.
- Local/custom scope signals: `this`, `here`, `current page`, `only this`, `special`, or Chinese phrases such as `这个`, `这里`, `当前页面`, `只改`, `特殊`.
- If the scope is ambiguous and the change affects tokens, shared components, or repeated UI patterns, ask whether it should be global or local before editing.

Reuse CSS deliberately:

- Put cross-page design decisions in tokens, CSS variables, theme files, or shared component variants.
- Put repeated layout and component patterns in reusable classes or components.
- Keep page-specific composition near the page or component that owns it.
- Avoid one-off hard-coded values that duplicate existing tokens.
- Avoid over-abstracting a style used only once.

## Color Token Defaults

Do not ask for a primary color unless brand fidelity is central to the request, the user asks for brand alignment, or supplied assets make the color decision ambiguous.

- If the user provides a brand color, logo, reference image, or visual direction, derive a tokenized color system from it.
- If no primary color is provided, choose a restrained product-appropriate primary color and apply it consistently through design tokens.
- The primary color should drive key interactive states: primary buttons, links, active navigation, selected tabs, focus rings, switches, checkboxes, radio controls, sliders, progress, chart emphasis, selected rows, and selected items.
- Keep neutral surfaces, text, borders, and semantic status colors distinct. Do not turn the whole interface into variations of one hue.
- Avoid disconnected accents where buttons, form focus, active navigation, charts, and selections feel like unrelated themes.
- Respect existing project tokens and design systems before introducing new color values.

## Page Intent Inference

When the user asks to add a page with broad wording, infer the frontend page pattern from keywords and project context before implementing. Do not treat broad words literally if the project context implies a common product pattern.

- Examples: `list page`, `management page`, `CRUD page`, `detail page`, `edit page`, `form page`, `settings page`, `log page`, `monitoring page`, `dashboard`, `overview`, `profile page`, `search page`.
- In existing projects, search for similar pages first. Reuse their layout, routing style, navigation placement, components, table/form patterns, state handling, mock/API conventions, naming, spacing, and visual tokens.
- If no similar page exists, use the smallest standard frontend pattern that satisfies the inferred page type. Keep it complete enough to feel usable, but do not invent business workflows.
- A broad `list page` inside an admin or product-management context usually means a management table page with filters, actions, pagination, loading, empty, error, and feedback states. It is not a bare list and not an invented domain system.
- Ask only when the missing detail blocks frontend integration quality, such as route placement, navigation grouping, or conflict with existing project conventions.
- Do not infer domain models, permission rules, approval flows, backend contracts, persistence semantics, billing logic, or authentication strategy. Use neutral mock data and frontend placeholders when business details are not provided.

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
- Do not scaffold a new mixed website/admin project before resolving the app boundary.
- Do not use big heroes, cinematic scroll, or decorative motion inside dense admin workflows.
- Do not make dashboards flash everywhere; motion should highlight change and risk.
- Use premium motion for brand and product storytelling, but use calm feedback for operational software.
- Prefer fewer, stronger ideas over many animated decorations.
- Do not create static-looking product UI for apps, admin systems, dashboards, editors, or tools. Core controls should have believable states and feedback even when using mock data.

## Repository Description Suggestion

Use this for the GitHub repository description:

`A Codex skill that helps teams build project-aware frontend experiences: premium landing pages, admin systems, dashboards, digital twins, editors, developer portals, and polished motion design.`
