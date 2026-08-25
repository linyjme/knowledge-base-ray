---
id: RSKB-TRANSFER-006
title: Does Raysync resume an interrupted transfer?
product: raysync
components: [user-portal, desktop-client]
domain: transfer
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Will my stopped client task continue from the breakpoint when I restart it?
  - Why did an older web upload begin again after Start or Retry?
  - Is breakpoint resume behavior the same in every transfer mode?
keywords: ["breakpoint resume", "interrupted transfer", "web upload", "client task"]
legacy_ids: ["FAQ-TRANSFER-006", "RS-FEAT-034"]
safety_tags: ["authorization", "destructive-operation"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-005", "RSKB-TRANSFER-012"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-006 | Does Raysync resume an interrupted transfer from where it stopped?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-034 | Support breakpoint resume in the process of file transfer
    evidence_type: feature-matrix
  - file: source_file/resume.md
    section: Does ordinary upload/download support resuming?
    evidence_type: technical-boundary-document
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Does Raysync resume an interrupted transfer?

## Short answer

Web upload breakpoint resume is documented from version 5.0.8.8. In the current client task list, use **Start** for a paused task and **Retry** when available for a failed task. Use of those controls does not establish the byte continuation point for client work. This article applies to version 8.1.8.7.

## Authorization and preconditions

Use Start or Retry only for the exact authorized task. Confirm its paused or failed state, an unchanged readable source, the expected target, usable temporary content, and support from the active storage backend.

## Exact target and effect

Start continues a paused task and Retry resubmits an eligible failed task. Neither control proves the byte offset, authorizes overwrite, or authorizes deletion of source or target data.

## Confirmation

Confirm the task identity, source version, target state, same-name policy, and displayed control before acting. Do not retry a stale task against a changed source or uncertain destination.

## Recovery boundary

Preserve source content and any partial target until verification closes. If continuation conditions are not evidenced, retain the partial result and use a reviewed clean target rather than assuming byte-level recovery.

## Post-action verification

Verify the task reaches its documented terminal result, then compare target count, size, checksum where available, and business readability. A restarted process alone is not proof of resumed or completed content.

Do not promise identical behavior for every transfer mode, protocol, or conflict condition. Resume **does not authorize overwrite** of a target and **does not authorize delete** of source or destination data. Breakpoint resume is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**

Continuation also depends on the task policy, an unchanged source, usable target temporary content, and support from the active storage backend. If those conditions are not evidenced, retry from a reviewed clean target instead of assuming byte-level continuation.
