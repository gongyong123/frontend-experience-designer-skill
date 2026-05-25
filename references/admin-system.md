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
