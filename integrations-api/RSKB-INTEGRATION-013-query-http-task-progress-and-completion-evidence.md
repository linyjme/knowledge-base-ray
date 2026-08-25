---
id: RSKB-INTEGRATION-013
title: 'Query HTTP task progress and completion evidence'
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
- 'Which HTTP query evidence proves a long-running task reached a final result?'
- 'How should an integration inspect failed or skipped files after polling task progress?'
- 'Why is a successful list response insufficient for accepting the destination contents?'
keywords:
- 'HTTP task query'
- 'progress polling'
- 'file list'
- 'terminal state'
- 'failure set'
- 'target evidence'
- 'local web API'
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-038
- RSKB-INTEGRATION-014
source_refs:
- file: source_file/http-task-query-and-acceptance.md
  section: 'Query task, file progress and completion results through HTTP'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Query HTTP task progress and completion evidence

## Short answer

The task list locates an ID, task status exposes state and progress, and file count and details expose failures. Reasonable-interval polling produces a state-transition timeline. A snapshot or successful query is not completion; acceptance requires a terminal state plus target evidence.

## Guidance

Completion evidence consists of the business query result, expected terminal state, full failure set, failed and skipped objects, target count and total size, key-deliverable checksums, required permissions, and readability. Synchronization adds next-trigger evidence, P2P adds peer result, and cluster work adds subtask results.

## Boundaries

This article is explanatory. It describes a documented data or result boundary and does not authorize changing a task, setting, listener, certificate, route, or remote object. Only the installed release's published contract is authoritative. Examples contain placeholders such as `<host>`, `<token>`, and `<path>`.
