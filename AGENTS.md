# ClikPets Frontend

## Project

ClikPets is a browser-based pet adoption SPA built with React 19, TypeScript 5.9, Vite 8, React Router 7, TanStack Query 5, Axios, and CSS Modules. The backend is a separate service.

## Structure and boundaries

- `src/app/` composes the application, providers, and global styles.
- `src/features/` owns authentication, pet, and user workflows, including pages, hooks, services, types, and constants.
- `src/shared/` contains UI and utilities reused across features; `src/layouts/` contains shared page structure.
- `src/api/` owns the HTTP client and response types; `src/router/` owns routes and navigation; `src/stores/` currently owns authentication context.
- Routing uses React Router's browser router and route constants; `AuthGuard` protects authenticated routes. Auth context derives its user state from TanStack Query.
- Keep feature-specific behavior with its feature. Share code when there is an actual reuse or a stable cross-feature responsibility. Preserve the current direction and introduce layers only to solve a demonstrated coupling or complexity problem.

## Conventions

- Follow existing TypeScript, React, import-alias, and file naming patterns. TypeScript is strict; prefer inferred and precise types, avoid `any`, and justify assertions.
- Use CSS Modules for component styles and the existing global CSS variables/utilities for app-wide styling. Keep responsive behavior and accessible semantics in the component's design.
- Keep server state in TanStack Query and UI state near its consumer unless a real cross-feature need justifies sharing it. Use the existing API services, request handling, and query/mutation wrappers unless the task requires changing those boundaries.
- Treat all `VITE_*` values as public client data. Do not place secrets in frontend environment variables; authorization remains a backend responsibility.
- Do not add dependencies, architectural layers, design patterns, or abstractions without a concrete need and a clear benefit.

## Workflow and validation

- Read the relevant feature, shared implementation, and existing usage before changing a convention.
- Available scripts: `npm run prepare` initializes Husky; `npm run dev` starts Vite; `npm run lint` and `npm run build` check the project; `npm run preview` serves an existing build; and `npm run release:patch`, `npm run release:minor`, and `npm run release:major` create version releases (run only when requested). There is currently no test script or test framework; do not claim tests ran when none are configured. If a task needs tests, describe this limitation and follow the `test-strategy` skill.
- Run checks that are relevant to the requested change and report what ran and any limitations. Do not install dependencies or change package configuration unless the task explicitly includes that work.

## Skills and agents

- Use a project skill for its named workflow; skill descriptions define when they apply. See `docs/codex-engineering-ecosystem.md` for the catalog.
- Delegate only independent specialist work that benefits from a separate review. Give each agent a bounded task and combine findings before editing shared files. The custom agents complement skills; they do not replace reading the affected code.
