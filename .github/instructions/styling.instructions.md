---
name: ClikPets styling and accessibility
description: Apply ClikPets CSS Modules, theme, responsive, and accessibility conventions to stylesheet changes.
applyTo: "src/**/*.css"
---

- Keep component-specific rules in that component's CSS Module. Use global styles and existing CSS variables for app-wide behavior.
- Preserve the light/dark theme conventions where relevant; avoid introducing a second styling system.
- Check responsive layouts, text scaling, contrast, visible focus, and interaction states relevant to the change.
- Do not communicate state through color alone. Prefer semantic markup and native controls; keep ARIA for cases native HTML cannot express.
