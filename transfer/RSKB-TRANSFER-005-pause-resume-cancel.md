---
id: RSKB-TRANSFER-005
title: How do I pause, resume, or cancel a transfer task?
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
  - How can I temporarily stop and restart client work?
  - Are Delete and Cancel proven to mean the same thing?
  - What should I check before removing an active task?
keywords: ["pause task", "resume task", "cancel task", "delete task"]
legacy_ids: ["FAQ-TRANSFER-005"]
safety_tags: ["authorization", "destructive-operation"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-004", "RSKB-TRANSFER-006"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-005 | How do I pause, resume, or cancel a transfer task?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)
    evidence_type: feature-matrix
  - file: source_file/task-recovery-stop-delete.md
    section: Task resume, stop and delete FAQ
    evidence_type: technical-boundary-document
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I pause, resume, or cancel a transfer task?

## Short answer

In the client list, Pause temporarily stops a task and Start resumes a paused task. The client source also documents Delete, but does not prove that Delete and Cancel have identical effects.

## Authorization and preconditions

Act only on a task owned by or delegated to the signed-in account. Identify the exact task, current state, source, target, and control label before pausing, starting, cancelling, or deleting a record.

## Exact target and effect

Pause temporarily stops the selected task and Start resumes that paused task. Delete is documented for the client record, but the supplied evidence does not establish that it has the same cleanup effect as Cancel or that either removes source or target files.

## Confirmation

Confirm the exact task identifier, displayed state, and literal control before acting. Do not infer cleanup scope from a similar label or from another transfer mode.

## Recovery boundary

Preserve source and target content and any partial result until the task reaches a clear state. If cleanup scope is not documented for the active control, stop and retain the record rather than assuming deletion is reversible.

## Post-action verification

Refresh the task list and verify the selected task's new state. Check both endpoints and the target result before treating pause, resume, cancel, or record removal as complete.

The supplied sources conflict on the introduction version for web pause and cancel: FAQ-TRANSFER-005 says 8.1.8.1, while RS-FEAT-027 gives 6.3.8.0 for the HTTP web capability that includes those controls. The conditions behind the difference are unclear, so do not select an introduction version. The current applicable version 8.1.8.7 supports web pause and cancel.

Do not infer that removing a task record deletes source or target files. Confirm the exact control and cleanup scope, wait for a clear final state, and verify both ends.

For the HTTP web capability that supplies these web controls, **Supported in SMB, Enterprise, and Multiple Spaces; unsupported in Cloud.** This edition statement applies to RS-FEAT-027 and must not be generalized to every Cloud transfer workflow.
