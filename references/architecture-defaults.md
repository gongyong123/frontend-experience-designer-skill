# Architecture Defaults

Use this when the user has not specified a stack, is not a frontend specialist, asks Codex to decide, or the task starts in an empty folder.

## Decision Order

1. Existing project wins: inspect `package.json`, router, layout, state, UI library, request layer, and styling before changing code.
2. Reference folder wins when provided: mirror its stack and project conventions.
3. User-specified stack wins when compatible with the project.
4. Empty folder plus simple test/demo page: choose the shortest path, usually vanilla HTML/CSS/JS.
5. Empty folder plus large or long-lived app: ask one concise stack question. If the user does not care, apply the defaults below.

## User Capability

- Non-developer: ask business questions, not framework questions, unless the stack choice has long-term impact.
- Backend or partial-web developer: inspect existing architecture first; explain the chosen path briefly.
- Frontend expert: follow explicit framework, library, style, performance, and accessibility constraints.

## Team Defaults

When the user says "you decide", "anything is fine", "I don't know frontend", or otherwise does not care about the stack:

- Official website, marketing site, product site: `Nuxt + Vue3 + TypeScript + Sass` for SEO and route-level content. Add Pinia only for meaningful shared state.
- Admin system: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router`.
- Dashboard or BI page: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + ECharts`; add Pinia for filters, live status, cross-panel state, or user preferences.
- WebGL, 3D, digital twin: `Vue3 + Vite + TypeScript + Sass + Babylon.js`; add Pinia for scene, selection, device, alarm, and panel state; add ECharts for operational charts.
- Workflow, EIP, visual editor: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Pinia`; choose Vue Flow, LogicFlow, or AntV X6 by graph complexity.
- Developer portal or docs with SEO needs: prefer Nuxt; keep motion restrained and code examples readable.

All Vue3 production projects should use TypeScript and Sass. Use Tailwind CSS for admin, dashboard, workflow, and utility-heavy product UI unless the existing project uses another styling system.

## Ask-or-Decide Rules

Ask one concise question when:

- The folder is empty and the user asks for a long-lived framework, admin, official site, dashboard, or platform.
- The requested stack conflicts with the existing project.
- The user asks for a major architecture decision that affects future maintenance.

Do not ask when:

- The user asks for a simple test page, prototype, or quick demo.
- The existing project or reference folder clearly defines the stack.
- The user explicitly says to decide for them.
- The task is a local page/component addition inside an established project.
