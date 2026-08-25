---
id: RSKB-INTEGRATION-012
title: 'Start stop modify and delete tasks over HTTP'
product: raysync
components:
- client-manager
- http-api
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
- 'How can I stop and modify an HTTP-managed task without racing a transitional state?'
- 'Which task-control evidence should be retained before removing records while preserving remote files?'
- 'Why should an integrator avoid an all-tasks control call as a connectivity test?'
keywords:
- 'HTTP task control'
- 'start task'
- 'stop transition'
- 'modify task'
- 'delete record'
- 'batch partial failure'
- 'local web API'
- 'remove task records'
- 'keep remote files'
legacy_ids: []
safety_tags: 
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-037
- RSKB-INTEGRATION-035
source_refs:
- file: source_file/http-task-control.md
  section: 'Start, stop, modify and delete tasks via HTTP'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Start stop modify and delete tasks over HTTP

## Short answer

Read the current task type, state, and update time before one control operation. After start, stop, or modify, wait through transitions and query again. Before delete, retain failures and target evidence. Deleting a task record does not delete remote files.

## Guidance

Confirm which fields may change online and which apply only to a later trigger. Batch calls may contain partial failures, so inspect each selected task instead of trusting an overall message. An all-tasks operation is not a connectivity probe. Source cleanup and remote-object deletion are separate effects that require their own explicit authorization.

## Authorization and target

Only an authorized operator may act. Confirm the exact target manager, caller, documented method, task or setting, affected scope, and installed contract. Store secrets outside the request example and use `<host>`, `<token>`, and `<path>`; never record a real account, password, access key, certificate, device or group identifier, port, endpoint, or full local path.

## Effect and confirmation

Confirm one current task ID and whether the intended effect is start, stop, a documented field update, or task-record deletion. Re-read state after every write and inspect per-task results for a batch.

## Recovery boundary

Preserve the old task configuration, current state, failures, and target evidence. Wait through stop transitions, avoid all-task calls as probes, and recover a mistaken field only through the documented update contract. Deleting a task record does not delete remote files.

## Verification

Query the same task after start, stop, or update and confirm the expected state and effective fields. After deletion, verify the selected record scope and separately retain remote-file evidence because file deletion is not the effect.
