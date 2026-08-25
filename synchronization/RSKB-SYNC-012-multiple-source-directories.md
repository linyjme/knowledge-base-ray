---
id: RSKB-SYNC-012
title: Can I select multiple source directories for one sync task?
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
  - Can one synchronization job use several source folders?
  - Why is my selection of folders from different levels rejected?
  - Must multiple sync source paths be at the same directory level?
keywords: [multiple source directories, same level, source paths, folder selection, sync task]
legacy_ids: [FAQ-SYNC-012]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-002, RSKB-SYNC-015]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-012 | Can I select multiple source directories for one sync task?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-070 | Support for synchronizing multiple source directories
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can I select multiple source directories for one sync task?

## Short answer

Yes. Raysync supports selecting multiple source paths at the same directory level for one sync task. Set the target and direction as for a single-source task.

The evidence does not support combining arbitrary unrelated directory levels or provide a workaround for a rejected selection. Also review **Transfer source files only**: enabling it transfers the contents without the first-layer source folder, while disabling it transfers the directory's files and folders with their structure.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
