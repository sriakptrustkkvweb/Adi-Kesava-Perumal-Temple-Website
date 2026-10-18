# Media Architecture

## Purpose and scope

This document provides proposed guidance for media used by the Phase 1 public
static website. It complements the [Architecture Overview](./architecture-overview.md)
and [Content Architecture](./content-architecture.md). It does not implement
media processing, responsive variants, video embeds, or approval automation.

## Organization and naming

Store approved image assets under `public/images/`, organized in simple,
descriptive category directories when useful. Use descriptive lowercase
kebab-case filenames; avoid personal or sensitive information in paths and
filenames. Keep media-reference metadata, such as captions, alternative text,
and approved asset paths or video URLs, in `src/content/` as described in the
[Content Architecture](./content-architecture.md).

Do not add media to the public asset directory until its intended public use
has been authorized. Keep video content externally hosted by default and
reference it from content metadata rather than storing video files in the
repository.

## Images: formats, delivery, and performance

- Prefer modern formats such as WebP or AVIF where supported, with suitable
  fallbacks such as JPEG or PNG when required for compatibility or image
  characteristics.
- Resize and compress images for their intended use. Avoid delivering
  unnecessarily large files or retaining redundant delivery copies.
- Where layouts need different image sizes, provide responsive delivery so
  browsers can select an appropriate variant for the viewport and display
  density. Specific dimensions and variant counts are implementation decisions
  and must be validated against actual page requirements.
- Preserve each image's intended aspect ratio and provide intrinsic dimensions
  or an aspect ratio in the rendered layout to reduce layout shifts.
- Prioritize loading for prominent, immediately visible imagery. Defer
  off-screen images where appropriate, and avoid eager loading every gallery
  image.
- Provide meaningful alternative text for informative images; use empty
  alternative text for purely decorative images.

Optimize for visual quality as well as file size. Verify format support, output
quality, responsiveness, and loading behavior in the actual pages before
choosing implementation-specific values.

## Video references and embeds

Use descriptive links to externally hosted videos by default. Consider an
embedded player only for a specific user need and after reviewing the provider's
privacy implications, performance impact, accessibility, terms, and any costs.
Avoid autoplay and unnecessary third-party requests. Do not assume a particular
provider is approved, suitable, or permanently available at no cost.

For either a linked video or an embed, verify that the source and intended
public use are authorized. An external URL or the ability to embed a video does
not establish permission to republish it or approval by the temple.

## Rights and publication approval

Before public publication, verify who owns or controls each image or video and
whether that party has authority to permit the intended use. Confirm applicable
permissions, consent where relevant (including for identifiable people),
attribution requirements, and suitability for public display. Obtain approval
from an authorized temple representative for the specific media and its
intended public use.

Keep media unpublished if ownership, rights, permission, consent, attribution,
or approval is uncertain or disputed. The presence of a file, metadata, or
approval status alone is not evidence that publication is authorized.

## Static-first and cost boundary

Prefer static assets and simple external video references consistent with the
static-first, low-cost architecture. Review any hosting, provider, bandwidth,
privacy, or operational implications before adoption; do not assume a free
tier or unchanged provider terms. Do not introduce a media service or recurring
cost without the appropriate review and approval.

This document defines architecture guidance only. It adds no media-processing
pipeline, responsive-image generation, video embedding, upload system, backend,
CMS, database, dependency, or automated approval workflow.
