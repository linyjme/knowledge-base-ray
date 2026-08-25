---
id: RSKB-FILE-011
title: Can a deleted file be recovered from the recycle bin?
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
  - How can I restore a deleted personal file?
  - Can an administrator recover a group file from the recycle bin?
  - Why is a deleted file not recoverable?
keywords: [recycle bin, recover file, restore deletion, personal file, group file]
legacy_ids: [FAQ-FILE-011]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-005, RSKB-FILE-012]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-011 | Can a deleted file be recovered from the recycle bin?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-015 | Support expiration file cleaning and setting recycle bin path
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can a deleted file be recovered from the recycle bin?

## Short answer

Yes, if the deletion policy moved the item to a recycle bin and the bin has not been emptied. The documented recovery controls are administrator controls for a personal user's recycle bin or a group file library's recycle bin, so ask your administrator to recover the selected item.

Recovery is not available when the file was deleted directly, has already been removed by emptying the recycle bin, or was overwritten rather than recycled. An isolated file is also different: a security control moved it to the isolation zone.

The feature matrix lists expiration-file cleaning and recycle-bin path configuration for SMB, Enterprise, Cloud, and Multiple Spaces. It does not replace the recovery preconditions above.
