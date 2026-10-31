# Source Code Structure

## Purpose

This document describes the intended organization of the source code for the Sri Adi Kesava Perumal Temple website. It establishes consistent conventions for contributors while keeping the application simple, static-first, and maintainable.

## Source Directory Layout

```text
src/
├── pages/
│   └── index.astro
├── layouts/
├── components/
├── styles/
└── content/
```

### `src/pages/`

Contains Astro page route entry points and page composition. Astro uses
file-based routing, so filenames and directory paths determine the corresponding
website routes. Pages should assemble layouts, reusable components, and
content rather than becoming the only copy of editable website information.

### `src/layouts/`

Contains shared page layouts that define common document structure, such as the
HTML document shell, shared navigation placement, footer placement, and
page-level metadata. Layouts should be introduced when they provide genuine
reuse and should focus on presentation structure rather than duplicating
editable temple content.

### `src/components/`

Contains reusable Astro presentation and behavior components used by pages or
layouts. Components should have clear responsibilities and should not be
created solely to wrap trivial markup without a reuse or clarity benefit.
Presentation components should consume shared or page content rather than
hardcoding editable website information.

### `src/styles/`

Contains presentation styling, including global styles and common design rules.
Page-specific styles may remain alongside their relevant Astro components when
that is simpler. Styling must remain separate from editable content and should
not be used to hide unapproved or draft information from the intended public
page.

### `src/content/`

Reserved for organized, approved temple website content, including history,
deity information, trustee details, timings, location, announcements, and
photograph and video-reference metadata. Use Markdown for narrative content and
structured data where repeated fields need consistent presentation or sorting.
Shared configuration may also use an agreed structured file under this existing
directory where appropriate; do not create a new configuration structure or
schema as part of the content editing standards.
See the [Content Architecture](./content-architecture.md) for recommended
formats, organization, naming, and manual publication governance, including the
detailed [Content Authoring, Editing and Publication Standards](./content-architecture.md#content-authoring-editing-and-publication-standards).

Content files are edited narrative and structured website content, not Astro
layout or component implementation. Pages and components consume this content;
they must not duplicate authoritative content as hardcoded text. Content must be
reviewed and authorized by the appropriate temple representative before
publication.

## Supporting Directories

- `public/` contains static assets served directly, such as favicons and images
  that do not require processing by Astro. Organize approved images under
  `public/images/`; keep their reference metadata in `src/content/`. See the
  [Media Architecture](./media-architecture.md) for image delivery and video
  reference guidance.
- `docs/` contains project documentation, including architecture decisions and contributor guidance.

## Conventions

1. Follow Astro's file-based routing conventions under `src/pages/`.
2. Prefer simple, descriptive filenames and clear responsibilities.
3. Reuse components and layouts where they improve consistency or reduce meaningful duplication.
4. Avoid unnecessary dependencies, abstractions, and directory nesting.
5. Keep the initial website static-first; do not introduce a backend, database, authentication, or CMS as part of source organization.
6. Keep temple content changes subject to the project's content-approval expectations.
7. Update this document when the established source structure changes materially.

## Scope

This structure provides a foundation for incremental development. It does not require every directory to contain implementation code immediately, nor does it prescribe future features before they are approved.