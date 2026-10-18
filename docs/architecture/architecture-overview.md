# Temple Website — Architecture Overview

**Document Version:** 1.0

**Project:** Arulmigu Sri Ambujavalli Thaayar Samedha Sri Adhi Kesava Perumal Temple Website

**Status:** Proposed Architecture

**Applies To:** Phase 1 — Public Static Website

---

## 1. Purpose

This document describes the proposed architecture for the temple's public static website.

It records the initial technology direction, structural principles, deployment approach and constraints that will guide implementation.

This is a planning document. Unless explicitly identified as implemented and verified, the technologies and capabilities described here are proposed rather than operational.

## 2. Architecture Objectives

The architecture should:

- Deliver a fast, responsive and accessible public website.
- Support reliable presentation of temple information on desktop and mobile devices.
- Keep infrastructure and operational costs low.
- Minimize ongoing maintenance and unnecessary operational complexity.
- Allow approved content to be updated without requiring changes to application logic for every routine content update.
- Support automated build and deployment workflows.
- Maintain clear separation between content, presentation, configuration and documentation.
- Allow future enhancements to be evaluated without unnecessarily complicating Phase 1.

## 3. Architectural Style

The initial solution will use a statically generated website.

Pages will be generated during the build process and delivered as static assets through a suitable hosting platform. The initial release does not require a custom application server, database or backend API.

This approach is appropriate for a predominantly informational website whose initial requirements do not include user accounts, online transactions or dynamic server-side operations.

Any future requirement that introduces dynamic behaviour must be assessed separately before the architecture is extended.

## 4. Proposed Technology Stack

| Concern | Proposed Technology | Purpose |
|---|---|---|
| Website framework | Astro | Generate static pages with limited unnecessary client-side JavaScript |
| Programming language | TypeScript | Improve code clarity and catch common development errors |
| Source control | Git and GitHub | Maintain history, collaboration and reviewable changes |
| Development environment | Visual Studio Code and GitHub Codespaces | Provide a consistent development workflow |
| Automation | GitHub Actions | Automate applicable validation, builds and deployment |
| Static hosting | GitHub Pages | Host the generated public website, subject to repository and domain configuration |
| DNS and domain management | Cloudflare DNS or another approved arrangement | Manage domain resolution and related configuration |
| Content | Markdown and structured content where appropriate | Separate suitable informational content from page implementation |
| Image delivery | Optimized WebP or AVIF where supported, with suitable fallbacks | Reduce image transfer size and improve loading performance |
| Video | External video hosting where appropriate | Avoid unnecessary video-storage and bandwidth requirements in the website repository |

The final implementation must verify compatibility, current platform capabilities, domain requirements and any applicable costs before production deployment.

## 5. High-Level Architecture

The intended delivery flow is:

1. A developer changes website source code, approved content or configuration in a Git branch.
2. The change is reviewed and merged into the designated deployment branch.
3. GitHub Actions runs the configured validation and build workflow.
4. The generated static website is published to the configured static hosting platform.
5. Visitors access the website through the configured public domain, when domain configuration is complete.

The deployment workflow, branch rules and hosting configuration must be implemented and tested before this flow is considered operational.

## 6. Repository Organization

The intended repository structure is:

- `README.md` — project overview, scope and current status.
- `AGENTS.md` — instructions and guardrails for AI coding agents.
- `docs/project-management/` — project charter and management documentation.
- `docs/architecture/` — architecture overview and related design documentation.
- `docs/adr/` — Architecture Decision Records.
- `docs/deployment/` — deployment and release instructions.
- `docs/maintenance/` — maintenance, content update and handover instructions.
- `src/` — Astro application source code and page components.
- `public/` — static assets served without application processing, where appropriate.

Additional directories may be introduced when required by the selected Astro structure or implemented features.

The presence of a directory in this planned structure does not imply that the corresponding application functionality has been implemented.

## 7. Content Architecture and Governance

Temple information should be organized so that content can be reviewed and maintained independently of presentation wherever practical.

Markdown and Astro-supported structured content are the initial preferred options for suitable content.

Content categories may include:

- General temple information.
- Temple history and background.
- Deity information.
- Approved trustee information.
- Timings and visitor information.
- Announcements.
- Photo and video gallery metadata.

Content models and page structures should be introduced incrementally as features are implemented.

See the [Content Architecture](./content-architecture.md) for recommended
content formats, categories, organization, and manual publication governance.

