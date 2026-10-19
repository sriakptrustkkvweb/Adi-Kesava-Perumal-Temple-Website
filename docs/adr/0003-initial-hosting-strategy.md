# ADR 0003: Candidate initial static hosting strategy

- **Status:** Proposed
- **Date:** 2026-10-19
- **Scope:** Hosting for the Phase 1 public static website

## Context and problem

The project will need a hosting arrangement for the generated public website.
The README describes GitHub Pages as the planned initial production host. The
project charter and architecture overview describe it as a planned or
proposed option, subject to configuration, suitability, repository and
domain requirements, platform limitations, and applicable costs.

The reviewed project records do not establish a formally accepted final
hosting provider, configured hosting or deployment workflow, custom-domain
setup, or production deployment. Cloudflare is identified as a possible DNS
arrangement; DNS management is distinct from static-site hosting.

## Decision

Keep GitHub Pages as a candidate initial host for Phase 1, not as a final
hosting commitment. This ADR remains `Proposed`. Confirm suitability,
repository and build compatibility, domain requirements, current platform
limitations and terms, and any applicable costs before approving production
hosting.

Treat domain ownership and DNS management as related but separate matters.
The existing documentation proposes Cloudflare DNS or another approved
arrangement; this ADR does not select a DNS provider or authorize a domain,
infrastructure, or expenditure commitment.

## Rationale

GitHub Pages is the hosting candidate already named in the project documents
for a static website. Retaining it as a candidate preserves the documented
direction while making the unresolved checks and need for approval explicit.
No hosting platform has been verified as configured or operational in the
reviewed repository.

## Alternatives assessed for this ADR

The following options are assessed for this record; the project records do
not establish that contributors previously compared them:

- **GitHub Pages as the candidate:** consistent with the existing
  documentation, but still subject to suitability, configuration, domain,
  platform, and cost checks.
- **Another suitable static hosting provider:** could be considered if
  requirements or verification show that the candidate is unsuitable; no
  alternative provider is selected here.
- **Defer provider selection:** avoids implying a commitment before deployment
  requirements are confirmed, but leaves the hosting choice open.

## Consequences and trade-offs

- GitHub Pages remains the documented candidate, not an approved final
  provider or a claim of existing deployment.
- Verification is required before production use, including build and
  repository compatibility, custom-domain and HTTPS requirements, platform
  limits and terms, and any applicable costs.
- The hosting choice may be revised if those checks identify a blocker or a
  better suitable arrangement.
- Cloudflare DNS, domain ownership, and any related costs require their own
  confirmation and approval; they are not settled by this hosting proposal.
- No hosting configuration, deployment workflow, domain change, or
  infrastructure is authorized by this ADR.

## References

- [README — planned initial hosting and deployment flow](../../README.md)
- [Project Management Charter — planned technology direction](../project-management/project-management-charter.md)
- [Architecture Overview — hosting, domain, and cost considerations](../architecture/architecture-overview.md)
