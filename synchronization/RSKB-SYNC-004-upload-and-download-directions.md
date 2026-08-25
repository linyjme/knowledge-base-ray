---
id: RSKB-SYNC-004
title: How do sync upload and download directions work?
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
  - Which source path creates a synchronous upload?
  - How do I synchronize from the server to my computer?
  - What determines the direction of a one-way sync?
keywords: [sync upload, sync download, source path, target path, one-way direction]
legacy_ids: [FAQ-SYNC-004]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-002, RSKB-SYNC-003, RSKB-SYNC-013]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-004 | How do sync upload and sync download directions work?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do sync upload and download directions work?

## Short answer

For one-way synchronization, the source path determines the direction. A source on your computer creates a synchronous upload to the server. A source on the server creates a synchronous download to your computer. Select the destination on the other side as the target.

## Authorization and preconditions

Use an account permitted to read the selected source and write the selected target. Identify the authoritative location before setting a one-way direction.

## Exact target and effect

For synchronous upload, the exact computer path is the source and the exact server path is the target. For synchronous download, the server path is the source and the computer path is the target. Post-sync source processing is a separate destructive effect.

## Confirmation

Confirm both displayed paths, the chosen direction, target conflict policy, and any source deletion or move option before creating the task.

## Recovery boundary

Keep a backup or approved recovery path for the authoritative source and any existing target that may be overwritten. Do not enable post-sync source removal without its separate recovery and retention review.

## Post-action verification

Verify that the task list preserves the intended source and target roles. After the first run, check the expected target inventory and ensure the authoritative source changed only when an explicitly reviewed processing option required it.

Upload/download direction is not the same setting as one-way/two-way mode: two-way synchronization exchanges changes between local and server directories. Verify the authoritative side before creating a one-way task. Post-sync source deletion can apply after an upload or download, while the separately documented delayed move-and-delete mode is upload-only; both are destructive options rather than direction settings.
