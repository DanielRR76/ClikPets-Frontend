---
name: ClikPets TypeScript conventions
description: Apply strict TypeScript and type-modeling conventions to ClikPets TypeScript source files.
applyTo: "src/**/*.{ts,tsx}"
---

- Preserve the strict compiler settings in `tsconfig.app.json`; do not loosen project settings to silence local errors.
- Model actual optional and variant states with precise types, unions, and narrowing. Prefer inference for obvious local values and explicit types at public boundaries.
- Avoid `any` and assertions that bypass validation. Treat API payloads as external data rather than runtime-validated values.
- Reuse existing domain/API types when their meaning matches. Add a generic or utility type only when it removes real duplication while retaining clarity.
