---
name: react-feature-development
description: Implement or change React components, hooks, routes, or feature state in this SPA. Use for user-facing React work and component refactors.
---

# React feature development

1. Trace the current feature page, components, hooks, services, and nearby examples before choosing where logic belongs.
2. Keep components focused on rendering and interaction; extract a hook when it gives reused or meaningfully separated stateful behavior, not just to shorten a file.
3. Colocate transient UI state. Use TanStack Query for remote data and the established auth context for cross-route identity; avoid mirroring query data in local state.
4. Preserve route and provider composition. Use React Router APIs already installed and existing route constants/helpers.
5. Handle loading, empty, error, success, and disabled states when relevant. Preserve native HTML behavior and useful keyboard interaction.
6. Avoid memoization, effects, and generalized component APIs without a specific need. Prefer derived render values over duplicated state; use effects to synchronize with external systems.
7. Validate the changed behavior with the checks available in the repository and report any test-infrastructure limitation.

## References

- [React Learn](https://react.dev/learn)
- [React reference](https://react.dev/reference/react)
- [You Might Not Need an Effect](https://react.dev/learn/you-might-not-need-an-effect)
- [React Router declarative routing](https://reactrouter.com/start/declarative/routing)
- [TanStack Query invalidation](https://tanstack.com/query/latest/docs/framework/react/guides/query-invalidation)
