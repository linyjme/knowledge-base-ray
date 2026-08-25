---
id: RSKB-ADMIN-034
title: Manager and file-client subprocess coordination
product: raysync
components: [client-manager, file-service]
domain: administration
access_level: internal
audience: [internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which child process is launched before controller enrollment?
- How are enrolled workers assigned during dispatch?
- Where can worker process coordination fail before a job?
keywords: [child process launched, controller enrolled, worker assigned, dispatch, worker coordination job, manager subprocess, local bridge]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-031, RSKB-TROUBLE-008]
source_refs:
- {file: source_file/child-process-coordination.md, section: Coordination between the manager and the sub-process of the file client, evidence_type: technical-boundary-document}
- {file: source_file/child-process-start-failure.md, section: File client subprocess failed to start, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Manager and file-client subprocess coordination

## Short answer

The manager selects and starts a file-client worker, waits for registration over the local control boundary, delivers work, and consumes status reports. A process that merely exists has not proved registration or task execution.

## Terminology and boundaries

A **child** is the subprocess created for work; **worker launched** records local creation. **Controller enrollment** and **registration** establish coordination identity, while **dispatch** and **assignment** deliver work. Each is a distinct internal checkpoint, so evidence from one stage cannot stand in for a later stage.

## Coordination stages

Distinguish no worker, started but unregistered, registered without progress, progressing without caller updates, and disconnected after registration. These stages respectively focus evidence on installation selection, runtime prerequisites, task delivery or remote access, status reporting, and worker stability.

Preserve only sanitized timestamps, exit categories, registration state, and task-stage summaries. Do not expose executable packages, raw paths, credentials, logs, or internal connection details. Do not start duplicate workers outside the manager to simulate recovery.

## Publication boundary

This child-process explanation is not a supported public contract. It does not authorize killing, manually launching, or replacing worker processes; recovery must follow an approved product procedure for the exact release.