### Content Approval

Information supplied by an individual must not automatically be treated as authorized for public release.

Before publication:

- Confirm the authority of the person supplying or approving the information.
- Verify factual accuracy where appropriate.
- Obtain the required approval for trustee details, religious or historical descriptions, announcements and media.
- Respect applicable privacy, copyright and permissions requirements.
- Exclude confidential records, private financial information, credentials and unnecessary personal data.

When approval or publication rights are uncertain, keep the affected content unpublished until the matter is resolved.

## 8. Presentation and Accessibility

The website should follow responsive design principles and provide a usable experience across common screen sizes.

Implementation should consider:

- Semantic HTML and logical heading structure.
- Keyboard navigation and visible focus indicators.
- Adequate colour contrast.
- Descriptive alternative text for meaningful images.
- Readable typography and appropriate text sizing.
- Clear navigation and link labels.
- Appropriate page titles, descriptions and language metadata.
- Optimized images and sensible loading behaviour.

Accessibility and performance checks should be incorporated into the acceptance criteria of relevant stories.

## 9. SEO and Discoverability

The initial implementation should provide appropriate foundations for search engine discoverability, including:

- Descriptive page titles and meta descriptions.
- Semantic page structure.
- Canonical URLs where appropriate.
- A sitemap and robots directives as applicable.
- Social-sharing metadata where useful.
- Meaningful internal links.
- Consistent public-domain configuration.

Search engine registration, indexing and ranking are external outcomes and cannot be guaranteed by the implementation alone.

## 10. Security and Privacy

The public website should minimize the collection and processing of personal information.

Phase 1 does not require user authentication, a database, a payment gateway or a custom backend API.

Development practices should include:

- Never committing credentials, access tokens or other secrets.
- Reviewing third-party dependencies and integrations.
- Avoiding unnecessary third-party scripts and trackers.
- Restricting deployment credentials and permissions to what is required.
- Reviewing generated content and configuration before publication.
- Using authorized public content and media.
- Ensuring that deployment changes are reviewed and verified.

Any later feature that introduces personal-data collection, authentication, transactions or other sensitive processing requires a separate security, privacy, architecture and cost assessment.

## 11. Hosting, Domain and Cost Considerations

GitHub Pages is the proposed static hosting option for the initial release, subject to confirmation of repository compatibility, build configuration, custom-domain requirements and platform limitations.

Cloudflare DNS is the proposed DNS-management option, subject to confirmation of domain ownership and the appropriate configuration.

Before production deployment:

- Confirm who owns and controls the domain.
- Confirm who will maintain DNS and hosting access.
- Verify HTTPS and custom-domain configuration.
- Confirm applicable usage limits and platform terms.
- Identify any recurring or one-time charges.
- Obtain approval from the appropriate temple representative for any expenditure.

No production infrastructure or paid service should be assumed to exist until it has been configured and verified.

## 12. Build, Test and Deployment Strategy

The intended workflow includes:

- Local development and preview.
- Automated build validation.
- Relevant automated tests and quality checks.
- Pull request review.
- Deployment after the agreed merge and release conditions are satisfied.
- Verification of the deployed website.
- Documentation of operational and rollback considerations where applicable.

The initial automation should remain proportionate to the static site's needs. Additional testing, preview deployments or deployment protections may be introduced as the project matures.

## 13. Architectural Constraints and Non-Goals

The initial architecture intentionally avoids:

- A custom application server.
- A database.
- A custom backend API.
- User authentication and member accounts.
- Online payments and donation processing.
- A custom content management system.
- Unnecessary client-side JavaScript.
- Unapproved third-party services or recurring costs.

These exclusions are specific to the initial release and may be reconsidered through a separately approved change or future phase.

## 14. Architecture Decisions and Future Review

Significant architectural decisions should be recorded in `docs/adr/` using Architecture Decision Records.

Each relevant decision should capture:

- Context and problem.
- Options considered.
- Decision and rationale.
- Consequences and trade-offs.
- Status and date.

The architecture overview should be updated when material decisions change or when implementation establishes that a proposed assumption is incorrect.

## 15. Implementation Status

At the time this document is created, the repository contains the initial project documentation foundation.

The Astro application, build pipeline, automated deployment, hosting configuration, custom-domain setup and production website must each be verified independently as they are implemented.

Planned architecture must not be reported as completed implementation.

---

**End of Architecture Overview v1.0**
