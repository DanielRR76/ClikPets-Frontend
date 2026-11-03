---
name: test-strategy
description: Plan or write automated tests for frontend behavior. Use when a task adds behavior, fixes a regression, or changes an existing test strategy.
---

# Test strategy

1. Inspect the repository before selecting a test approach. At present, `package.json` has no test script and no test runner or test files are configured.
2. If a test setup exists, test observable behavior and user interactions at the narrowest useful level; prefer integration coverage for flows crossing hooks, services, and UI.
3. Keep tests deterministic. Mock network boundaries rather than internal component details, and avoid asserting implementation-only state or call sequences without a behavioral reason.
4. Use TDD when it clarifies a regression or evolving behavior; do not require a test-first ritual for trivial edits.
5. If the needed runner is absent, report the gap. Do not install dependencies or introduce test infrastructure unless the task explicitly includes that decision.
6. Name the checks actually run and distinguish automated coverage from manual review.

## References

- [Testing Library principles](https://testing-library.com/docs/)
- [Jest getting started](https://jestjs.io/docs/getting-started)
- [Martin Fowler: Practical Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)
