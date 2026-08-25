---
id: RSKB-INTEGRATION-032
title: 'Use SDK local-copy operations'
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
- 'How can an SDK local-copy task avoid nested source and destination directories?'
- 'What should be accepted before post-copy source deletion is allowed?'
- 'Why must local replication wait for worker final state after creation succeeds?'
keywords:
- 'SDK local copy'
- 'local replication'
- 'nested paths'
- 'source deletion'
- 'worker state'
- 'target acceptance'
- 'client library'
legacy_ids: []
safety_tags: 
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/local-copy.md
  section: 'Local copy capability'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use SDK local-copy operations

## Short answer

Use SDK local copy only between locally visible storage paths. Confirm readable source, writable destination, non-nested paths, capacity, and an explicit overwrite, skip, or documented continuation policy. A created record still requires worker and target acceptance.

## Guidance

Begin with one small file and record the expected destination. Do not treat append as resume. If source post-processing is enabled, it must occur only after all required objects pass; back up and verify the target before accepting source disappearance. Check terminal state, failures, target count, size, checksums, and readability.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm two locally visible non-nested paths, destination capacity, conflict mode, verification, and any source post-processing. The client library creates a manager task whose worker performs local copy without remote file-service login.

## Recovery boundary

Preserve destination content before overwrite and the source before optional deletion. If nesting, file use, space, or conflict errors appear, stop the worker task and correct one condition before retrying the same small scope.

## Verification

Require worker terminal state and complete failures, then compare local source and destination count, size, checksums, and readability. Accept source post-processing only after every required destination object passes.
