---
id: RSKB-INTEGRATION-030
title: 'Handle SDK callbacks asynchronous results and timeouts'
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
- 'How should client library handlers copy callback arrays without blocking the receiving thread?'
- 'What should happen after a wait deadline expires but the original task may still exist?'
- 'Which callback data must be copied before the SDK returns from the handler?'
keywords:
- 'SDK callback'
- 'asynchronous result'
- 'timeout'
- 'user data'
- 'receive thread'
- 'task correlation'
- 'client library'
legacy_ids: []
safety_tags: 
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/callback-async-results.md
  section: 'SDK callbacks and asynchronous results'
  evidence_type: technical-boundary-document
- file: source_file/callback-timeout.md
  section: 'SDK callback did not arrive or the wait timed out'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Handle SDK callbacks asynchronous results and timeouts

## Short answer

Register callbacks and stable user data before the first request, correlate work by task ID, copy callback-owned arrays and strings immediately, and enqueue only lightweight processing from the receive thread. A callback does not mean complete unless it carries the required terminal evidence.

## Guidance

Do not block, perform long I/O, wait for the same request, or access destroyed objects in a callback. On timeout, do not immediately resubmit: inspect connection-close events and query the original task first to avoid duplicates. Preserve request time, expected callback category, deadline, masked task correlation, callback time, final state, and failure details; never retain function pointers or raw logs.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm callback registration order, stable user data, task correlation, receive-thread constraints, and the expected callback category and deadline. The intended effect is asynchronous result handling without blocking or duplicate submission.

## Recovery boundary

On timeout or connection close, stop new requests through the old handle and query the original task before resubmission. Copy callback-owned arrays and strings before return; do not wait for the same request or access destroyed data.

## Verification

Verify a directory query or small-file callback chain, masked request and callback times, original task ID, terminal state, and failure list. A callback does not mean complete; target evidence remains a separate acceptance step.
