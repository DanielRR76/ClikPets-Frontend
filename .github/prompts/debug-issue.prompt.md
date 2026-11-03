---
name: debug-issue
description: Trace a ClikPets bug to its cause, make a focused fix, and validate the affected behavior.
argument-hint: Describe the observed behavior and steps to reproduce.
agent: 'agent'
tools: ['read', 'search', 'edit', 'execute']
---

Investigate and fix the reported issue.

1. Read the relevant feature code and [API/data workflow](../../.agents/skills/api-data-resilience/SKILL.md) or [React workflow](../../.agents/skills/react-feature-development/SKILL.md), as appropriate.
2. Reproduce or trace the reported behavior and identify the responsible state transition or request path before editing.
3. Make the smallest change that addresses the cause; avoid unrelated cleanup.
4. Run relevant configured checks. If reproduction depends on an unavailable backend or browser, state that limitation. There is no configured test runner.
5. Report the cause, fix, validation, and any remaining uncertainty.
