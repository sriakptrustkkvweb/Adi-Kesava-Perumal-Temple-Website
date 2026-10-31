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

## Content Authoring, Editing and Publication Standards

### Content classification

Classify website information before choosing its storage location:

- **Shared website configuration:** Temple name display, navigation labels and
  route paths, footer labels, and shared website metadata such as a default
  title or description. Keep these in an agreed structured-file location,
  preferably under `src/content/` where that location provides practical reuse
  and does not introduce a separate parallel content tree or new schema.
  Navigation labels and route paths are presentation configuration by default
  and are not automatically governed temple content merely because the
  navigation is displayed in the site header or footer.
- **Page-specific content:** Home page text, temple history, deity descriptions,
  and other information that belongs to a particular published page. Use
  narrative Markdown where prose is clear; use structured metadata only where
  repeated fields or display behavior require it.
- **Structured records:** Timings, location details, trustee entries,
  announcements, photograph metadata, and other repeated records that need
  consistent fields, sorting, or filtering.
- **Presentation code:** Astro layouts, components, styling, and interaction
  code. Presentation code controls structure, rendering, and behavior; it must
  not become the only editable copy of reusable temple information.

A content item should have one clear authoritative location in the repository.
If information changes, the contributor should update that location rather than
creating another copy for a page, component, or file.

### Content location and formats

Continue to use the existing `src/content/` architecture established by S11.
Do not create another parallel content tree or introduce content schemas,
collections, loaders, or directories without a separately approved need.

- Use Markdown under `src/content/` for narrative material.
- Use JSON or YAML for small structured records under `src/content/` when
  repeated fields, consistent rendering, sorting, or filtering make structure
  useful.
- Use an agreed structured file for shared website configuration when it is
  reused by multiple pages or components. Prefer an existing `src/content/`
  location where appropriate; do not create a separate configuration
  architecture or schema for this purpose.
- Keep image assets in `public/images/` and video references in approved
  content metadata according to the
  [Media Architecture](./media-architecture.md). Do not duplicate media
  metadata, captions, alternative text, rights information, or asset paths in
  presentation code.
- Do not duplicate the same temple name, page text, structured record, label,
  or media reference across files or components.

The formats above remain format guidance, not a requirement to add schemas,
Astro collections, or new frontmatter fields for this story.

### Editing conventions

Contributors should:

1. Add new content only under the existing `src/content/` category structure
   that matches the content type. Add a new category only when an implemented
   website need clearly requires it.
2. Edit the existing authoritative content file rather than adding a second
   copy or editing generated output.
3. Use descriptive lowercase kebab-case filenames and category directories.
   Use names that remain stable rather than names that encode a temporary
   layout or route.
4. Keep fields in existing structured records consistently named and use only
   fields needed for the published content. Use ISO 8601 dates (`YYYY-MM-DD`)
   for verified dates. Avoid inconsistent spelling, units, and date formats.
5. Keep editable temple information out of Astro layouts, components, and
   style files. Pages and components should consume shared or page content
   rather than hardcoding the same information.
6. Reuse content by importing or loading the existing shared content from the
   appropriate implementation mechanism. Do not copy or redeclare a value that
   already has one authoritative file.

Before changing content, inspect nearby files for established conventions and
preserve useful fields, formatting, and links. Content examples or AI-generated
drafts are not evidence that information is accurate or authorized.

### Editorial status

Draft, Review, and Approved are the human-managed editorial states defined
under [Manual content governance](#manual-content-governance). They describe
progress only: neither Draft nor Review means publication approval, and
Approved means the exact content and intended public use have been confirmed
by an authorized temple representative as described there.

These states provide no automated enforcement, automated approval, build
exclusion, or proof of authority. A status field, filename, folder, label, or
pull-request state does not establish approval by itself.

### Roles and approval workflow

The responsibilities are separate:

- **Content author/contributor:** Prepares accurate, clearly scoped content
  and submits it through the GitHub change workflow.
- **Technical reviewer/project maintainer:** Checks formatting, repository
  conventions, Markdown or structured-file correctness, build compatibility,
  links, privacy, and presentation integration. Technical review does not
  grant temple publication authority.
- **Authorized temple representative/publication approver:** Confirms authority,
  accuracy where applicable, and approval for the exact content and intended
  public use.

Use the following workflow:

1. The author prepares the content change.
2. The author submits a pull request containing the exact proposed content
   and any necessary factual or media references.
3. The technical reviewer checks correctness, formatting, repository
   conventions, and build compatibility.
4. The authorized temple representative confirms publication approval for the
   exact content and intended public use.
5. The approval is recorded or referenced in the pull request.
6. After technical review and publication approval, the change can be merged
   and published according to the project workflow.

A technical review, successful build, closed issue, or merged pull request is
not by itself temple publication approval. Approval must come from the
authorized representative before the approved content is used by a published
page.

Publication approval is also distinct from repository visibility. Draft or
review pull requests may exist in a repository only when they contain
non-sensitive proposed public content that is suitable for review under the
repository's access controls. They must still not be merged into the
publication branch or referenced by a published page until the temple
publication approval is confirmed.

### Approval evidence

The pull request should identify:

- The content or content files being approved.
- The authorized approver's role, without inventing an individual role or
  authority that has not been confirmed.
- The approval confirmation or an appropriate reference to the approval.
- The scope of the approval, including the intended page or public use where
  relevant.

Do not commit confidential correspondence, private personal information,
credentials, or unnecessarily detailed approval records to the repository.
Link or summarize approval evidence only to the extent needed to support a
reviewable public change.

### Privacy and repository visibility

Separate repository safety from publication approval:

- **Private, confidential, sensitive, or unauthorized personal information**
  must never be committed, including as draft content or placeholder examples.
  This includes credentials, confidential records, private financial or contact
  information, unnecessary personal information, sensitive media, and secret
  access information.
- **Non-sensitive proposed public content** may be submitted for technical and
  editorial review when its use is appropriate for the repository and its
  visibility or access controls. Such proposals may still be inaccurate,
  disputed, draft, or awaiting approval and therefore are not authorized for
  publication merely because they are committed or included in a pull request.
- **Publication-unapproved content** must not be merged into the publication
  branch and must not be referenced by pages intended for publication. A
  successful build, technical approval, issue closure, repository inclusion,
  or pull-request merge does not replace temple publication approval.

Keep unresolved or uncertain material outside the repository where practical,
or use an appropriate non-public workflow until its authority, accuracy,
privacy, rights, and publication approval are resolved.

### Publication safety

Marking a content item as Draft, or placing a draft status label in a file, does
not automatically prevent Astro or another build process from including it in a
static build. Generated pages may expose any referenced unapproved content.

Unapproved content must not be referenced by pages intended for publication.
Draft exclusion, automated status filtering, automated approval enforcement, and
automated publication workflows are outside S37's scope and are not substitutes
for the manual approval process.

## Manual content governance

The repository-safety and publication-safety distinctions are summarized in
[Privacy and repository visibility](#privacy-and-repository-visibility) and
[Publication safety](#publication-safety). The following checks remain the
pre-publication requirements for each content item.

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
