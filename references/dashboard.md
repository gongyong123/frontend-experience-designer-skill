# Dashboard

Goal: make status, trends, and anomalies easy to scan.

## Default Stack

- Use `Vue3 + Vite + TypeScript + Sass + Tailwind CSS + ECharts` when no existing project dictates another choice.
- Add Pinia for shared filters, live data status, cross-panel selections, user preferences, or drill-down state.
- If the dashboard is part of an admin system, follow the admin system stack and use Naive UI for controls.

## Visual Rules

- Establish clear KPI hierarchy.
- Group related metrics.
- Use charts for comparison, trend, distribution, and composition.
- Make alerts visually distinct but not overwhelming.
- Keep legends and units visible.

## Motion Rules

- Motion intensity should be medium.
- Use count-up only where it helps indicate refreshed data.
- Use chart draw-in or transition only for changed data.
- Use pulsing or blinking sparingly for warnings and critical alerts.
- Use smooth crossfades for time range and filter changes.

## Good Patterns

- KPI cards with clear deltas.
- Chart transitions tied to filter changes.
- Live status indicators.
- Alert rows or markers with priority color.
- Drill-down panel transitions.

## Avoid

- Every number rolling constantly.
- All charts animating at once.
- Decorative grid backgrounds that reduce readability.
- Alarm colors everywhere.
- Dense data without visual hierarchy.
