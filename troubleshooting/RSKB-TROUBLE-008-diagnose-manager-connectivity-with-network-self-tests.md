---
id: RSKB-TROUBLE-008
title: Diagnose manager connectivity with network self-tests
product: raysync
components:
- client-manager
- cli
- sdk
domain: troubleshooting
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why does a command-line or SDK call fail before it reaches a remote file operation?
- Which layered self-test separates local-manager, control-channel, worker, and data-path
  failures?
- What does a successful task-list query prove before a minimum transfer is attempted?
- Why can task listing succeed while a minimum test transfer never launches?
- What prevents an SDK from reaching the local native transfer manager?
- Why does the command-line client fail before transfer submission reaches its local manager?
- Why does a test transfer not start although task listing works?
- What if the task list loads but a small transfer does not start?
keywords:
- local manager connection
- control channel test
- worker registration
- remote reachability
- data surface
- read-only task list
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
- certificate
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/manager-connection-failure.md
  section: Synchronization command line failed to connect to local manager
  evidence_type: technical-boundary-document
- file: source_file/network-self-check.md
  section: Local manager network self-test
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose manager connectivity with network self-tests

## Short answer

Test from the local control plane outward: native manager, control channel, worker process, remote reachability, data progress, then target file. A local-manager failure is not a remote transfer failure.

## Symptoms

The CLI returns a non-zero result, an SDK connection fails before submission, a browser WebSocket does not respond, or a task is accepted without a worker starting.

## Checks

First confirm the executable starts with help and the native manager loads the same installation and user scope. Use a read-only task list through the original caller. Then check the control channel, submit one minimum task, observe worker process registration, inspect approved remote reachability and certificate trust from the worker host, and finally look for first data and the target file.

## Interpretation

A failed read-only query isolates the native manager or control channel. A successful query without worker process registration isolates dispatch or local worker preparation. Registration followed by remote failure isolates routing, authentication, permission, certificate, or version compatibility. Data progress with the wrong result isolates destination or policy.

## Backup or recovery boundary

Keep the original process result, configuration-key names without values, stage timeline, and minimum-task evidence as the recovery baseline. Do not copy example endpoints or modify hidden settings. Restore only a documented manager, control-channel, or policy value from an approved snapshot. If the minimum test task is still executing, retain its task evidence before using Stop; the preserved record and file inventory remain the recovery reference.

## Corrective action

An authorized operator must confirm the exact target installation, manager, caller, operator-owned minimum task, and authority to control it. After confirming the expected effect, correct the first failed layer only, preserve the prior value, and retest before advancing to the next layer. If the exact minimum test task remains active, use only the documented **Stop** action. Confirm immediately before acting that the intended effect is to stop execution; Stop does not delete the task record or files.

## Verification

Post-action verification requires a stable read-only query against the same target, timely control response, worker registration, continuous data progress, terminal state, and target-file verification. After Stop, verify the exact task is stopped or terminal, its evidence remains available, and the source and target files are unchanged.

## Evidence to collect

Collect masked versions, platform, entry type, operation stage, exit category, worker registration time, and result summary. Use `<host>`, `<path>`, and `<token>` placeholders and omit real endpoints, process identifiers, credentials, and raw logs.

## Escalation

Escalate when the native manager remains unavailable, the worker never registers after a valid request, or the first failing layer cannot be isolated with the minimum test.
