# Temple Website Project — Project Management Charter

**Document Version:** 1.0

**Project:** Arulmigu Sri Ambujavalli Thaayar Samedha Sri Adhi Kesava Perumal Temple Website

**Status:** Baseline for Phase 1

**Project Delivery Model:** Agile, incremental delivery

**Source of Truth:** GitHub repository

**Document Owner:** Project Maintainer

**Development Contribution:** Voluntary service

---

## 1. Purpose

The purpose of this project is to design, develop, deploy and maintain an official public website for Arulmigu Sri Ambujavalli Thaayar Samedha Sri Adhi Kesava Perumal Temple.

The website will provide devotees and visitors with reliable, accessible and approved information about the temple, its deities, history, trustees, timings, location, announcements, photographs and videos.

The solution should be secure, cost-conscious, maintainable, accessible and capable of future enhancement without introducing unnecessary technical complexity in the initial release.

Development is undertaken as a voluntary service. Any infrastructure, domain, hosting or other operational costs, if applicable, must be borne by the temple and agreed upon before expenditure is incurred.

## 2. Project Objectives

1. Establish an official public-facing website for the temple.
2. Publish accurate information approved by an appropriate temple representative.
3. Provide a responsive experience across desktop, tablet and mobile devices.
4. Follow sound software engineering, accessibility, security, SEO and documentation practices.
5. Use a formal Agile approach with traceable requirements, milestones, reviews and acceptance criteria.
6. Maintain the source code, project documentation and delivery history in GitHub.
7. Keep the initial implementation simple and affordable while allowing future phases to be evaluated separately.

## 3. Scope

### 3.1 Phase 1 — Public Static Website

The initial release is limited to a public static website.

The planned website capabilities include:

- Home page and general temple introduction.
- Temple history and background information.
- Deity and temple information.
- Trustee information, subject to authorization and approval.
- Temple timings, address, location and visitor information.
- Announcements and public notices.
- Photo gallery containing approved photographs.
- Video gallery using suitable external video hosting where appropriate.
- Responsive layout and mobile-friendly navigation.
- Accessibility and search engine optimization.
- Production deployment, documentation and handover.

Features will be delivered incrementally according to approved stories, priorities and milestones.

### 3.2 Out of Scope for Phase 1

The following are excluded unless separately proposed, reviewed and approved as a future phase:

- Online donations, payment processing or financial transactions.
- User accounts, authentication or member login.
- Booking, appointment or reservation systems.
- Trustee administration portals or other restricted-access portals.
- A content management system or custom backend.
- A database or server-side application.
- Private trustee, member or financial records.
- Other interactive or transactional capabilities that require additional infrastructure or operational responsibilities.

Future possibilities are not commitments for the current release.

## 4. Technology and Architecture Direction

The planned technology direction is:

- **Frontend framework:** Astro.
- **Programming language:** TypeScript.
- **Source control:** Git and GitHub.
- **Continuous integration and deployment:** GitHub Actions.
- **Static website hosting:** GitHub Pages, subject to configuration and suitability.
- **Domain and DNS:** Cloudflare DNS or another approved arrangement.
- **Content:** Markdown and structured content where appropriate.
- **Images:** Optimized formats such as WebP or AVIF where supported.
- **Videos:** External video hosting where appropriate.

These are planned choices, not a statement that the application or deployment has already been implemented.

Any material architectural change should be documented with its rationale and implications before implementation.

## 5. Project Governance

### 5.1 Repository as the Source of Truth

The GitHub repository is the authoritative location for:

- Source code and configuration.
- Project charter and architecture documentation.
- Architecture Decision Records.
- Epics, features, stories and tasks, or links to their authoritative records.
- Milestone definitions and delivery status.
- Review history and release documentation.
- Deployment and maintenance instructions.

Project decisions that affect scope, architecture, security, cost or public content must be recorded in an appropriate, reviewable form.

### 5.2 Roles and Responsibilities

**Project Maintainer / Volunteer Developer**

- Coordinates planning and implementation.
- Maintains source code, technical documentation and project traceability.
- Reviews AI-generated changes and verifies implementation quality.
- Tracks actual effort for transparency.
- Does not independently authorize temple content or commit the temple to expenditure.

**Authorized Temple Representative**

- Confirms the authority to provide or approve public information.
- Reviews and approves temple-related content intended for publication.
- Confirms trustee details, timings, announcements, photographs and other sensitive or potentially disputed material as appropriate.
- Approves any temple-funded operational expenditure through the appropriate process.

Where authorization is unclear, the affected content must remain unpublished until clarified.

## 6. Agile Delivery Framework

### 6.1 Work Hierarchy

The project will use the following hierarchy:

**Project → Epic → Feature → User Story → Task**

- **Project:** The overall temple website initiative.
- **Epic:** A major delivery objective.
- **Feature:** A coherent capability within an epic.
- **User Story:** A testable requirement expressed from the perspective of a user or stakeholder.
- **Task:** A specific implementation, documentation, review or verification activity needed to complete a story.

### 6.2 Initial Epic

**EPIC-01 — Static Website Rollout**

This epic covers the delivery of the Phase 1 public static website and its supporting foundation.

Features and stories will be created beneath this epic and assigned to milestones according to scope and dependencies.

### 6.3 Work Item Status Workflow

The standard workflow is:

1. BACKLOG
2. READY
3. IN PROGRESS
4. CODE REVIEW
5. TESTING
6. ACCEPTANCE
7. DONE

