---
name: performance-audit
description: Investigate a frontend performance concern or requested optimization. Use when measuring load, interaction, rendering, assets, or bundle behavior.
---

# Performance audit

1. Define the affected user journey and obtain a reproducible baseline before recommending code changes.
2. Separate field data from lab measurements. Use Core Web Vitals for user experience and Lighthouse or browser tooling to investigate a concrete issue.
3. Inspect the relevant network requests, images/assets, build output, and React rendering path. Identify the measured bottleneck before choosing an optimization.
4. Prefer the smallest change with a plausible measurable benefit. Consider code splitting or lazy loading only where route/asset loading warrants it; avoid memoization and caching policies without evidence.
5. State the measurement conditions, before/after evidence, and trade-offs. If no measurement tooling or representative data is available, present that as a limitation rather than claiming an improvement.

## References

- [Web Vitals](https://web.dev/articles/vitals)
- [Lighthouse overview](https://developer.chrome.com/docs/lighthouse/overview/)
- [React reference](https://react.dev/reference/react)
