---
id: RSKB-FILE-012
title: What happens when the recycle bin is emptied?
product: raysync
components: [user-portal, admin-portal]
domain: file-management
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Are files recoverable after the recycle bin is emptied?
  - Does emptying a group recycle bin permanently delete files?
  - What should I check before asking to empty a recycle bin?
keywords: [empty recycle bin, permanent deletion, data loss, recover file, retained files]
legacy_ids: [FAQ-FILE-012]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-005, RSKB-FILE-011]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-012 | What happens when the recycle bin is emptied?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-015 | Support expiration file cleaning and setting recycle bin path
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What happens when the recycle bin is emptied?

## Short answer

Emptying a personal or group recycle bin permanently removes the selected retained files instead of recovering them. The documented empty and recover controls are on administrator pages, so ask about recovery before the bin is emptied.

## Data-loss warning

Emptying the recycle bin is not the same as a normal delete that first retains an item. Confirm the correct personal user or group library and the selected files before requesting the action. Content already removed this way cannot be recovered through the documented recycle-bin workflow.

The feature matrix lists expiration-file cleaning and recycle-bin path configuration for SMB, Enterprise, Cloud, and Multiple Spaces. It does not make emptying reversible.
