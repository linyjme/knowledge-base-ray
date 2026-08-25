---
id: RSKB-SYNC-003
title: Should I choose one-way or two-way synchronization?
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
  - Which sync mode should I use for one authoritative location?
  - When is bidirectional synchronization appropriate?
  - Do changes need to travel in one direction or both directions?
keywords: [one-way sync, two-way sync, bidirectional, authoritative copy, sync mode]
legacy_ids: [FAQ-SYNC-003]
safety_tags: [destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-004, RSKB-SYNC-008, RSKB-SYNC-009]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-003 | Should I choose one-way or two-way synchronization?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-057 | Unidirectional and bidirectional synchronization
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Should I choose one-way or two-way synchronization?

## Short answer

Choose one-way synchronization when one location is authoritative and changes should travel only from that source to the target. Choose two-way synchronization when both the local and server directories may change and Raysync should maintain consistency between them.

## Authorization and preconditions

Use synchronization only with permission to read and change both selected locations. Establish whether one side is authoritative or both sides may legitimately change before selecting the mode.

## Exact target and effect

One-way mode propagates changes from the exact source to the exact target. Two-way mode can carry changes in both directions and first uploads local files before downloading server files; it can therefore affect content on both sides.

## Confirmation

Confirm the selected local and server directories, mode, same-name policy, and synchronized-deletion setting before creating or enabling the task.

## Recovery boundary

Preserve an approved backup of valuable content on both sides before two-way synchronization or destructive conflict behavior. Do not use mode selection as a substitute for a recovery plan.

## Post-action verification

Verify the saved mode and both paths in the task list, then check the first completed run on both locations for the expected direction, final files, and absence of unintended deletions.

Two-way mode first uploads local directory files to the server directory and then downloads server directory files to the local directory. This mode choice is distinct from choosing upload or download for a one-way task. Because two-way synchronization can propagate changes from either side, review synchronized deletion and same-name conflict behavior before using it with valuable data.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
