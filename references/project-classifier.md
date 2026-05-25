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

- Three.js, 3D, digital twin, scene, camera, equipment, model, mesh, simulation, alarm highlight, data card

Use `tool-editor` when the request mentions:

- editor, canvas, drag and drop, workflow builder, node graph, visual builder, configuration workbench

Use `developer-portal` when the request mentions:

- docs, API, SDK, developer portal, integration guide, quickstart, code examples

## Decision Output

Before making major UI choices, internally decide:

- project type
- primary user
- primary task
- visual density: low, medium, high
- motion intensity: low, medium, high, situational
- risky patterns to avoid

## Mixed Cases

- SaaS marketing homepage: use `marketing-site`.
- SaaS logged-in product: use `admin-system` or `tool-editor`.
- Monitoring console with charts and tables: use `dashboard`.
- 3D operations platform: use `digital-twin` plus `dashboard`.
- API docs with marketing hero: use `developer-portal` plus restrained `marketing-site` hero.
