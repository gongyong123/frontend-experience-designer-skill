# Digital Twin

Goal: support spatial understanding, equipment location, operational awareness, and simulation.

## Default Stack

- Default to `Vue3 + Vite + TypeScript + Sass + Babylon.js` for WebGL and digital twin work when the user does not care about the stack.
- Add Pinia for scene state, selected equipment, alarm state, camera mode, filters, and panel state.
- Add ECharts for operational charts and time-series panels.
- Follow an existing Three.js or other WebGL stack only when the project already uses it or the user explicitly requests it.

## Visual Rules

- The 3D scene or spatial model is the primary surface.
- UI panels should support the scene, not cover it.
- Keep equipment identity, status, and location readable.
- Use overlays, cards, and legends sparingly.

## Motion Rules

- Motion intensity is situational.
- Strong motion is appropriate for camera fly-to, equipment selection, alerts, data flow, simulation.
- Weak motion is better for panels, filters, and repeated operations.
- Camera moves should ease to a stable inspection angle.
- Selection should persist after the animation.

## Good Patterns

- Device selected: camera ease + outline/glow + data card reveal.
- Alarm: amber/red pulse, then steady acknowledged state.
- Data flow: directional line or particles for power, cooling, water, network.
- Simulation: animated field overlay with legend.
- 3D card: fade/scale in and follow projected position.

## Avoid

- 3D as decoration only.
- Constant camera movement.
- Cards covering the selected model.
- Fast flashing alarms.
- Heavy scene effects without performance fallback.
