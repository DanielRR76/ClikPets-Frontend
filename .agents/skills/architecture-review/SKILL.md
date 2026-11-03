---
name: architecture-review
description: Assess frontend boundaries, coupling, or design trade-offs. Use when a change affects multiple modules or proposes architectural patterns or layers.
---

# Architecture review

1. Trace the affected behavior through the existing app, feature, shared, API, routing, and state boundaries. Cite the files that establish each observed convention.
2. Separate observed facts, inferred risks, and recommendations. Identify the smallest boundary that owns the behavior.
3. Evaluate coupling, cohesion, dependency direction, and whether the change belongs in a feature or shared module.
4. Recommend Clean Architecture, DDD, dependency injection, or a design pattern only when a concrete complexity or change pressure justifies its cost. Prefer the existing feature-oriented structure for ordinary UI workflows.
5. Present trade-offs, compatibility concerns, and a small set of decision-ready options. Do not turn a review into an unrequested rewrite.

## Project context

This is a modest React SPA with auth, pets, and users as feature areas. It has service and hook conventions but no separate domain layer. Model domain rules where useful; do not introduce entities/use-cases/repositories as mandatory ceremony.

## References

- [Martin Fowler: Domain-Driven Design](https://martinfowler.com/bliki/DomainDrivenDesign.html)
- [Refactoring.Guru: design patterns](https://refactoring.guru/design-patterns)
- [Clean Code JavaScript](https://github.com/ryanmcdermott/clean-code-javascript)
