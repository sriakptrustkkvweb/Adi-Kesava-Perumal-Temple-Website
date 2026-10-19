# ADR 0002: Astro and TypeScript technology stack

- **Status:** Proposed
- **Date:** 2026-10-19
- **Scope:** Phase 1 — Public Static Website

## Context and problem

The project needs a maintainable implementation direction for its Phase 1
static website. The README, project charter, and architecture overview list
Astro and TypeScript as the planned framework and language. The repository
contains an Astro dependency in `package.json`, an `astro.config.mjs`, a
`tsconfig.json` extending Astro's strict configuration, and an Astro page at
`src/pages/index.astro`.

This is evidence of an initial Astro scaffold and TypeScript configuration,
not evidence that the complete application or a formal technology decision
has been accepted. The project charter describes these choices as planned.

## Decision

Propose Astro with TypeScript as the Phase 1 website stack. Keep this status
`Proposed` unless project records or an explicit maintainer decision establish
formal acceptance. Existing scaffold files do not change that status.

## Rationale

The architecture overview proposes Astro for static page generation with
limited unnecessary client-side JavaScript and TypeScript to improve code
clarity and catch common development errors. This direction is consistent
with the static-first Phase 1 scope and the documented preference for a
simple, maintainable implementation.

## Alternatives assessed for this ADR

The following options are assessed for this record; there is no claim that
project contributors previously evaluated them:

- **Plain HTML and CSS without a framework:** could minimize framework
  conventions, but may require more manual organization as pages and shared
  presentation grow.
- **Another static-site framework:** could also generate static pages, but
  would differ in conventions, capabilities, and contributor workflow. No
  specific alternative is selected by the existing project records.
- **Astro with TypeScript:** follows the documented planned direction and
  current scaffold, while committing the project to Astro conventions and
  its associated build tooling if later accepted.

## Consequences and trade-offs

- If accepted, Astro's static generation and file-based conventions provide
  the implementation basis described by the architecture documents.
- TypeScript's types can improve clarity and catch some development errors,
  but require contributors to work with TypeScript conventions.
- The current repository evidence is limited to the initial Astro package,
  configuration, TypeScript configuration, and an Astro page; it does not
  establish the completion or verification of the full site.
- This ADR does not approve additional dependencies or change the current
  scaffold.
- Until formally accepted, the documented stack remains a proposal subject to
  project review.

## References

- [README — technology direction](../../README.md)
- [Project Management Charter — technology and architecture direction](../project-management/project-management-charter.md)
- [Architecture Overview — proposed technology stack](../architecture/architecture-overview.md)
- [Source Code Structure — intended Astro organization](../architecture/source-code-structure.md)
