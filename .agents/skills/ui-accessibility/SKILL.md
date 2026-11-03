---
name: ui-accessibility
description: Build or audit frontend styling, responsive layouts, semantics, or interaction accessibility. Use when a task changes visible UI or reusable controls.
---

# UI, styling, and accessibility

1. Inspect the component and its stylesheet plus existing theme variables and shared UI patterns.
2. Keep one-off styles in the component CSS Module; use global styles and CSS variables only for genuinely app-wide behavior. Preserve light/dark theme support where applicable.
3. Use semantic HTML and native controls first. Ensure controls have accessible names, form fields have associated labels, images have meaningful alternatives (or empty alternatives when decorative), and interactive elements support keyboard use and visible focus.
4. Check responsive behavior, text scaling, contrast, focus, hover, disabled, loading, and error states as relevant. Do not communicate state by color alone.
5. Add ARIA only when native semantics do not express the interaction. For custom widgets, follow the relevant keyboard and state pattern in WAI-ARIA APG.
6. Report what was inspected and any checks that require a browser or assistive technology; do not claim formal conformance from source review alone.

## References

- [WCAG overview](https://www.w3.org/WAI/standards-guidelines/wcag/)
- [WAI-ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
- [React Learn](https://react.dev/learn)
