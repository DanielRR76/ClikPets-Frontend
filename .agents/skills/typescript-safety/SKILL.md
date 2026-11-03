---
name: typescript-safety
description: Design or review TypeScript types, component props, API payloads, or generic helpers. Use when a change affects type safety or inference.
---

# TypeScript safety

1. Read the relevant domain types and call sites; model the actual input, output, and optional states.
2. Preserve the strict compiler settings. Prefer inference for obvious local values and explicit types at public boundaries.
3. Use unions and narrowing for distinct states. Use generics when a function genuinely preserves a relationship between input and output; constrain them only as needed.
4. Prefer `unknown` plus narrowing over `any`. Avoid assertions that only silence a compiler error; validate external data at runtime when the boundary requires it.
5. Reuse existing API and domain types where their meaning matches. Avoid duplicating types or creating broad utility types for one call site.
6. Keep React props aligned with native element props when wrapping an element, and preserve meaningful event and ref types.
7. Check the affected code with the configured lint/build commands when relevant; do not loosen compiler settings to accommodate a local mismatch.

## References

- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html)
