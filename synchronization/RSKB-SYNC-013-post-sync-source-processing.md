---
id: RSKB-SYNC-013
title: Can Raysync move or delete source files after synchronization?
product: raysync
components: [user-portal, desktop-client, browser-plugin]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Can completed synchronization clear the original source content?
  - How can uploaded source files be moved to an archive path and retained?
  - What is the difference between deleting all source folders and keeping empty structure?
keywords: [delete source, move source, preserve directory structure, never delete, retention]
legacy_ids: [FAQ-SYNC-013]
safety_tags: [authorization, destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-004, RSKB-SYNC-008, RSKB-SYNC-015]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-013 | Can Raysync move or delete source files after synchronization?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-060 | Deleting source files after synchronization complete (Delete al the source directorys and file )
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-061 | Deleting source files after synchronization complete (Reserve source directory structure)
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-062 | Preserve directory structure when deleting source files
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-073 | After synchronization is completed, the source files are moved and deleted
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can Raysync move or delete source files after synchronization?

## Short answer

Yes, through explicit post-sync processing. One mode can delete all source directories and files after an upload or download. Another deletes the files but preserves the empty source directory structure. A separate upload-only mode can move uploaded source files to another path after a delay and delete them after a configured retention period.

## Authorization and preconditions

Only enable source processing when policy and account permissions allow changes to the exact source. Require a successful synchronization result, an accessible archive path where applicable, and a reviewed retention or **Never Delete** value.

## Exact target and effect

Identify the exact source tree and choose one effect: delete all source content, delete files while retaining empty directories, or move uploaded files to the exact archive path and later delete them under the configured retention period.

## Confirmation

Confirm the source, destination, archive path, completion condition, retention interval, directory-structure choice, and backup policy before enabling the option.

## Recovery boundary

Keep a verified backup or approved source-recovery path before any delete mode. For move-and-delete, verify the archive before retention can expire; **Never Delete** retains moved files but does not replace backup verification.

## Post-action verification

Verify the synchronization terminal result and target acceptance first. Then inspect the exact source and archive paths to confirm that only the selected files moved or were removed and that the requested directory structure and retention state remain.

These options are destructive and are different from synchronized target deletion. Before enabling them, confirm that policy and account permissions allow source changes, then verify the destination, successful transfer result, retention interval, and backup policy. In the documented 8.1.8.7 plug-in behavior, **Never Delete** (represented as `0` days in the detailed guide) retains moved files in the archive path.

## Availability

The feature-matrix entries for deleting all source content, retaining source directory structure, and moving then deleting source files have the same boundary: Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
