---
id: RSKB-INTEGRATION-006
title: 'Query monitor and control tasks from the CLI'
product: raysync
components:
- client-manager
- cli
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
- 'How do I safely start or stop the correct managed task from the command line?'
- 'Why can leaving continuous CLI monitoring have no effect on the running job?'
- 'What should be saved before removing task records in a filtered batch?'
keywords:
- 'CLI task query'
- 'continuous monitoring'
- 'start stop'
- 'task ID'
- 'batch removal'
- 'task record'
- 'command-line tool'
legacy_ids: []
safety_tags: 
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-query-monitor-control.md
  section: 'Synchronous command line task query, monitoring and control'
  evidence_type: technical-boundary-document
- file: source_file/task-delete-vs-file-delete.md
  section: 'Will deleting the synchronization command line task delete the files?'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Query monitor and control tasks from the CLI

## Short answer

Query first, confirm the current task ID, type, state, and update time, then issue one supported control operation and query again. Leaving continuous monitoring does not stop the task. Save failures and target evidence before removal; deleting a task record does not delete remote files.

## Guidance

A list is a filtered snapshot, task details identify the current state, and monitoring repeatedly refreshes it. Group or space results are not completion evidence. Stop may pass through a transition, so do not immediately submit the opposite operation. Before any batch removal, export the selected list, confirm the exact filter, record the recovery boundary, and use a small reversible scope.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm the current task ID, type, state, and update time before start, stop, or record removal. The intended effect is one state transition or one reviewed cleanup scope; leaving monitoring has no task-control effect.

## Recovery boundary

Keep the current task details, failure evidence, and exported batch list before control. Wait for a stop transition to settle, and never broaden a failed single-task action into remove-all; deleting the record cannot recover or delete remote files.

## Verification

Re-query the same task ID after control and compare the new state and update time. Before removal, close the failure and target checks; after removal, verify only the record scope because remote-file state is a separate operation.
