# Admin System

Goal: help users complete repeated operational tasks quickly and accurately.

## Default Stack

- Use `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router` when the user does not care about the stack and no existing project dictates another choice.
- In an existing project, follow the current UI library, state management, request layer, and style system.
- Use Tailwind for layout utilities and spacing, Naive UI for production-grade controls, Sass for app-level styling and tokens.

## Product Defaults

- Use a unified theme foundation: shared color tokens, typography, spacing, border radius, shadows, component density, and state colors.
- If the user does not explicitly request multilingual content, write UI copy in English by default.
- Leave an i18n extension point, such as centralized copy keys or a locale-ready structure, but do not install or wire a full i18n system by default.
- Leave theme switching extension points, such as CSS variables, theme tokens, and a theme store shape, but do not build a full skin marketplace unless requested.
- Keep future UI designer rules easy to apply by avoiding hard-coded one-off visual values scattered across pages.

## Visual Rules

- Use dense but organized information.
- Prioritize tables, filters, tabs, sidebars, forms, batch actions, and clear state.
- Keep navigation stable and predictable.
- Use compact typography and consistent spacing.
- Cards are for repeated items or panels, not decorative page sections.
- Admin systems must look like modern operational software, not legacy admin templates.
- Do not default to black or near-black sidebars. Use light, softly tinted, or restrained branded navigation surfaces unless the user requests a dark console theme.
- Avoid old admin-template composition: dark sidebar, flat gray page background, disconnected white cards, oversized headings, sparse dashboard layouts, and generic blue accents.
- Use a cohesive app shell with tokenized color, active navigation states, clear page hierarchy, polished table/form states, and subtle branded surfaces.
- Use the primary color consistently for intent and selection: primary actions, active menu items, tabs, focus rings, selected rows, switches, and key chart emphasis.
- White cards are acceptable only when they sit in a coherent surface system with deliberate borders, subtle elevation, consistent radii, and meaningful internal hierarchy.
- Prefer borders and soft tonal surfaces over heavy shadows. Keep card radius at 6-8px unless the existing design system says otherwise.

## Modern Admin Baseline

When no brand system is provided, choose a restrained product-appropriate palette instead of a black/white/gray template.

- Common shell structure: `AppShell`, `Sidebar`, `Topbar`, `PageHeader`, `Toolbar`, `MetricCard`, `DataPanel`, `ChartPanel`, `DataTable`, `EmptyState`, and feedback/toast primitives.
- Default surfaces should feel connected: page background, sidebar, topbar, cards, borders, and selected states should come from one token system.
- Use light or softly tinted navigation by default. Dark navigation is reserved for explicit dark-console requests or existing project conventions.
- Keep dashboards work-focused: compact KPI cards, chart panels, recent activity, alerts, and tables should create a useful first screen without hero-style spacing.
- Keep typography practical: page titles are clear but not oversized; card headings and table labels stay compact.
- Give tables and forms complete visual states: hover, selected, focused, disabled, loading, empty, error, success, and pagination where relevant.
- If the first rendered screen reads as "black sidebar + gray background + white cards", revise the palette and shell before finishing.

## Motion Rules

- Motion intensity should be low.
- Use fast feedback: hover, active, selection, loading, drawer/modal open, row expansion.
- Typical duration: 120-220ms.
- Use skeletons, inline spinners, optimistic feedback, and clear disabled states.
- Keep layout stable; hover must not shift table columns or toolbar positions.

## Good Patterns

- Filter bar with clear active chips.
- Table rows with subtle hover and selected state.
- Modal/drawer fade + slight scale or slide.
- Form validation with clear inline messages.
- Empty state with one primary action.

## Avoid

- Big marketing heroes.
- Scroll storytelling.
- Decorative parallax.
- Large animated backgrounds.
- Motion that slows repeated work.
- Near-black default sidebars without a deliberate dark theme.
- Flat gray pages filled with isolated white cards.
- Generic blue buttons that are disconnected from the rest of the theme.
- Oversized dashboard headings or card spacing that makes operational views feel empty.
