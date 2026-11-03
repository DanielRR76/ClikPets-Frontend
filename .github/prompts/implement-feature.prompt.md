---
name: implement-feature
description: Implement a bounded frontend feature using the repository's existing React, TypeScript, and data-flow conventions.
argument-hint: Describe the behavior and acceptance criteria.
agent: 'agent'
tools: ['read', 'search', 'edit', 'execute']
---

Implement the requested behavior in the ClikPets frontend.

1. Read the relevant feature files and [React feature workflow](../../.agents/skills/react-feature-development/SKILL.md). Read the TypeScript or API workflow too when the task crosses those concerns.
2. Confirm the expected behavior and inspect existing conventions before changing files. Ask only for missing details that block implementation.
3. Make the smallest cohesive change. Preserve feature boundaries, accessible interaction states, and existing API/query/error patterns.
4. Run relevant existing checks (`npm run lint` and/or `npm run build`). There is no configured test runner; do not add dependencies or test infrastructure unless explicitly requested.
5. Summarize changed behavior, validation performed, and any limitations.
