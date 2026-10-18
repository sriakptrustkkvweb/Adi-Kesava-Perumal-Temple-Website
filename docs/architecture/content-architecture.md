# Content Architecture

## Purpose and scope

This document defines a minimal, proposed organization for public temple website
content. It applies to Phase 1 — Public Static Website and complements the
[Architecture Overview](./architecture-overview.md) and
[Source Code Structure](./source-code-structure.md).

The recommendations below guide future content implementation; they do not
create content, schemas, Astro collection loaders, an approval workflow, or
application behavior. Content must remain unpublished until it has been
reviewed and authorized for public release.

## Content formats and organization

Use Markdown for narrative material that benefits from headings and prose, such
as history, deity information, and longer announcements. Use small structured
records, in an Astro-supported format such as JSON or YAML, when a category has
repeated fields that need consistent display, sorting, or filtering, such as
timings, location details, trustee entries, and media references. Do not
duplicate prose in structured fields when a Markdown document is clearer.

Keep content separate from page and component implementation. A simple,
category-based layout under `src/content/` is sufficient; keep image assets in
the static asset area (for example, `public/images/`) and refer to them from
content metadata. Video entries should normally reference an approved external
host rather than store video files in the repository. Introduce only the
categories and files needed by implemented pages.

See the [Media Architecture](./media-architecture.md) for image delivery,
responsive performance, video-reference, and media-rights guidance.

The following fields are representative, not a required schema. Select only
fields needed for a specific published item and do not add personal or
operational details without a clear public purpose and authorization.

| Category | Recommended format | Representative fields |
|---|---|---|
| Temple history | Markdown for narrative; optional structured metadata for display title or chronology | `title`, `summary`, `body`, `period` or `date`, `sourceReferences`, `status` |
| Deity information | Markdown for explanatory prose; structured metadata only for repeated display fields | `title`, `body`, `sourceReferences`, `status` |
| Trustees | One minimal structured record per approved public entry | `name`, `publicRole`, `term` if relevant, `status` |
| Timings | Structured data for consistently formatted days and time periods | `dayOrPeriod`, `openingTime`, `closingTime`, `notes`, `effectiveFrom`, `status` |
| Location | A single structured record for stable, displayable visitor details | `postalAddress`, `mapReference` if approved, `visitorNotes`, `status` |
| Announcements | Markdown for message body, with structured publication metadata when needed | `title`, `body`, `publishedOn`, `expiresOn` or `eventDate`, `status` |
| Photographs | Image asset plus a structured metadata entry | `file`, `caption`, `altText`, `dateOrPeriod` if verified, `rightsOrPermissionReference`, `status` |
| Video references | Structured metadata linking to an approved external video | `title`, `provider`, `url`, `caption`, `rightsOrPermissionReference`, `status` |

Do not create sample temple records as part of establishing this architecture.
Actual text, facts, names, dates, addresses, media, and external links require
separate verification and publication approval.

## Naming conventions

- Use lowercase, descriptive kebab-case for category folders and filenames.
- Prefer stable descriptive names over names that encode changeable presentation
  or route details.
- Use ISO 8601 dates (`YYYY-MM-DD`) for dates when dates are needed and verified.
- Use descriptive, lowercase filenames for media. Avoid personal details or
  other sensitive information in filenames.
- Keep media references relative to the repository where practical; use
  canonical HTTPS URLs for approved external video references.
- Keep category-specific fields small and consistently named. Avoid introducing
  identifiers or metadata that have no current use.

## Manual content governance

Content follows three manual states:

1. **Draft** — being prepared; not eligible for publication.
2. **Review** — awaiting factual, permissions, privacy, and publication review;
   not eligible for publication.
3. **Approved** — an authorized temple representative has approved the specific
   content and its intended public use. It may be considered for publication
   after the checks below are complete.

These states describe editorial progress only. A `status` field, filename,
folder, or other status metadata does not itself establish authority, prove
accuracy, grant media rights, or authorize publication. Publication requires
human confirmation that the appropriate representative approved the exact
content and its intended public use. There is no automated approval workflow
defined by this architecture.

Before publication, the maintainer and authorized temple representative should
manually confirm:

- **Authority and scope:** The representative is authorized to approve the
  material, and the approval covers its public use in the intended context.
- **Accuracy:** Historical, religious, deity, trustee, timing, location, and
  announcement details have been checked with appropriate sources or
  representatives. Record source references where useful; do not present
  uncertain claims as facts.
- **Personal information:** Trustee or other individual details are limited to
  what is appropriate and approved for public release. Exclude private contact
  details and unnecessary personal information.
- **Media permissions:** Confirm rights, consent, attribution, and suitability
  for the intended public use of each photograph, video, caption, and related
  asset. An asset being available online or supplied to a contributor is not
  evidence of permission.
- **Sensitive and unauthorized material:** Exclude confidential records,
  internal communications, private financial information, credentials, and
  content whose authority, accuracy, privacy, or permissions are uncertain.

Keep unresolved or disputed material unpublished until the relevant questions
are resolved. Do not treat inclusion in the repository or a successful build as
publication approval.

## Implementation boundary

This architecture intentionally adds no content schema, collection loader,
CMS, database, backend, dependency, or automated workflow. Any future
implementation should follow the approved content categories and governance
above while preserving the static-first architecture.
