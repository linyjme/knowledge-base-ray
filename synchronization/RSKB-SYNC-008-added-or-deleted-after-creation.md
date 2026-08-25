---
id: RSKB-SYNC-008
title: What happens when files are added or deleted after task creation?
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
  - Will later sync runs notice a new source file?
  - Can deleting one synchronized copy remove the copy on the other side?
  - Are source updates and synchronized deletion controlled together?
keywords: [added file, deleted file, synchronized deletion, source update, target deletion]
legacy_ids: [FAQ-SYNC-008]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-007, RSKB-SYNC-013]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-008 | What happens when files are added or deleted after a sync task is created?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-058 | Aadd files/folders synchronously
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-059 | Delete files/folders synchronously
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What happens when files are added or deleted after task creation?

## Short answer

New or modified source files can be picked up by later runs when source-update synchronization is enabled. Deletion is a separate setting. If **Delete target file synchronously when source deleted** is enabled, deleting a file in one synchronized path also deletes the corresponding file in the other path.

Synchronized deletion is destructive: it can remove the remaining copy on the other side. It does not support the root directory and cannot be combined with **Transfer source files only**. It is also distinct from post-sync processing that deletes or moves source content after a completed run.

## Availability

The feature-matrix entries for synchronous addition and deletion have the same boundary: Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
