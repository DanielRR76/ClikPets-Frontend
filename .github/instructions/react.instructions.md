---
name: ClikPets React conventions
description: Apply ClikPets component, hook, routing, and state conventions when editing React TypeScript files.
applyTo: "src/**/*.tsx"
---

- Follow nearby page/component/hook conventions and keep feature behavior in `src/features/<feature>/` unless it is genuinely shared.
- Keep components focused on rendering and interaction. Extract hooks when they provide meaningful reuse or separation, not only to reduce line count.
- Keep transient UI state close to its consumer. Use TanStack Query for remote state; avoid copying query data into component state.
- Prefer derived render values over redundant state and Effects. Use Effects to synchronize with external systems.
- Preserve useful loading, empty, error, success, and disabled states. Avoid memoization without evidence of a rendering or calculation cost.
