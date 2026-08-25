---
id: RSKB-INTEGRATION-024
title: 'Validate rayfile-c output logs callbacks and exit results'
product: raysync
components:
- cli
- file-service
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
- 'Which result should automation trust when a direct-file-client process exits but the destination remains incomplete?'
- 'How should a direct-file-client receiver correlate duplicate callbacks after a timeout retry?'
- 'Which log details must be redacted before a rayfile-c failure is escalated?'
keywords:
- 'rayfile-c output'
- 'exit status'
- 'callback'
- 'log redaction'
- 'automation result'
- 'SSRF'
- 'direct file client'
- 'idempotent receiver'
- 'duplicate callback'
- 'callback timeout retry correlation'
legacy_ids: []
safety_tags:
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-output-validation.md
  section: 'rayfile-c output, log, callback and exit results'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Validate rayfile-c output logs callbacks and exit results

## Short answer

Treat console output, exit result, callback delivery, and target acceptance as separate evidence. A callback does not mean complete and process exit does not mean complete. Automation should fail when the documented result, per-object outcomes, or target verification is incomplete.

## Guidance

Send callbacks only to an administrator-approved allowlist. Reject unknown destinations and targets that resolve to local management services or cloud metadata; otherwise a callback option can become an SSRF path. The callback receiver must be idempotent, recognize a duplicate callback, and correlate timeout retry delivery without repeating a business effect. Never include tokens, accounts, full requests, file paths, contents, or raw logs in the callback.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm which direct file client result, object list, and callback event represent the intended effect. Callback delivery notifies an external process; it neither validates file integrity nor changes a failed transfer into success.

## Recovery boundary

A callback failure or timeout retry must not delete source content and must not change success from failure or incomplete to successful. Preserve the original command result and target evidence; retry notification only through the receiver's idempotent correlation boundary.

## Verification

Require the public process result, expected terminal state, complete failure and skip lists, target count, size, checksum, and readability. Confirm callback delivery separately, including duplicate handling and timeout-retry correlation. A callback does not mean complete, and process exit does not mean complete.
