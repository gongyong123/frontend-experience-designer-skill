# Performance Checklist

Before finishing animation work, check:

- Animate `transform` and `opacity` where possible.
- Avoid animating `width`, `height`, `top`, `left`, `margin`, or expensive filters unless there is a strong reason.
- Avoid infinite animations on many DOM nodes.
- Pause ambient animations when offscreen.
- Keep layout stable; no hover-induced reflow for toolbars, cards, tables, or grids.
- Use `prefers-reduced-motion`.
- Test desktop and mobile viewports.
- For Three.js, check frame stability, pixel rendering, asset loading, camera framing, and cleanup on unmount.
- Do not use motion to hide slow data fetching; fix loading and caching where possible.

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
