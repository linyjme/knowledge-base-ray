---
id: RSKB-TROUBLE-010
title: Run the end-to-end troubleshooting workflow
product: raysync
components:
- client-manager
- file-service
- node-scheduler
domain: troubleshooting
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why can an accepted transfer request still leave no usable file at the destination?
- How should support branch when a job is queued, never dispatched, interrupted, or
  apparently complete?
- What proves delivery after creation, execution, and final-state evidence disagree?
- Why can an accepted request leave the destination result unverified?
- How do I distinguish a waiting task from one stopped or failed?
- Why was the request accepted although the destination file is incorrect?
- How can I tell whether an existing job is waiting or failed to dispatch?
keywords:
- end-to-end diagnosis
- created not running
- waiting reason
- stale task state
- file state
- target acceptance
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/faq.md
  section: Common FAQ
  evidence_type: technical-boundary-document
- file: source_file/end-to-end-troubleshooting.md
  section: Raysync end-to-end troubleshooting process
  evidence_type: technical-boundary-document
- file: source_file/troubleshooting-overview.md
  section: General troubleshooting process
  evidence_type: technical-boundary-document
- file: source_file/state-not-updating.md
  section: Task status is not updated
  evidence_type: technical-boundary-document
- file: source_file/transfer-interruption.md
  section: Observation
  evidence_type: technical-boundary-document
- file: source_file/task-waiting.md
  section: What to do if the task keeps waiting
  evidence_type: technical-boundary-document
- file: source_file/transfer-start.md
  section: Observation
  evidence_type: technical-boundary-document
- file: source_file/task-created-not-running.md
  section: The task was created but not run
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Run the end-to-end troubleshooting workflow

## Short answer

Follow the last confirmed successful link: request accepted, task created, dispatched, running progress, terminal state, and target verification. Request accepted does not mean target success, and task creation or a status update is never sufficient delivery evidence.

## Symptoms

The request was rejected; the task is created but not running; it remains waiting; it is stopped or failed; a stale task state differs from current file state; or the interface reports success while target verification fails.

## Checks

Record the same entry, direction, source and destination summary, waiting reason, last state-update time, failure set, and target inventory. Distinguish scheduler non-dispatch from created but not running, resource waiting from connection waiting, stopped from failed, stale task state from file state, and file presence from target verification of count, size, checksum, and readability.

## Interpretation

Failure before creation belongs to parameters, session, permission, or local manager. Created but not running belongs to dispatch or worker preparation. Waiting needs its recorded reason and is not automatically a network fault. Stopped is an intentional terminal state; failed records an error. Terminal task success still requires independent target verification.

## Backup or recovery boundary

Save the original error and target inventory as the recovery baseline. Do not clear a task, delete a record, retry into an existing destination, or overwrite files until the task type, same-name policy, and recoverable target state are confirmed.

## Corrective action

An authorized operator must confirm the exact target task, source, destination, direction, and affected objects. Confirm the intended effect, correct only the first failed link, and perform one small reversible retry without changing other factors.

## Verification

Post-action verification follows the same target through acceptance, creation, dispatch, running progress, terminal state, failure or skipped set, and target verification. Compare count, size, available checksum, and readability before declaring success.

## Evidence to collect

Collect versions, platforms, entry, direction, masked task parameters, status timeline, waiting reason, terminal result, failure set, and redacted target difference. Use `<host>`, `<task>`, `<path>`, and `<account>` placeholders.

## Escalation

Escalate when a minimum task fails, state remains stale after the worker reports a different result, integrity differs, or the same first failing link recurs without a configuration change.
