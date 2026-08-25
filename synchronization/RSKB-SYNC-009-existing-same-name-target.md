---
id: RSKB-SYNC-009
title: How does a sync task handle an existing same-name target?
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
  - Which conflict option keeps an existing target file?
  - Can synchronization append incoming content instead of replacing it?
  - How does overwrite-if-newer differ from unconditional overwrite?
keywords: [same-name target, overwrite target, append, rename, overwrite if source newer]
legacy_ids: [FAQ-SYNC-009]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-010]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-009 | How does a sync task handle an existing same-name target?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-065 | Overwriting existing files
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-066 | Appending existing files
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-067 | Rename when file exists
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-068 | Overwrite when the source file is newer
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How does a sync task handle an existing same-name target?

## Short answer

The existing-target setting provides four distinct, non-equivalent choices:

## Authorization and preconditions

Use an account permitted to modify the exact synchronization target. Inspect the existing target and incoming source, including names, modification times, and whether object storage is involved, before selecting a policy.

## Exact target and effect

Apply one reviewed policy to the exact same-name target: overwrite replaces it, append modifies it, rename retains it and changes the incoming name, and overwrite-if-newer replaces it only when the source modification time is newer.

## Confirmation

Confirm the exact source, target, selected policy, expected resulting name, and modification-time basis before saving or running the task.

## Recovery boundary

Preserve the existing target through an approved backup or recovery path before overwrite or append. Rename is the documented choice that retains the prior same-name target, but the renamed result still requires verification.

## Post-action verification

After the run, verify the target name, count, size, modification time, and business readability. For append, verify the resulting content boundary; for overwrite, confirm that only the reviewed target was replaced.

- **Overwrite target file** replaces the existing target content unconditionally.
- **Append to target file** adds incoming content to the end of the target; it is unavailable for object storage.
- **Rename file** keeps the existing target and, for one-way sync, renames the incoming source, such as `test(1)`.
- **Overwrite if source newer** replaces the target only when the incoming file's modification time is newer.

Overwrite can destroy prior target content, while append modifies that content rather than creating an independent copy. Modification-time preservation is a separate control and does not itself select any of these conflict behaviors.

## Availability

All four feature-matrix conflict choices have the same boundary: Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
