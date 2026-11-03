# Codex Engineering Ecosystem

This guide describes the project-level Codex guidance in `AGENTS.md`, reusable workflows in `.agents/skills/`, and specialist agents in `.codex/agents/`. The system is intentionally small and follows the current React/TypeScript implementation rather than imposing a new application architecture.

## How to use it

Codex reads the root `AGENTS.md` as general repository guidance. Skills are selected when their short descriptions match a task or when explicitly invoked; they provide repeatable workflows and relevant references. Custom agents define bounded roles for delegated work. Use a skill directly for a focused task; delegate when work is independent and benefits from a separate specialist perspective.

Give an agent a specific area, expected output, and boundary. For example, ask the architect to assess a feature boundary, then ask the React/TypeScript engineer to implement the agreed change, and ask the quality engineer for a read-only review. Avoid parallel agents editing the same files.

## Skills

| Skill | Use it for |
| --- | --- |
| `architecture-review` | Cross-feature boundaries, coupling, and architecture trade-offs. |
| `react-feature-development` | React components, hooks, route behavior, and feature state. |
| `typescript-safety` | Domain/API types, component props, generics, and unsafe typing. |
| `ui-accessibility` | CSS Modules, responsive behavior, semantic UI, and accessible interactions. |
| `api-data-resilience` | Axios services, TanStack Query flows, auth data, and request errors. |
| `test-strategy` | Test planning or implementation when behavior changes or regresses. |
| `performance-audit` | Evidence-led investigation of load, rendering, assets, and bundle behavior. |
| `code-review` | Read-only review of a diff for actionable defects and risks. |

Each `SKILL.md` contains the workflow and links to relevant references. Add a reference file only when it materially improves the workflow or would otherwise make the skill difficult to scan.

## Custom agents

| Agent | Responsibility and boundary |
| --- | --- |
| `frontend_architect` | Makes evidence-based module and design recommendations; avoids prescribing layers or DDD by default. |
| `react_typescript_engineer` | Implements React feature behavior, hooks, query flows, routing, and precise TypeScript. |
| `ui_accessibility_engineer` | Owns presentation, CSS, responsive behavior, semantics, and accessible interactions. |
| `quality_engineer` | Performs independent reviews and test, security, and performance analysis; reports evidence and limits. |

Agents point to skills rather than restating their complete workflows. They should consult another agent when a task crosses a stated boundary and return concise findings with relevant file paths, trade-offs, and validation performed.

## Project standards

- Preserve the current feature-oriented organization (`auth`, `pets`, `users`) and shared responsibilities under `src/`. Put feature-specific behavior with its feature; share only stable or genuinely reused code.
- Keep remote data in TanStack Query and UI state near its consumer. Use current services, query/mutation wrappers, request error handling, CSS Modules, theme variables, and React Router patterns unless the task calls for a change.
- Maintain strict TypeScript. Model external data and optional states accurately; avoid `any` and assertions that merely silence errors.
- Prefer semantic HTML, native controls, accessible labels and alternatives, keyboard support, visible focus, and responsive layouts. Use ARIA only when native HTML does not provide the needed semantics.
- Treat `VITE_*` variables as public client values. Do not put secrets in the frontend or treat client-side route checks as authorization.
- Apply Clean Code, SOLID, DDD, and design patterns as tools for observed complexity, not as checklists. Avoid additional dependencies and abstractions without a specific benefit.

## Validation and known limits

The available project checks are `npm run lint` and `npm run build`. There is currently no test script, test runner, or test suite configured. When asked to add tests, first state this constraint; do not install a runner or change package configuration unless that work is explicitly in scope. Prefer behavior-level tests when a test harness exists. For performance work, establish a reproducible baseline before claiming an improvement. Report exactly which checks ran and any browser, assistive technology, or measurement limits.

## Maintaining this ecosystem

When the stack, scripts, or module structure change, update `AGENTS.md` and this guide. Update skill references if a dependency version or API changes. Add a new skill only for a distinct repeatable workflow; add an agent only when it has an ongoing responsibility that cannot be expressed more simply through an existing agent and skill. Keep skill descriptions short and precise so Codex can select them reliably. Periodically check for duplicate or stale guidance and remove it.

## External references

- [React Learn](https://react.dev/learn) and [React API reference](https://react.dev/reference/react)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/) — [generics](https://www.typescriptlang.org/docs/handbook/2/generics.html) and [utility types](https://www.typescriptlang.org/docs/handbook/utility-types.html)
- [React Router declarative routing](https://reactrouter.com/start/declarative/routing)
- [TanStack Query invalidation](https://tanstack.com/query/latest/docs/framework/react/guides/query-invalidation)
- [Vite environment variables](https://v8.vite.dev/guide/env-and-mode) and [Axios error handling](https://axios-http.com/docs/handling_errors)
- [Testing Library principles](https://testing-library.com/docs/) and [Fowler's practical test pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)
- [Web Vitals](https://web.dev/articles/vitals) and [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/)
- [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/) and [WAI-ARIA APG](https://www.w3.org/WAI/ARIA/apg/)
- [Clean Code JavaScript](https://github.com/ryanmcdermott/clean-code-javascript), [Refactoring.Guru patterns](https://refactoring.guru/design-patterns), and [Fowler on DDD](https://martinfowler.com/bliki/DomainDrivenDesign.html)
- [Codex skills](https://learn.chatgpt.com/docs/build-skills) and [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents)
