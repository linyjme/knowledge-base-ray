---
id: RSKB-INTEGRATION-005
title: 'Trigger transfer and synchronization from the CLI'
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
- 'How should an operator choose a trigger policy for a persistent CLI synchronization job?'
- 'What must be confirmed before enabling source cleanup in a command-line transfer task?'
- 'Why does a one-round CLI trigger remain a manager-owned job that needs status checks?'
keywords:
- 'CLI synchronization'
- 'trigger policy'
- 'two-way sync'
- 'source cleanup'
- 'include exclude'
- 'persistent task'
- 'command-line tool'
- 'timer and change trigger model'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-transfer-sync-trigger.md
  section: 'Synchronize command line upload, download and trigger strategy'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Trigger transfer and synchronization from the CLI

## Short answer

Define direction, source and destination, task name, authentication, filters, conflict behavior, and one trigger policy before submission. Upload, download, and two-way synchronization create persistent manager tasks even when configured for one round. Follow the task to a terminal state and verify the target.

## Guidance

Fixed-time, interval, real-time, execute-once, and user-start-once strategies have different acceptance checks. Test include or exclude rules on a small directory. Source deletion, source movement, bidirectional deletion, and overwrite are destructive: back up the source, diagram the expected target tree, and confirm recoverability before enabling them. Append is not resume; use only the conflict or resume mode documented by the installed release.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm the transfer direction, task name, source and destination, one trigger policy, filters, conflict rules, and any post-transfer source effect. The intended effect may be a persistent schedule even when the first trigger runs once.

## Recovery boundary

Create and validate a restorable backup before bidirectional deletion, overwrite, movement, or source cleanup. If the saved trigger or target tree differs from the review, stop the task before another trigger and restore through the documented source or destination recovery path.

## Verification

Query the saved task rules and next trigger, then require terminal state and a complete failure set for the executed round. Compare target inventory, size, checksums, and readability, and verify source movement or deletion separately.
