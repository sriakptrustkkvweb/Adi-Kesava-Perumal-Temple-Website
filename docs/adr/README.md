# Architecture Decision Records

This directory records significant architectural decisions for the Sri Adi
Kesava Perumal Temple website. ADRs explain why a direction was chosen, the
alternatives assessed for the record, and the resulting trade-offs. The
architecture documents describe how the system is organized.

## Status meanings

- **Proposed** — documented as a candidate or recommendation, but not
  established by project records as formally accepted.
- **Accepted** — approved for the stated scope. This status does not mean the
  decision has been implemented, tested, or verified in production.
- **Superseded** — replaced by a later decision. Link to the replacing ADR.
- **Withdrawn** — no longer being considered. Explain why in the ADR.

Use `Proposed` unless existing project records or an explicit project
maintainer approval support `Accepted`. A repository scaffold or planned
technology listing alone does not establish that a decision has been formally
accepted.

## Creating or updating an ADR

1. Copy the [ADR template](./0000-adr-template.md).
2. Assign the next four-digit number and a concise kebab-case filename.
3. Record the scope, status, context, decision, rationale, alternatives, and
   consequences or trade-offs.
4. Link relevant project records using paths relative to the ADR.
5. Distinguish documented facts from analysis newly performed in the ADR.
   Do not present newly assessed alternatives as historical evaluations.
6. Update the status and date when an authorized decision is made. Preserve
   superseded records and link the replacement rather than silently rewriting
   the decision history.

## Initial decisions

| ADR | Title | Status |
|---|---|---|
| [0001](./0001-static-first-architecture.md) | Static-first architecture for Phase 1 | Accepted for Phase 1 direction; implementation is not thereby complete |
| [0002](./0002-astro-typescript-technology-stack.md) | Astro and TypeScript technology stack | Proposed |
| [0003](./0003-initial-hosting-strategy.md) | Candidate initial static hosting strategy | Proposed |
