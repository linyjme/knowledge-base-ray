---
id: RSKB-SYNC-015
title: How is source directory structure preserved during synchronization?
product: raysync
components: [user-portal, desktop-client]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Will the top-level source folder appear at the synchronization target?
  - What does transferring only source files and folders do to the first directory layer?
  - Can an upload retain the complete hierarchy under the source directory?
keywords: [directory structure, source folder, top-level folder, complete hierarchy, transfer source files only]
legacy_ids: [RS-FEAT-063, RS-FEAT-074]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-012, RSKB-SYNC-013]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-063 | Transfer only files and folders in the source directory
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-074 | Reserve the complete structure of the source directory when uploading to the target
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How is source directory structure preserved during synchronization?

## Short answer

The feature matrix documents two related source-layout behaviors. **Transfer source files only** transfers the files and folders inside the selected source directory without transferring that first-layer source folder itself. When that option is not used, Raysync can preserve the complete source directory structure while uploading to the target.

These choices affect the relative layout at the target; they do not imply that arbitrary source directory levels can be combined. They are also distinct from the destructive post-sync option that preserves empty source directories while deleting the files within them.

## Availability

Both source-layout feature entries have the same synchronization boundary: Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB. The equivalent transfer-domain structure entry also supports SMB, so its edition availability is broader.
