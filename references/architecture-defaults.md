# Architecture Defaults

Use this when the user has not specified a stack, is not a frontend specialist, asks Codex to decide, or the task starts in an empty folder.

## Decision Order

1. Blocking gate first: empty folder plus official website/homepage and admin/user management/control panel must stop for app-boundary confirmation before scaffolding.
2. Runtime preflight before modern tooling: check `node -v` and the relevant package manager before scaffolding, installing dependencies, or running a dev server.
3. Existing project wins: inspect `package.json`, router, layout, state, UI library, request layer, and styling before changing code.
4. Reference folder wins when provided: mirror its stack and project conventions.
5. User-specified stack wins when compatible with the project. If the user only names a framework, complete the missing companion choices from the partial-stack rules below.
6. Empty folder plus simple test/demo page: choose the shortest path, usually vanilla HTML/CSS/JS.
7. Empty folder plus large or long-lived app: ask one concise stack question. If the user does not care, apply the defaults below.

## Runtime Preflight

- Modern frontend frameworks require Node.js to scaffold, install dependencies, and run local dev servers.
- If Node.js and a package manager are present, proceed with the chosen framework and run the project.
- If Node.js is missing, do not silently install it or continue as if the framework can run. Ask whether to install Node.js, use an available bundled/session runtime for this task, or generate a static HTML/CSS/JS demo instead.
- Treat system Node.js installation as a machine-level environment change that requires explicit user approval.
- When using a bundled/session runtime, say clearly that it helps run the current task but does not mean Node.js is installed on the user's machine.
- If the user asked for a quick visual demo and Node.js is missing, prefer offering static HTML/CSS/JS as the lowest-friction option.

Example response when Node.js is missing:

`This project would use a modern frontend toolchain, which needs Node.js to install dependencies and start the dev server. I do not see Node.js available here. Should I install Node.js for you, use a bundled runtime just for this session if available, or make a static HTML/CSS/JS demo that runs without Node?`

## User Capability

- Non-developer: ask business questions, not framework questions, unless the stack choice has long-term impact.
- Backend or partial-web developer: inspect existing architecture first; explain the chosen path briefly.
- Frontend expert: follow explicit framework, library, style, performance, and accessibility constraints.

## Team Defaults

When the user says "you decide", "anything is fine", "I don't know frontend", or otherwise does not care about the stack:

- Official website, marketing site, product site: `Nuxt + Vue3 + TypeScript + Sass` for SEO and route-level content. Add Pinia only for meaningful shared state.
- Admin system: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router`; use English UI copy by default, keep centralized theme tokens, and leave i18n/theme-switching extension points without wiring full systems unless requested.
- Dashboard or BI page: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + ECharts`; add Pinia for filters, live status, cross-panel state, or user preferences.
- WebGL, 3D, digital twin: `Vue3 + Vite + TypeScript + Sass + Babylon.js`; add Pinia for scene, selection, device, alarm, and panel state; add ECharts for operational charts.
- Workflow, EIP, visual editor: `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Pinia`; choose Vue Flow, LogicFlow, or AntV X6 by graph complexity.
- Developer portal or docs with SEO needs: prefer Nuxt; keep motion restrained and code examples readable.

All Vue3 production projects should use TypeScript and Sass. Use Tailwind CSS for admin, dashboard, workflow, and utility-heavy product UI unless the existing project uses another styling system.

## Style System Files

For new Sass-based projects, create a clear system style entry instead of scattering global visual decisions.

- Default new-project convention: `src/styles/system.scss`.
- Use `system.scss` for system-level CSS variables, Sass tokens, base surfaces, typography defaults, radius/spacing/shadow scales, semantic colors, focus rings, and shared low-level utility classes.
- Keep component-specific styles inside the component or component stylesheet.
- Keep page-specific composition styles inside the page or feature folder.
- Import `system.scss` once from the app entry or root stylesheet.
- If a project already has `tokens.scss`, `variables.scss`, `theme.scss`, `global.scss`, Tailwind config, or a UI-library theme provider, follow and extend the existing convention instead of adding `system.scss`.
- For global user requests such as "make all corners 2px" or "change the project primary color", update the system style source of truth, not isolated page styles.
- For local customization requests, use local classes or component variants without changing global tokens.

## CSS Reuse Rules

- Reuse existing tokens, utility classes, shared components, and variants before creating new CSS.
- Promote a style into `system.scss`, tokens, or a shared component only when it represents a cross-page rule or appears in repeated UI.
- Do not duplicate the same color, radius, spacing, shadow, or focus treatment across files with hard-coded values.
- Use semantic names for reusable styles, such as `--color-primary`, `--surface-muted`, `--radius-card`, `--shadow-panel`, or `panel-card`, instead of visual names tied to one screen.
- Keep CSS close to the narrowest correct owner: system tokens for global decisions, shared components for repeated behavior, pages for layout composition, and local classes for one-off exceptions.

