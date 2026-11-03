---
name: api-data-resilience
description: Add or change API calls, query/mutation flows, authentication data, or request failure handling. Use when frontend behavior depends on remote data.
---

# API and data resilience

1. Trace the feature hook to its service, shared Axios client, response type, and UI request state. Follow existing feature-owned service conventions.
2. Keep request and response types honest; do not assume server data is validated merely because it has a TypeScript annotation.
3. Use TanStack Query for remote state. Make query keys identify the requested data and invalidate or update the affected cache after mutations.
4. Preserve the shared request error behavior and show actionable loading/error feedback. Treat unauthorized responses consistently with the existing auth flow without making the UI an authorization boundary.
5. Avoid logging credentials or personal data. Treat `VITE_*` values as public because Vite embeds them in client bundles; never put secrets there.
6. Do not add retries, caching policies, optimistic updates, or shared abstractions without a reliability or UX reason. Check cancellation and stale-result behavior when requests can overlap.

## References

- [TanStack Query: Query Invalidation](https://tanstack.com/query/latest/docs/framework/react/guides/query-invalidation)
- [Vite: Env Variables and Modes](https://v8.vite.dev/guide/env-and-mode)
- [Axios: Handling Errors](https://axios-http.com/docs/handling_errors)
