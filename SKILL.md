---
name: frontend-motion-designer
description: Design polished, purposeful frontend motion for websites and apps. Use when building or improving UI animation, micro-interactions, page transitions, loading states, digital-twin dashboards, Three.js scenes, data visualization motion, hover/selection feedback, or premium interactive web effects.
---

# Frontend Motion Designer

Treat motion as product design, not decoration. Add animation only when it improves orientation, feedback, hierarchy, continuity, delight, or attention.

## Workflow

1. Identify the experience type:
   - SaaS/dashboard
   - digital twin or 3D scene
   - landing page
   - portfolio/editorial page
   - game or interactive tool
   - data visualization

2. Define the motion purpose before coding:
   - `orientation`: help users understand where they are
   - `feedback`: confirm hover, press, select, success, error
   - `hierarchy`: guide attention to what changed
   - `continuity`: connect one state/view to another
   - `delight`: add memorable polish without blocking work
   - `alert`: signal risk, alarm, abnormal state

3. Pick the lightest implementation that fits:
   - CSS transitions for hover, focus, press, opacity, transform
   - CSS keyframes for small loops, shimmer, pulse, ambient effects
   - Framework animation libraries for component/layout transitions
   - GSAP only for timeline-heavy sequences or complex orchestration
   - Three.js for spatial camera, object, shader, particle, and 3D scene motion
   - Lottie only when a prepared vector animation asset exists

4. Apply restraint:
   - Prefer `transform` and `opacity`
   - Avoid animating layout-heavy properties unless necessary
   - Keep micro-interactions around 120-250ms
   - Keep view transitions around 300-700ms
   - Use easing that feels physical; avoid linear UI motion
   - Respect `prefers-reduced-motion`

5. Verify the result:
   - No jank or long main-thread work
   - No text overlap or clipped controls
   - No constant motion competing with primary tasks
   - Mobile layout remains calm and usable
   - Animation still makes sense with reduced motion enabled

## Motion Patterns

Use `references/motion-patterns.md` when deciding what animation pattern to add.

Use `references/library-selection.md` when choosing CSS, framework animation, GSAP, Three.js, or Lottie.

Use `references/performance-checklist.md` before finalizing significant animation work.

Use `references/digital-twin-motion.md` for 3D, digital twin, industrial dashboard, alarm, camera, equipment, and spatial data-card interactions.

## Default Taste

Make interfaces feel alive, legible, and responsive. If motion only adds noise, remove it.

For operational tools, dashboards, and enterprise systems, prefer quiet confidence over spectacle. For digital twin and 3D work, reserve stronger motion for camera travel, equipment selection, alarms, data flow, and simulation states.
