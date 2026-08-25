---
id: RSKB-INTEGRATION-007
title: 'Run local copy from the CLI'
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
- 'How can I validate a CLI local-copy job without creating a recursive path relationship?'
- 'Which checks distinguish overwrite, skip, and documented resume behavior for local replication?'
- 'What evidence is required before source cleanup is accepted after a local copy?'
keywords:
- 'CLI local copy'
- 'local replication'
- 'recursive path'
- 'conflict mode'
- 'disk space'
- 'source cleanup'
- 'command-line tool'
legacy_ids: []
safety_tags: 
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-local-copy.md
  section: 'Synchronize command line local copy operation'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Run local copy from the CLI

## Short answer

Confirm that the source exists, the destination is writable, the paths cannot recurse, and the disk has capacity. Select the documented overwrite, resume, or skip behavior, begin with low concurrency, and use verification when consistency matters. Source cleanup is accepted only after the target passes.

## Guidance

Local copy still depends on the manager but does not require remote file-service login. File locks, account permissions, path rules, and target capacity remain relevant. Save the task ID and terminal state, inspect the failure set, then compare target count, total size, checksums, permissions, and time attributes. Append is not resume, so never substitute append semantics for the product’s documented conflict mode.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm two non-nested local paths, a writable destination, conflict mode, verification choice, concurrency, and any source cleanup. The intended effect is local replication through the manager, not remote-service transfer.

## Recovery boundary

Preserve the destination before overwrite and the source before post-copy deletion. If recursive placement, file locks, or capacity errors appear, stop the local-copy task and correct one condition before a small targeted retry.

## Verification

Require the local-copy terminal state and failure set, then compare source and destination count, size, checksums, permissions, and timestamps. Accept source disappearance only after the copied target has passed every required check.
