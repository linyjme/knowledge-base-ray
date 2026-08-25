---
id: RSKB-INTEGRATION-034
title: 'Distinguish scheduled synchronization, local-copy, and cluster tasks'
product: raysync
components:
- client-manager
- sdk
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
- 'How do scheduled synchronization, local-copy, and cluster jobs differ in dependencies?'
- 'Why can a cluster batch creation succeed while a required subtask still reports failure?'
- 'Which policies need backup review before enabling two-way scheduled synchronization?'
keywords:
- 'scheduled synchronization'
- 'local copy'
- 'cluster task'
- 'trigger policy'
- 'coordination dependency'
- 'subtask acceptance'
- 'client library'
- 'command-line tool'
- 'required subtask failure'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/timing-local-cluster.md
  section: 'Scheduled synchronization, local replication and cluster tasks'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Distinguish scheduled synchronization, local-copy, and cluster tasks

## Short answer

Scheduled synchronization repeats or watches remote and local content, local copy operates between locally visible paths, and cluster tasks add coordination and subtask dependencies. The source does not establish that local-copy or cluster tasks are themselves scheduled; treat the three categories separately.

## Guidance

Synchronization requires trigger, next-run, conflict, deletion, and restart checks. Local copy requires path, disk, conflict, verification, and optional source-processing checks. Cluster creation requires an approved coordination service and acceptance of every required subtask. Back up before two-way deletion, overwrite, move, or source cleanup. A created job, reachable coordinator, or one successful subtask does not prove completion.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm which of three distinct task categories applies: scheduled synchronization with triggers, local copy between visible local paths, or cluster work with coordination and subtasks. The evidence does not establish that local-copy or cluster tasks are scheduled.

## Recovery boundary

Back up before synchronization deletion, overwrite, move, or source cleanup; preserve local source and destination before copy; and retain cluster batch and subtask evidence before directed retry. Recovery follows the selected category only.

## Verification

For scheduled synchronization, verify saved trigger, next run, terminal round, failures, and target. For local copy, verify worker state and local inventory. For cluster, require coordination plus every required subtask, failure scope, and target acceptance.
