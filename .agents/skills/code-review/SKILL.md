---
name: code-review
description: Review a change for bugs, regressions, security, or maintainability. Use for pull requests, diffs, or explicit review requests; report findings without editing.
---

# Code review

1. Read the full diff and enough surrounding code to understand the behavior and project conventions.
2. Prioritize concrete defects, regressions, security/privacy risks, missing failure states, and meaningful accessibility or test gaps. Do not report style preferences without user impact or a project rule.
3. Verify each concern against the actual code path. Label facts and uncertainty clearly; do not infer backend guarantees from frontend types.
4. Lead with findings, ordered by severity. For each, include file/line, the triggering scenario, impact, and a concise corrective direction. If no actionable findings exist, say so and mention validation gaps.
5. Keep the review read-only. Use the architecture, accessibility, API, test, or performance skill for a deeper specialist pass when the change warrants it.

## References

- [Clean Code JavaScript](https://github.com/ryanmcdermott/clean-code-javascript)
- [React reference](https://react.dev/reference/react)
- [WCAG overview](https://www.w3.org/WAI/standards-guidelines/wcag/)
