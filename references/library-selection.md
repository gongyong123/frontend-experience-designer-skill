# Library Selection

Choose the lightest implementation that satisfies the project type and motion purpose.

## CSS

Use CSS for:

- hover, focus, press, disabled states
- opacity, transform, clip-path, mask transitions
- skeletons, shimmer, pulse, simple loops
- admin and dashboard UI feedback
- reduced-motion fallbacks

CSS should be the default for ordinary UI motion.

## Small JavaScript

Use small JS for:

- intersection-triggered section reveals
- scroll progress variables
- cursor-following highlights
- count-up values
- canvas ambient details
- coordinating state-based UI transitions

Avoid layout thrashing. Read layout once, write styles separately when possible.

## Existing Framework Animation

Use the app's existing framework animation library when present.

Good for:

- route transitions
- component enter/exit
- layout transitions
- shared element transitions
- drawers, modals, tabs, accordions

Do not add a new dependency for simple hover or fade effects.

## GSAP

Use GSAP when the experience needs:

- pinned scroll storytelling
- complex timelines
- product choreography across many elements
- SVG path drawing or mask sequencing
- precise scroll-linked animation

Good fit for marketing sites and immersive product pages. Usually too heavy for admin systems.

## Three.js / WebGL

Use Three.js/WebGL when:

- the product is spatial or 3D
- digital twin scenes need camera/equipment/simulation motion
- hardware/product showcases need 3D rotation or material lighting
- shader/canvas effects are core to the story

Do not use WebGL only as decoration when CSS, video, or imagery would communicate better.

## Video / Canvas

Use video/canvas for:

- cinematic product hero media
- complex background motion that would be expensive in DOM
- generated visual fields, particles, flows, or simulations

Always provide a still or reduced-motion fallback.
