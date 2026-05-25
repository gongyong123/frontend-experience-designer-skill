# Marketing Site

Goal: create desire, communicate value quickly, and make the product memorable.

## Default Stack

- For official websites, marketing sites, and product sites that may need SEO, default to `Nuxt + Vue3 + TypeScript + Sass` when the user does not care about the stack.
- Add Pinia only when shared state is meaningful, such as user/session state, personalization, configurators, or multi-step flows.
- For a simple one-off test page, use the shortest path instead of scaffolding a full Nuxt app.

## Visual Rules

- Use a strong first viewport: product, brand, or offer must be immediately visible.
- Favor large typography, confident spacing, and high-quality media.
- Build fewer sections with stronger composition.
- Use product screenshots, videos, 3D objects, or generated/real imagery instead of generic cards.
- Make the H1 literal and memorable; supporting copy carries explanation.

## Motion Rules

- Motion intensity can be medium to high.
- Use hero reveal, product choreography, scroll storytelling, parallax, mask reveals, and premium hover.
- Text motion should be elegant and readable: line reveal, word group reveal, fade/slide, clip mask.
- Product/media motion can be more cinematic: scale, rotate, depth, light sweep, crossfade states.
- Avoid making every section enter the same way.

## Good Patterns

- Product-first hero with text over or around high-quality media.
- Pinned visual with changing copy chapters.
- Before/after or state transformation.
- Feature sections where each section has one visual idea.
- CTA that feels tactile but not loud.

## Avoid

- Admin-style tables and dense filters.
- Floating card soup.
- Random blobs, orbs, and generic gradients.
- Long delays before content is readable.
- Copying a specific brand exactly.
