---
id: RSKB-FILE-007
title: Which files can I preview online?
product: raysync
components: [user-portal, desktop-client]
domain: file-management
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Which image and document formats can Raysync preview?
  - Can I preview video or audio without downloading it?
  - Does my Raysync edition include CAD preview?
keywords: [online preview, document preview, image preview, media preview, CAD preview]
legacy_ids: [FAQ-FILE-007]
safety_tags: [license-control]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-003, RSKB-FILE-016]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-007 | Which files can I preview online?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-013 | Support online preview of files, pictures and videos
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-014 | Support online preview of CAD file (Additional paid for Enterprise)
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Which files can I preview online?

## Short answer

Select a file name to open its preview. The user guide lists images (`png`, `jpg`, `gif`, `jpeg`, `bmp`, `ico`, `svg`), documents (`pdf`, `doc`, `docx`, `ppt`, `pptx`, `xls`, `xlsx`, `csv`), video (`mp4`, `avi`, `mov`, `mxf`, `mpg`), and audio (`aac`, `aiff`, `aif`, `m4a`, `mp3`, `WAV`).

## Requirements and limits

Except for PDF, Office-file preview requires a separate service installed by the administrator. Some video and audio files require the client.

For a share-download link with **Allow Downloaded** disabled, web recipients cannot preview or download. Client recipients can preview but cannot download.

Regular online preview of files, pictures, and videos is marked unsupported for SMB and supported for Enterprise, Cloud, and Multiple Spaces. CAD preview has the same matrix availability, but its feature label states that it requires an additional payment for Enterprise. Do not assume CAD preview is included merely because regular preview is available.
