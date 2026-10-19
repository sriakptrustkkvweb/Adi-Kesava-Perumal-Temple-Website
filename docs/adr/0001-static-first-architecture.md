# ADR 0001: Static-first architecture for Phase 1

- **Status:** Accepted — Phase 1 architectural direction
- **Date:** 2026-10-19
- **Scope:** Phase 1 — Public Static Website

## Context and problem

The project needs an initial architecture for a public website whose Phase 1
scope is primarily informational. The project records identify low operating
cost, maintainability, simplicity, and future extensibility as goals. They
exclude a custom backend, database, authentication, and CMS from Phase 1.

The project charter establishes a public static website as the initial
release. The architecture overview describes static generation and delivery
through a suitable host as its proposed approach. These records establish the
static-first direction for Phase 1; they do not establish that the website,
build pipeline, or deployment is complete.

## Decision

Use a static-first architecture for Phase 1: generate the website during the
build and deliver generated static assets. Do not introduce a custom
application server, backend API, database, user authentication, or CMS as part
of this phase.

`Accepted` applies only to this documented Phase 1 direction. It does not mean
the architecture is fully implemented, deployed, or production-verified.
Requirements that exceed static delivery must be assessed separately before
any future scope or architecture change.

## Rationale

The initial public information site does not have a documented requirement
for user accounts, transactions, or dynamic server-side operations. Static
generation fits that scope while supporting the project's stated goals of
keeping infrastructure, operational cost, and maintenance complexity low.
It provides a simple foundation without ruling out separately reviewed
future requirements.

## Alternatives assessed for this ADR

The following options are assessed here; the project records do not establish
that they were previously compared in a formal evaluation:

- **Server-rendered application with a backend:** could support dynamic
  behavior, but adds server-side implementation and operational
  responsibilities not required by Phase 1.
- **CMS-backed website:** could provide editorial tooling, but introduces
  additional system and operational complexity beyond the documented initial
  scope.
- **Static-first delivery:** meets the documented informational scope with
  fewer runtime requirements; dynamic capabilities would require a separate
  assessment if needed later.

## Consequences and trade-offs

- The initial site can be delivered as generated static assets without a
  project-operated application server or database.
- A simpler runtime supports the project's low-cost and low-maintenance goals,
  but static delivery alone does not provide server-side transactions,
  authentication, or dynamic data processing.
- Content and pages must be prepared and built for publication; this decision
  does not provide a CMS or automated editorial approval workflow.
- Any future need for dynamic behavior must be evaluated against scope,
  security, privacy, cost, and operational responsibilities before changing
  the architecture.
- This ADR makes no hosting-provider decision.

## References

- [README — project overview and scope](../../README.md)
- [Project Management Charter — Phase 1 scope](../project-management/project-management-charter.md)
- [Architecture Overview — architectural style and constraints](../architecture/architecture-overview.md)
- [Content Architecture — implementation boundary](../architecture/content-architecture.md)
- [Source Code Structure — static-first conventions](../architecture/source-code-structure.md)
