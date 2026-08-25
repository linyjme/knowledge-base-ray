---
id: RSKB-SYNC-007
title: Can a sync task transfer only added or modified files?
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
  - How can I avoid synchronizing unchanged source files again?
  - Will a later run pick up newly added source content?
  - Is source-update handling the same as real-time sync?
keywords: [added files, modified files, source update, incremental sync, unchanged files]
legacy_ids: [FAQ-SYNC-007]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-005, RSKB-SYNC-006, RSKB-SYNC-008]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-007 | Can a sync task transfer only files that were added or modified?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-075 | Synchronize when source files are updated
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can a sync task transfer only added or modified files?

## Short answer

Yes. Enable source-update synchronization so later runs transfer files that have been added or modified without performing unnecessary duplicate synchronization of unchanged files.

This control determines which source content qualifies for another run; the configured schedule still determines when the task runs. It is separate from real-time upload. The source-update evidence does not include deletion, which is controlled by the distinct synchronized-deletion option.

## Version evidence conflict

The FAQ source says version 6.8.8.0, while the feature matrix says 6.6.8.0. The supplied sources do not resolve that discrepancy. Confirm the feature in the deployed Raysync version instead of treating either introduction version as authoritative.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
