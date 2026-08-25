---
id: RSKB-SECURITY-009
title: Understand video-preview watermarks
product: raysync
components:
- user-portal
domain: security
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why is a watermark shown while I preview a video?
- What information can appear in a video-preview overlay?
- Can an end user remove a security watermark from preview playback?
keywords:
- video preview
- watermark
- image overlay
- security
- Why is a watermark displayed during video preview?
- Set video playback watermark
- Raysync
legacy_ids:
- FAQ-SECURITY-013
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-013 | Why is a watermark displayed during video preview?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-114 | Set video playback watermark
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand video-preview watermarks

## Short answer

The administrator has enabled the video online-preview watermark. Raysync supports an uploaded watermark image and a configured display position. The watermark is therefore expected portal behavior for protected video preview, not a modification you can remove from the user portal.

## Version differences

Video preview watermarking appears in the release history from version 5.0.7.8. Both the legacy and 8.1.8.0 and later guides document an administrator-supplied watermark image and display position. The end-user preview effect is unchanged in the available documentation.

## Important notes

Do not interpret the watermark as evidence that the source video file itself has been altered; the source describes it specifically as online-preview watermark configuration. If placement prevents an authorized review, contact the administrator, who controls the watermark image and location.

The documented setting applies to online video preview, not to every file shown in the user portal.

## Related documented boundaries

- **Set video playback watermark:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
