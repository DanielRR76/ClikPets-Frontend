---
name: review-code
description: Perform a read-only review of a ClikPets change and report prioritized, actionable findings.
argument-hint: Provide a diff, PR context, or files to review.
agent: 'agent'
tools: ['read', 'search']
---

Review the supplied change without editing files.

1. Read the complete diff and enough surrounding code to verify behavior. Follow the [shared code-review workflow](../../.agents/skills/code-review/SKILL.md).
2. Report only actionable findings, ordered by severity. Include file and line, triggering scenario, impact, and a concise corrective direction.
3. Focus on defects, regressions, security/privacy, accessibility, and relevant test gaps. Avoid style-only feedback.
4. If no actionable findings exist, state that and mention validation gaps. Do not claim checks ran unless they did.
