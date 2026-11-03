# ClikPets Frontend

ClikPets is a React 19 and TypeScript 5.9 single-page app built with Vite 8. It uses React Router 7, TanStack Query 5, Axios, CSS Modules, and a separate backend API.

## Project structure

- `src/app/` composes the app, providers, and global styles; `src/main.tsx` is the entry point.
- `src/features/` owns auth, pets, and users workflows. Keep feature behavior with its feature.
- `src/shared/` contains reused components, hooks, types, and utilities; `src/layouts/` contains shared page structure.
- `src/api/`, `src/router/`, and `src/stores/` own the HTTP client/types, route composition, and auth context respectively.

Preserve the feature-oriented structure and existing service, hook, query wrapper, and error-handling conventions. Use TanStack Query for remote state and colocate transient UI state. Share code when it has real reuse or a stable cross-feature role; do not add architecture layers, patterns, abstractions, or dependencies without a concrete need.

TypeScript is strict. Prefer precise types and narrowing; avoid `any` and assertions used only to silence errors. Use CSS Modules for local styles and existing CSS variables/global styles for app-wide behavior. Prefer semantic HTML, native controls, accessible names and labels, keyboard support, and visible focus.

Treat `VITE_*` values as public client data. Never put secrets in the frontend, and do not treat route guards as backend authorization. Follow existing request error handling and provide useful loading and failure feedback.

Available commands: `npm run dev`, `npm run lint`, `npm run build`, `npm run preview` (after building), and the version release scripts `npm run release:patch`, `npm run release:minor`, and `npm run release:major` (only when a release is requested). There is no configured test runner or test script. Do not claim tests ran or install a runner unless test infrastructure is explicitly in scope. Run relevant existing checks and report what ran.

Read the affected feature and representative usage before changing a convention. Use the matching project skill for specialized workflows and select a custom agent only when its bounded expertise helps. See [COPILOT_GUIDE.md](./COPILOT_GUIDE.md) for customization discovery and invocation details.
