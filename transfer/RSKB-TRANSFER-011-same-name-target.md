---
id: RSKB-TRANSFER-011
title: What happens when a target file has the same name?
product: raysync
components: [desktop-client]
domain: transfer
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Which conflict policy preserves existing and incoming content?
  - When will incoming content replace an older destination?
  - What is the data-loss risk of overwrite?
keywords: ["same-name target", "overwrite target", "append file", "rename incoming"]
legacy_ids: ["FAQ-TRANSFER-011", "RS-FEAT-048"]
safety_tags: ["authorization", "destructive-operation"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-010", "RSKB-TRANSFER-012"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-011 | What happens when a target file has the same name?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-048 | Support rename file when the targe file already exists
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What happens when a target file has the same name?

## Short answer

Choices include Overwrite target file, Overwrite if source newer, Append to target file, and Rename file. Rename preserves the existing target.

## Authorization and preconditions

Use only an account permitted to change the exact destination. Inspect the incoming source, existing target, names, modification times, and expected content before choosing a same-name policy.

## Exact target and effect

Overwrite replaces the selected target, overwrite-if-newer replaces it only when the source is newer, append modifies its content, and rename retains the existing target while giving the incoming object another name.

## Confirmation

Confirm the exact source, destination, selected conflict policy, expected resulting name, and modification-time basis before starting the transfer.

## Recovery boundary

Preserve the existing target through an approved backup or recovery path before overwrite or append. Rename retains the prior target but still requires enough capacity and verification of both objects.

## Post-action verification

Verify the final target names, count, sizes, modification times, checksums where available, and business readability. Confirm that only the reviewed same-name target was modified or replaced.

**Data-loss warning:** overwrite replaces target content. Confirm the policy first. Rename-on-existing-target is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
