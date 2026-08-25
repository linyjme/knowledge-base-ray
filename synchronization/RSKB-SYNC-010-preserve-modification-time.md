---
id: RSKB-SYNC-010
title: How does preserving modification time affect synchronized files?
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
  - Can a synchronized target keep the source timestamp?
  - What timestamp is used when preservation is disabled?
  - Does preserving time control whether a target is overwritten?
keywords: [modification time, source timestamp, transfer completion, preserve timestamp, newer file]
legacy_ids: [FAQ-SYNC-010]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-009]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-010 | How does preserving modification time affect synchronized files?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-064 | Preserve file modification time
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How does preserving modification time affect synchronized files?

## Short answer

Enable **Preserve modification time** to keep the source file's modification time on the synchronized target. If it is disabled, the target's modification time becomes the time when the client finishes the transfer.

This option does not decide whether an existing file is replaced. Overwrite, append, rename, and overwrite-if-newer are separate existing-target choices. When using overwrite-if-newer, confirm that source and target timestamps represent the comparison you intend.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
