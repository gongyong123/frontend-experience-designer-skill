# Motion Patterns

## Entrance

Use entrance motion to stage information, not to delay access.

- Fade and translate content 8-24px.
- Stagger repeated items by 30-70ms.
- Avoid every section entering from a different direction.
- Keep dashboards mostly immediate; animate changed data, not the whole page.

## Hover And Press

Use hover/press motion to show affordance.

- Buttons: slight translateY, shadow, background, icon movement.
- Cards: subtle border, shadow, image scale, or action reveal.
- Toolbars: icon button feedback should be quick and stable.
- Do not resize controls on hover if it shifts layout.

## Selection And Focus

Use selection motion to confirm target identity.

- Add ring, outline, glow, pulse, or camera focus.
- Keep selected state persistent after the motion ends.
- For 3D equipment, combine highlight + camera easing + optional data-card reveal.

## Loading

Use loading motion to communicate progress or skeleton state.

- Skeleton shimmer for unknown content.
- Determinate progress when real progress exists.
- Avoid fake complex loaders for fast operations.
- Use reduced-motion-friendly opacity changes as fallback.

## Transitions

Use transitions to preserve continuity between states.

- Panels: fade + slide from the direction of navigation.
- Modals: scale 0.98 to 1 + fade.
- Tabs: animate indicator and content opacity.
- Routes: keep transitions short; avoid blocking first meaningful content.

## Ambient

Use ambient motion sparingly.

- Good: slow data flow, subtle grid scan, tiny particle drift, gentle 3D camera idle.
- Bad: background motion that fights reading or interaction.
- Stop or reduce ambient motion when a modal, editor, or dense table is active.
