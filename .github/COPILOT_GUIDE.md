# GitHub Copilot Customizations

This repository has project customizations for GitHub Copilot in Visual Studio Code. The shared engineering workflows remain in `.agents/skills/`; Copilot entries under `.github/skills/` link to those canonical files so the same detailed knowledge serves Codex and Copilot.

## What loads and when

| Customization | Location | Activation |
| --- | --- | --- |
| Repository-wide instructions | `.github/copilot-instructions.md` | Automatically included for repository tasks in supported Copilot sessions. |
| Path-specific instructions | `.github/instructions/*.instructions.md` | Automatically attached when a changed/created path matches `applyTo`. |
| Skills | `.github/skills/<name>/SKILL.md` | Available to Copilot for relevant tasks or explicit invocation; each points to its canonical workflow in `.agents/skills/`. |
| Custom agents | `.github/agents/*.agent.md` | Select from the agent picker or use when delegating appropriate specialist work. Agent tool lists constrain their available tools. |
| Prompt files | `.github/prompts/*.prompt.md` | Explicit slash-command workflows in VS Code's **Local** harness only. They do not run in the GitHub Copilot harness. |

Discovery makes a skill available but does not guarantee automatic invocation. Select the relevant skill or ask Copilot to use it if a task needs that workflow.

## Instructions

The root instructions summarize stack, architecture, validation, and broad conventions. Path-specific files add only relevant details:

- React and hook guidance applies to `src/**/*.tsx`.
- Type safety guidance applies to `src/**/*.{ts,tsx}`.
- Styling guidance applies to `src/**/*.css`.
- HTTP client guidance applies to `src/api/**`.

There is no test-specific path instruction because the repository currently has no test files or runner. The `clikpets-test-strategy` skill covers test-related work and explains this constraint.

## Skills

| Skill | Use it for |
| --- | --- |
| `clikpets-architecture-review` | Cross-feature boundaries, coupling, and design trade-offs. |
| `clikpets-react-feature-development` | Components, hooks, routing, and feature state. |
| `clikpets-typescript-safety` | Types, props, API payloads, generics, and narrowing. |
| `clikpets-ui-accessibility` | CSS, responsive behavior, semantics, and accessible interactions. |
| `clikpets-api-data-resilience` | API calls, query/mutation flows, auth data, and errors. |
| `clikpets-test-strategy` | Behavior-focused test planning or implementation. |
| `clikpets-performance-audit` | Evidence-led performance investigation. |
| `clikpets-code-review` | Read-only review for actionable defects and risks. |

The Copilot skill files use a `clikpets-` prefix to avoid name collisions in VS Code Local sessions, which can discover both skill locations. They are small adapters; update the canonical `.agents/skills/<name>/SKILL.md` workflow when changing shared engineering guidance. Update the Copilot description or adapter only when its trigger or link changes.

## Custom agents and collaboration

| Agent | Responsibility | Tool boundary |
| --- | --- | --- |
| `Frontend Architect` | Architecture and module-boundary analysis. | Read, search, and agent delegation; no editing. |
| `React and TypeScript Engineer` | Feature, hooks, routing, API/query implementation. | Read, search, edit, execute, and agent delegation. |
| `UI and Accessibility Engineer` | Styling, responsive behavior, semantics, and accessible UI. | Read, search, edit, and execute. |
| `Test Engineer` | Test planning and bounded test work; performance skill when relevant. | Read, search, edit, execute, and agent delegation. |
| `Code Reviewer` | Independent review with prioritized findings. | Read/search only; no edit or execute tools. |

Delegate only when independent expertise helps. For a feature with meaningful architectural impact, have the architect assess boundaries before implementation. Use the reviewer for an independent read-only pass. Do not run multiple agents on the same files without a clear reason.

## Prompt files

Use `/implement-feature`, `/debug-issue`, or `/review-code` in a Local harness session. Prompts provide an explicit task workflow; they reference canonical skills rather than restating them. For GitHub Copilot harness sessions, use the skills and select the appropriate custom agent instead.

## Project constraints

- The project uses React 19, TypeScript 5.9, Vite 8, React Router 7, TanStack Query 5, Axios, and CSS Modules. Preserve existing feature organization and query/service patterns.
- Available checks are `npm run lint` and `npm run build`; `npm run preview` serves an existing build. There is no test script or test runner. Do not install one unless explicitly asked.
- `VITE_*` values are public client values. Frontend route guards are not an authorization boundary.
- Avoid adding dependencies, abstractions, architecture layers, or patterns without a concrete, explainable benefit.

## Maintaining the ecosystem

Keep `.github/copilot-instructions.md` and `AGENTS.md` aligned on shared project facts, without copying detailed workflows between them. Keep reusable skill bodies in `.agents/skills/` and their Copilot adapters linked. When the tool schema changes, validate agent `tools` and `skills` against the current VS Code Custom Agent File Reference. Prompt-file behavior is Local-only; retain that limitation in this guide. Verify changes in VS Code's Agent Customizations diagnostics and a fresh session with the GitHub Copilot harness.

Useful references: [VS Code custom instructions](https://code.visualstudio.com/docs/agent-customization/custom-instructions), [Agent Skills](https://code.visualstudio.com/docs/agent-customization/agent-skills), [custom agents](https://code.visualstudio.com/docs/agent-customization/custom-agents), [agent file reference](https://code.visualstudio.com/docs/agents/reference/custom-agent-file-reference), [prompt files](https://code.visualstudio.com/docs/agent-customization/prompt-files), and [GitHub Copilot instructions](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions).
