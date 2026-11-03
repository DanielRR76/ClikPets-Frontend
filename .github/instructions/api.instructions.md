---
name: ClikPets API client conventions
description: Apply API boundary, environment, and request-handling conventions when changing the shared HTTP client or API types.
applyTo: "src/api/**"
---

- Preserve the shared Axios client and typed response conventions; put feature endpoint operations in their feature service.
- Treat `VITE_*` values as public because Vite includes them in client bundles. Never add secrets or credentials to frontend environment variables.
- Keep request failures aligned with the shared request handler and the UI's loading/error states. Do not infer server authorization or runtime response validation from TypeScript types.
- Consult the `clikpets-api-data-resilience` skill for feature service, query, mutation, cache invalidation, and authentication workflows.
