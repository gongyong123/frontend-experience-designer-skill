# Admin System

Goal: help users complete repeated operational tasks quickly and accurately.

## Default Stack

- Use `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + Naive UI + Pinia + Vue Router` when the user does not care about the stack and no existing project dictates another choice.
- In an existing project, follow the current UI library, state management, request layer, and style system.
- Use Tailwind for layout utilities and spacing, Naive UI for production-grade controls, Sass for app-level styling and tokens.

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
