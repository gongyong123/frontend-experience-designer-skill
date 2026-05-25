# Digital Twin

Goal: support spatial understanding, equipment location, operational awareness, and simulation.

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
