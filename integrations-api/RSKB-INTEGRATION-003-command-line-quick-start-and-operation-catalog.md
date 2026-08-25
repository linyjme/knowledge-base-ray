---
id: RSKB-INTEGRATION-003
title: 'Command-line quick start and operation catalog'
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
- 'What lifecycle and release boundaries define the synchronization command-line tool?'
- 'Which CLI operation family represents listing, control, peer-to-peer, or local replication?'
- 'Why are command acceptance, managed-task state, and file completion separate results?'
keywords:
- 'CLI quick start'
- 'operation catalog'
- 'manager connection'
- 'task identifier'
- 'read-only query'
- 'synchronization CLI'
- 'command-line tool'
- 'peer-to-peer'
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-operation-catalog.md
  section: 'Synchronize command line operation directory'
  evidence_type: technical-boundary-document
- file: source_file/cli-quickstart.md
  section: 'Quick start with synchronization command line'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Command-line quick start and operation catalog

## Short answer

The synchronization CLI is a command-line tool in the same release family as the local manager and file client. Its public operation catalog groups synchronization creation, local copy, cluster, peer-to-peer, query, and control semantics. It creates manager-owned tasks and is not a standalone transport process.

## Guidance

Operation families describe different lifecycle roles: creation establishes a persistent manager record; query observes it; control changes that record; local copy uses locally visible storage; cluster adds coordination and subtasks; and P2P adds peer authorization and channel stages. A task ID associates later state but does not mean complete. Deleting a task record does not delete remote files. Option spelling and availability remain release-specific.

## Boundaries

This article is explanatory. It catalogs operation families and result semantics; it does not authorize task creation, control, file submission, deletion, or a command trial. Any state-changing trial must use the applicable action article for that surface. The action owners are RSKB-INTEGRATION-005 for transfer or synchronization creation, RSKB-INTEGRATION-006 for task query and control, RSKB-INTEGRATION-007 for local copy, RSKB-INTEGRATION-008 for P2P transfer, or RSKB-INTEGRATION-009 for cluster tasks. The installed binary's documented help remains authoritative.
