---
id: RSKB-INTEGRATION-009
title: 'Run cluster tasks from the CLI'
product: raysync
components:
- client-manager
- cli
- node-scheduler
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
- 'How does a command-line tool distinguish a cluster batch waiting for workers from partial failure?'
- 'What should be verified before submitting a small cluster upload or download batch?'
- 'Why do coordination, worker, subtask, and batch output need separate cluster checks?'
keywords:
- 'CLI cluster task'
- 'coordination service'
- 'batch status'
- 'subtask results'
- 'partial failure'
- 'directed retry'
- 'command-line tool'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-cluster.md
  section: 'Synchronization command line cluster task guide'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Run cluster tasks from the CLI

## Short answer

Verify the approved coordination dependency, direction, paths, trigger, and batch scope, then submit a small batch. Creation or coordination connectivity does not prove completion. Inspect the batch and required subtasks, preserve the partial-failure set, and verify the target.

## Guidance

Use a unique batch name but associate later actions by the returned task ID. If creation fails, check coordination and authentication; if the batch waits, check scheduling and execution units; if only some objects fail, retry only the confirmed failed scope. Acceptance includes required subtask terminal states, failed objects, target count and size, checksums, and readable deliverables.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm the approved coordination dependency, direction, batch scope, trigger, and required execution units. The intended effect is a cluster batch whose required subtasks write the reviewed targets, not merely a created batch record.

## Recovery boundary

Retain coordination and subtask evidence before retry. If only part of the batch fails, limit recovery to the confirmed failed objects; if workers never register, correct scheduling or dependency readiness without resubmitting the entire batch.

## Verification

Require the cluster batch terminal state and every required subtask result. Reconcile the partial-failure set, retry scope, target count and size, key checksums, and readable output rather than accepting coordinator health or one successful subtask.