A work item may move to the next applicable status only when its required conditions are satisfied. Blocked work must be made visible rather than silently treated as in progress or complete.

### 6.4 Definition of Ready

A story is ready to begin when:

- Its purpose and expected outcome are understood.
- Acceptance criteria are documented.
- Dependencies and material assumptions are identified.
- Required content, approvals or assets are identified.
- The work is sufficiently clear to estimate and implement.
- Its priority and milestone assignment are understood.

Unresolved matters that materially affect correctness, authorization, security or cost must be clarified before implementation.

### 6.5 Definition of Done

A story is considered done when all applicable conditions are satisfied:

- Acceptance criteria have been met.
- Implementation or documentation has been reviewed.
- Required builds and tests pass.
- Responsive behaviour and accessibility have been checked where applicable.
- SEO and content quality have been checked where applicable.
- No known unresolved critical defect remains.
- Documentation and related work items have been updated.
- Changes have been merged through the agreed Git workflow.
- Deployment has been verified when the story affects a deployed release.
- Actual volunteer effort has been recorded.

Public-facing temple content must additionally have the required approval before publication.

## 7. Milestones and Release Management

Work will be organized into milestones with defined objectives, included work items and completion criteria.

The initial milestone is:

**M1 — Project Foundation**

Its intended scope includes:

- Repository and project documentation foundation.
- Architecture overview and documented technical decisions.
- AI-assisted development instructions and engineering guardrails.
- Astro application initialization and foundational configuration, when scheduled in the approved stories.
- Initial continuous integration and deployment foundation.
- Initial deployment, maintenance and handover documentation as applicable.

Milestone scope must be reflected in the repository's work items. Completion is determined by the milestone's acceptance criteria, not merely by the presence of files or code.

Subsequent milestones will be planned and approved as the project progresses.

## 8. Development and Change Control

- Use feature branches for changes rather than making routine changes directly on the main branch.
- Keep changes focused on an identifiable story or related work item.
- Review changes before merging.
- Run relevant validation checks before accepting a change.
- Update documentation when implementation or decisions change.
- Record significant architectural decisions as Architecture Decision Records.
- Review changes to scope, technology, cost or release commitments before proceeding.
- Do not introduce new services, paid subscriptions or operational commitments without appropriate approval.

AI coding agents may assist with analysis, implementation, testing and documentation. Their output must be reviewed by the project maintainer. Agents must not independently publish unapproved content, expose secrets, or authorize spending or production changes beyond explicitly granted permissions.

## 9. Content Governance, Privacy and Security

Temple information is not automatically approved for publication merely because it has been supplied to the developer.

Before publication:

- Confirm that the person providing the information is authorized to do so, or obtain approval from an appropriate temple representative.
- Verify the accuracy of historical, religious, trustee and operational information.
- Obtain approval for photographs, videos and other assets where required.
- Avoid publishing private personal information, confidential records, private financial information or internal communications.
- Do not store credentials, API keys, access tokens or other secrets in source control.
- Use only content and assets that are authorized for the intended public use.
- Resolve material doubts about authority, accuracy, privacy or permissions before publication.

If approval is uncertain or disputed, the content must remain unpublished until the issue is resolved.

## 10. Effort Tracking and Cost Management

The developer is contributing development effort as a voluntary service. Development hours are recorded for transparency, planning and learning, not for billing.

Each applicable story should capture:

- Estimated effort.
- Actual effort.
- Significant deviations from the estimate, where useful.
- Relevant delivery or review notes.

Infrastructure and operational expenditure is separate from volunteer development effort.

Potential costs must be identified and communicated before they are incurred. Any domain, hosting, subscription or other operational cost must be agreed upon with the appropriate temple representative, and the temple must bear approved costs.

The project should prefer suitable free or low-cost options where they satisfy the requirements.

## 11. Quality and Acceptance

Quality is evaluated against the story's acceptance criteria and the project's Definition of Done.

Depending on the change, verification may include:

- Successful build and automated checks.
- Functional testing.
- Responsive layout checks.
- Accessibility checks.
- SEO and metadata checks.
- Link and content verification.
- Security and configuration review.
- Deployment verification.
- Documentation and maintenance readiness.

The project maintainer is responsible for technical verification. The appropriate temple representative is responsible for approving temple content and any other matters requiring temple authorization.

Technical completion does not replace content approval.

## 12. Documentation and Handover

The repository will maintain appropriate documentation for:

- Project management and scope.
- Architecture and technical decisions.
- Development setup and contribution workflow.
- Deployment and release procedures.
- Content update and maintenance procedures.
- Operational ownership and handover.

Documentation must distinguish planned capabilities from implemented and verified capabilities.

Before handover, operational responsibilities, access ownership, recurring costs and maintenance expectations must be clarified with the temple.

## 13. Charter Review and Amendments

This charter establishes the initial project management baseline.

Changes that materially affect project scope, governance, architecture, costs, security or delivery commitments must be reviewed and documented. Approved amendments should be version-controlled in GitHub.

The charter may be refined as implementation reveals new requirements, but changes must not silently expand the agreed Phase 1 scope.

## 14. Baseline Summary

The project will deliver an approved, public static temple website through an incremental Agile process. GitHub will serve as the source of truth. The initial technical direction is Astro with TypeScript and a static deployment approach. Content authorization, security, cost transparency, technical review and maintainability are mandatory considerations throughout delivery.

**End of Project Management Charter v1.0**
