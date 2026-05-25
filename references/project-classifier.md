# Project Classifier

Classify before designing. If multiple types apply, choose the primary job-to-be-done and borrow secondary patterns carefully.

## Signals

Use `marketing-site` when the request mentions:

- official website, landing page, product page, launch, brand, campaign, conversion, hero, pricing, testimonials
- Apple-like, Stripe-like, premium, cinematic, scroll storytelling, cool website

Use `admin-system` when the request mentions:

- backend management, admin, CRUD, list/detail, table, form, permissions, roles, audit, approval, order/user/device management
- internal tool used repeatedly by operators

Use `dashboard` when the request mentions:

- dashboard, BI, metrics, monitoring, analytics, charts, KPI, command center, overview, status, trend

Use `digital-twin` when the request mentions:

- WebGL, Babylon.js, 3D, digital twin, scene, camera, equipment, model, mesh, simulation, alarm highlight, data card

Use `tool-editor` when the request mentions:

- editor, canvas, drag and drop, workflow builder, node graph, visual builder, configuration workbench

Use `developer-portal` when the request mentions:

- docs, API, SDK, developer portal, integration guide, quickstart, code examples

## Decision Output

Before making major UI choices, internally decide:

- project type
- primary user
- primary task
- user capability: non-developer, backend/partial-web developer, frontend expert
- architecture source: existing project, reference folder, user-specified stack, empty-folder default, or simple demo
- visual density: low, medium, high
- motion intensity: low, medium, high, situational
- risky patterns to avoid

## Mixed Cases

- SaaS marketing homepage: use `marketing-site`.
- SaaS logged-in product: use `admin-system` or `tool-editor`.
- Official website plus admin/user management/control panel: treat as `marketing-site + admin-system`; use `architecture-defaults.md` and confirm whether to split into separate apps.
- Monitoring console with charts and tables: use `dashboard`.
- 3D operations platform: use `digital-twin` plus `dashboard`.
- API docs with marketing hero: use `developer-portal` plus restrained `marketing-site` hero.

## Empty Folder Signals

- "simple test page", "quick demo", "try an effect", "just see it run": use the shortest path unless the user names a framework.
- "build an admin framework", "official site", "platform", "dashboard system", "digital twin system": treat as long-lived and use `architecture-defaults.md`.
- If the user is not technical, ask about business scope rather than library preference unless the architecture is genuinely undecided.
