# Arulmigu Sri Ambujavalli Thaayar Samedha Sri Adhi Kesava Perumal Temple

Official website project for **Arulmigu Sri Ambujavalli Thaayar Samedha Sri Adhi Kesava Perumal Temple**.

This project is being developed as a volunteer-driven initiative to establish a reliable, maintainable and low-cost online presence for the temple.

---

## Project Overview

The initial goal is to build a simple, fast and accessible public website containing essential information about the temple.

The project follows a **static-first architecture**, allowing the website to remain inexpensive and easy to maintain while keeping the foundation extensible for future requirements.

The project is managed using an Agile-inspired approach with:

- Epics
- Features
- User Stories
- Tasks
- Milestones
- Releases
- GitHub Issues
- GitHub Projects
- Pull Requests

---

## Current Phase

**Phase 1 — Public Static Website**

### Current Epic

**EPIC-01 — Static Website Rollout**

### Current Milestone

**M1 — Project Foundation**

The current focus is establishing the project, technical architecture, development workflow and deployment foundation before implementing the complete public website.

---

## Objectives

The project aims to:

- Establish an official online presence for the temple.
- Publish accurate temple information.
- Provide temple history and background.
- Publish temple timings and location information.
- Provide approved trustee information where appropriate.
- Publish photographs and videos.
- Publish announcements and important updates.
- Provide a responsive experience across devices.
- Follow basic accessibility and SEO practices.
- Keep infrastructure and maintenance costs low.
- Provide sufficient documentation for future volunteers.
- Create a foundation that can support future temple-related digital services.

---

## Initial Scope

The first release is expected to include:

- Home page
- Temple history
- Deity information
- Temple timings
- Location and contact information
- Trustee information
- Photo gallery
- Video gallery
- Announcements
- Responsive design
- Basic accessibility
- Basic SEO
- Production deployment

---

## Out of Scope for Phase 1

The following capabilities are intentionally deferred:

- Online donations
- Payment gateway
- Member registration
- Member database
- User authentication
- Trustee administration portal
- Online booking
- Temple asset management
- Financial/accounting systems
- Custom backend
- Database-driven application

These may be considered in future phases based on actual requirements.

---

## Technology Direction

The current technical direction is:

| Area | Technology / Approach |
|---|---|
| Frontend | Astro |
| Language | TypeScript |
| Source Control | Git / GitHub |
| CI/CD | GitHub Actions |
| Initial Hosting | GitHub Pages |
| DNS | Cloudflare |
| Content | Markdown / structured content |
| Images | Optimized WebP/AVIF where appropriate |
| Video | External video platforms |
| Backend | Deferred |
| Database | Deferred |

Technology decisions may evolve as the project progresses.

Significant architectural decisions will be documented separately as Architecture Decision Records (ADRs).

---

## Repository Structure

The repository is organized approximately as follows:

```text
.
├── docs/
│   ├── project-management/
│   ├── architecture/
│   ├── adr/
│   ├── deployment/
│   └── maintenance/
│
├── public/
│
├── src/
│
├── README.md
└── ...
```

The structure may evolve as implementation progresses.

---

## Project Documentation

Important project documentation is maintained inside the repository.

### Project Management

`docs/project-management/`

Contains:

- Project Management Charter
- Agile/project execution guidance
- Project governance documentation
- Effort tracking information

### Architecture

`docs/architecture/`

Contains:

- System architecture
- Application structure
- Content architecture
- Technical design documentation

### Architecture Decision Records

`docs/adr/`

Contains important technical decisions and the reasoning behind them.

### Deployment

`docs/deployment/`

Contains deployment and hosting instructions.

### Maintenance

`docs/maintenance/`

Contains instructions required for future volunteers to maintain the project.

---

## Project Management

GitHub is the primary project management and development platform.

The project follows this hierarchy:

```text
Project
   │
   └── Epic
        │
        └── Feature
             │
             └── User Story
                  │
                  └── Task
```

Work is tracked using GitHub Issues, Projects, Milestones and Pull Requests.

The formal project-management rules are documented in:

`docs/project-management/project-management-charter.md`

---

## Development Workflow

The general development workflow is:

```text
BACKLOG
   ↓
READY
   ↓
IN PROGRESS
   ↓
CODE REVIEW
   ↓
TESTING
   ↓
ACCEPTANCE
   ↓
DONE
```

Changes should normally be developed on a separate branch and merged through a Pull Request.

---

## Local Development

Once the Astro project has been initialized, development instructions will be maintained here.

Typical workflow:

```bash
npm install
npm run dev
```

The exact commands will be finalized when the project foundation is established.

---

## Deployment

The initial production deployment is planned for **GitHub Pages**.

The intended deployment flow is:

```text
Developer
    ↓
Git
    ↓
GitHub Repository
    ↓
Pull Request
    ↓
GitHub Actions
    ↓
Build
    ↓
GitHub Pages
    ↓
Public Website
```

Deployment-specific instructions will be maintained under:

`docs/deployment/`

---

## Content Governance

Only information approved for public publication should be included in the public website repository.

The repository must not contain:

- Passwords
- API keys
- Payment credentials
- Private financial information
- Sensitive personal information
- Confidential trustee information
- Private member information
- Other information that is not authorized for public publication

Content should be verified with the appropriate temple authority before publication.

---

## Future Roadmap

The project may evolve through the following broad phases:

### Phase 1
**Public Static Website**

### Phase 2
**Content / Trustee Administration**

### Phase 3
**Online Donations and Payments**

### Phase 4
**Temple Member Services**

### Phase 5
**Temple Asset Management**

Future phases are not commitments at this stage.

They will be planned separately when the temple has an actual requirement.

---

## Volunteer Contribution

This project is being developed as a volunteer service to the temple.

Development effort, research, documentation, testing and other significant project activities may be recorded as part of the project's **Volunteer Contribution & Effort Register**.

The purpose of this record is transparency and project history, not commercial billing.

---

## Contribution

Contributions and changes should follow the project's GitHub workflow.

Before making significant changes:

1. Identify or create the relevant GitHub Issue.
2. Confirm the requirement and acceptance criteria.
3. Implement the change on an appropriate branch.
4. Create a Pull Request.
5. Perform the required testing.
6. Obtain review/acceptance where applicable.
7. Merge the change.
8. Record relevant project effort.

---

## Project Status

Project status and active work are tracked through GitHub Projects and Issues.

For the current work items, see the repository's GitHub Project.

---

## License and Usage

The project's licensing and content-usage policy will be established as part of the project foundation.

Temple photographs, historical material, written content and other media may have separate ownership or usage considerations and must not automatically be assumed to be freely reusable.

---

## Project Documentation

The repository is intended to contain everything necessary for a future volunteer to understand and maintain the project.

The guiding principle is:

> **Build it simply. Document it properly. Keep it maintainable.**