## TypeScript Project Consistency

- For TypeScript projects, keep supported project configuration TypeScript-first: use `vite.config.ts`, typed router and store files, typed env declarations, and `.ts` utility modules.
- Do not generate `vite.config.js` for a new TypeScript Vite project unless the existing project already uses JavaScript config or the user explicitly asks for JavaScript config.
- Keep configuration, source files, and examples aligned with the selected language mode. Avoid mixing `.js` and `.ts` casually in new projects.
- If following an existing project, preserve its config style even if it differs from the defaults.
- If a tool only supports JavaScript config or the local convention is JavaScript config, use it and briefly explain the exception when relevant.

## Mixed Product Architecture

Use this when one request combines multiple product types, especially an official website plus admin, console, user management, dashboard, or control panel.

- This is a blocking decision for a new empty project. Do not run scaffold commands or create files before the user answers, unless they already said it is a demo or asked Codex to decide.
- If the user says "homepage", "official website", or "website" plus "admin", "user management", "dashboard", "console", or "control panel", treat it as this blocking case.
- Do not silently put marketing pages and admin workflows into one SPA when the project is new and long-lived.
- Ask exactly one boundary question: split into separate apps, or keep one app for a simple demo?
- If the user says to decide, create a split structure such as `apps/website` and `apps/admin`.
- `apps/website`: use the official site default, normally `Nuxt + Vue3 + TypeScript + Sass` for SEO.
- `apps/admin`: use the admin default, normally `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router`.
- Website header buttons should link to the admin app URL or route boundary; do not hide admin pages inside marketing navigation unless requested.
- If the user explicitly says it is only a quick demo, a single lightweight project with separate pages is acceptable.
- If an existing monorepo or single-app project already exists, follow it, but mention the tradeoff when marketing and admin are being mixed.

Example blocking response:

`This combines an official website and an admin user-management app. For a new project, should I split it into apps/website (Nuxt for SEO) and apps/admin (Vue3/Vite/Naive UI), or keep one lightweight app only for a demo?`

Bad response to avoid:

`This is an empty directory, so I will scaffold a lightweight Vite + Vue single-page app with / and /admin/users routes.`

## Partial Stack Completion

Use this when the user says only "use Vue", "use Vue3", "use React", "use Nuxt", or "use Next" but does not specify the rest of the stack.

- Vue3 admin: add `Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router`; default copy to English and keep theme/i18n extension points lightweight.
- Vue3 dashboard: add `Vite + TypeScript + Sass + Tailwind CSS + ECharts`; add Pinia for shared filters, live status, or drill-down state.
- Vue3 WebGL/digital twin: add `Vite + TypeScript + Sass + Babylon.js`; add Pinia for scene and equipment state.
- Vue3 workflow/editor: add `Vite + TypeScript + Sass + Tailwind CSS + Pinia`; choose Vue Flow, LogicFlow, or AntV X6 by graph complexity.
- Vue/Nuxt official site: prefer `Nuxt + Vue3 + TypeScript + Sass` for SEO. If the user explicitly says plain Vue or SPA, confirm SEO is not required before avoiding Nuxt.
- React admin: add `Vite + TypeScript + Sass + Tailwind CSS + TanStack Query + Zustand`; choose a React UI library only if the user or existing project provides one, otherwise ask once.
- React dashboard: add `Vite + TypeScript + Sass + Tailwind CSS + ECharts or Recharts + TanStack Query`; add Zustand only for cross-panel client state.
- React/Next official site: prefer `Next.js + TypeScript + Sass` for SEO, content routes, metadata, and share cards.
- React WebGL/digital twin: add `Vite or Next by app needs + TypeScript + Sass + Babylon.js`; add Zustand for scene and equipment state.

Do not add a companion library just because it is common. Add state, query, animation, chart, or WebGL libraries when the project type needs them.

## Ask-or-Decide Rules

Ask one concise question when:

- The folder is empty and the user asks for a long-lived framework, admin, official site, dashboard, or platform.
- A new request combines an official site with admin, user management, dashboard, or control panel and does not specify whether to split apps.
- The requested stack conflicts with the existing project.
- The user asks for a major architecture decision that affects future maintenance.

Do not ask when:

- The user asks for a simple test page, prototype, or quick demo.
- The existing project or reference folder clearly defines the stack.
- The user explicitly says to decide for them.
- The task is a local page/component addition inside an established project.
