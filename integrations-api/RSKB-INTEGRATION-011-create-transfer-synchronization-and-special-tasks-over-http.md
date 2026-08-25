---
id: RSKB-INTEGRATION-011
title: 'Create transfer synchronization and special tasks over HTTP'
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
- 'How does a local web API client submit the smallest safe job and follow its final result?'
- 'Which HTTP creation prerequisites apply to a local-copy job between manager-visible paths?'
- 'Why can a successful HTTP creation response still leave a task without a file result?'
keywords:
- 'HTTP task creation'
- 'asynchronous request'
- 'JSON body'
- 'task type'
- 'business result'
- 'task ID'
- 'local web API'
- 'successful creation response'
- 'task without file result'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-036
- RSKB-INTEGRATION-035
source_refs:
- file: source_file/http-task-creation.md
  section: 'Create transport, synchronization and special tasks via HTTP'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Create transfer synchronization and special tasks over HTTP

## Short answer

Select the documented task type and submit only its required fields as JSON. Ordinary transfer, synchronization, local copy, P2P, scheduled P2P, and cluster work have different prerequisites. Request accepted does not mean complete, and task ID does not mean complete.

## Guidance

First prove a read-only query. Record a masked request time and category, inspect the business result in addition to the transport status, save the task ID, and query the resulting direction, paths, trigger, and state. HTTP 200 does not mean complete. Final acceptance requires the task's terminal state, failure set, and target-file evidence.

## Authorization and target

Only an authorized operator may act. Confirm the exact target manager, caller, documented method, task or setting, affected scope, and installed contract. Store secrets outside the request example and use `<host>`, `<token>`, and `<path>`; never record a real account, password, access key, certificate, device or group identifier, port, endpoint, or full local path.

## Effect and confirmation

Confirm the documented HTTP method and task type, required JSON fields, direction, source and destination, authentication boundary, trigger, and type-specific dependency. The intended effect is one correctly described asynchronous task record.

## Recovery boundary

Keep the masked creation response and task ID. If the created type, direction, paths, or trigger is wrong, stop new control calls and use the documented task-control article; do not repeat creation until the original record is located.

## Verification

Check transport and business results, then query the created task ID for type, paths, dispatch, progress, terminal state, and failures. Complete acceptance with target count, size, checksums, and readability.
