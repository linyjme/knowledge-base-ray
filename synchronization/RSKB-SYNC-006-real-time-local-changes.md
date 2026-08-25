---
id: RSKB-SYNC-006
title: Can Raysync synchronize local changes in real time?
product: raysync
components: [desktop-client]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Can a changed local file upload without waiting for the schedule?
  - Does real-time synchronization also download server changes?
  - Which storage source supports immediate sync updates?
keywords: [real-time sync, upload-only, local storage, modified file, schedule]
legacy_ids: [FAQ-SYNC-006]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-005, RSKB-SYNC-007]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-006 | Can Raysync synchronize local changes in real time?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-076 | Supports real-time sync (Upload only)
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can Raysync synchronize local changes in real time?

## Short answer

Yes, but documented real-time synchronization is upload-only and applies to files from local storage. When a corresponding local file changes, Raysync can upload the modified file in real time instead of waiting for the next normal schedule.

Real-time synchronization was introduced in version 8.1.8.3. The evidence does not establish real-time download, two-way real-time synchronization, or real-time operation with object storage. The normal client, global sync enablement, and account-permission prerequisites still apply.

## Availability

Supported in Enterprise and Cloud; unsupported in SMB and Multiple Spaces.
