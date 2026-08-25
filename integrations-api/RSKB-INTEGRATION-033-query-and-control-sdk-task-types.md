---
id: RSKB-INTEGRATION-033
title: 'Query and control SDK task types'
product: raysync
components:
- client-manager
- sdk
domain: integrations-api
access_level: support
audience:
- developer
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- 'How does one client library control flow distinguish ordinary, synchronization, peer-to-peer, and cluster jobs?'
- 'What distinguishes an accepted start or stop callback from the task''s final state?'
- 'Which scope must be exported before cleaning a task type in a batch?'
keywords:
- 'SDK task control'
- 'task type'
- 'start callback'
- 'stop transition'
- 'batch cleanup'
- 'task details'
- 'client library'
- 'peer-to-peer'
legacy_ids: []
safety_tags: 
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/task-control.md
  section: 'SDK task query and control'
  evidence_type: technical-boundary-document
- file: source_file/task-capabilities.md
  section: 'Common, synchronization and cluster task capabilities'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Query and control SDK task types

## Short answer

Obtain the current task ID, query its type, direction, paths, and state, then request one start, stop, delete, or type-scoped cleanup and query again after its callback. Immediate return or an accepted callback is not the final task result.

## Guidance

Ordinary transfer emphasizes one delivery; synchronization also requires trigger and policy evidence; cluster work requires batch and subtask results; P2P adds peer and channel stages. Export the selected list before batch cleanup and inspect partial failures. Deleting a task record does not delete remote files, and a stopped transition is not a safe moment to submit the opposite action.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm the current task ID and whether its type is ordinary, synchronization, peer-to-peer, local-copy, or cluster before a query, start, stop, delete, or type-scoped cleanup. The intended effect is one reviewed state or record change.

## Recovery boundary

Export the selected task list before batch cleanup and retain failures and target evidence. Wait for callbacks and stop transitions; never broaden a single-task failure into type-wide cleanup, and do not treat record deletion as remote-file deletion.

## Verification

Re-query the same ID after control and reconcile callbacks, state, progress, and failures. Add next-trigger evidence for synchronization, peer and channel evidence for P2P, local target checks for copy, and required subtask results for cluster.
