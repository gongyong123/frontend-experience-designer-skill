# Library Selection

## CSS

Use CSS transitions/keyframes for:

- hover, focus, active, disabled states
- opacity and transform changes
- small pulses, shimmers, loops
- simple responsive UI motion

Prefer CSS when the animation does not need timeline control, physics, layout measurement, or complex sequencing.

## Framework Animation Libraries

Use the app's existing animation library if one is already present.

Use component animation for:

- route and panel transitions
- enter/exit animation
- layout transitions
- disclosure, accordion, modal, drawer behavior

Do not add a new animation dependency for a single hover effect.

## GSAP

Use GSAP for:

- timeline-heavy sequences
- scroll-triggered storytelling
- coordinating many elements
- SVG path drawing or complex transforms

Avoid GSAP for ordinary UI feedback in enterprise apps.

## Three.js

Use Three.js motion for:

- camera fly-to and orbit transitions
- model highlight, pulse, blink, dissolve
- particles, flow lines, field visualization
- shader-driven data states
- simulation visualization

Always verify the canvas is nonblank, framed correctly, responsive, and performant.

## Lottie

Use Lottie only when a prepared `.json` animation asset exists and matches the brand/style. Do not invent Lottie where CSS or SVG would be simpler.
