# Performance Checklist

Use this before finalizing any meaningful frontend motion work.

## Universal Checks

- Text remains readable before, during, and after motion.
- No hover, reveal, image, or route transition causes layout shift.
- Animate `transform` and `opacity` where possible.
- Avoid expensive blur/filter animation over large areas.
- Respect `prefers-reduced-motion`.
- Test desktop and mobile.
- No interaction is blocked by decorative animation.

## Project-Specific Checks

Marketing site:

- First viewport renders quickly.
- Hero media has a fallback.
- Scroll storytelling does not trap normal scrolling.

Admin system:

- Tables, filters, and forms remain stable.
- Repeated actions feel faster, not slower.
- Loading, empty, error, and disabled states are explicit.

Dashboard:

- KPI and chart values are readable without waiting for animation.
- Alerts are noticeable but not overwhelming.
- Live animations do not obscure trend reading.

Digital twin:

- Canvas/WebGL scene is nonblank and framed correctly.
- Camera motion ends in a stable inspection angle.
- Overlays do not hide the target.
- Heavy effects clean up when leaving the scene.

Tool/editor:

- Toolbars and controls do not move unexpectedly.
- Drag/resize/select feedback is precise.
- Motion never reduces manipulation accuracy.

Reduced motion CSS pattern:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
```
