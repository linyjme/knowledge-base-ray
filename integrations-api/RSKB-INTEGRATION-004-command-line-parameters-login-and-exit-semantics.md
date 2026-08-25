---
id: RSKB-INTEGRATION-004
title: 'Command-line parameters login and exit semantics'
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
- 'How can I separate a CLI syntax error from a manager connection or remote login failure?'
- 'Which installed help should define the valid options for a synchronization command?'
- 'What evidence should an automation retain when the CLI exits before a task is created?'
keywords:
- 'CLI parameters'
- 'login failure'
- 'exit result'
- 'current help'
- 'manager connection'
- 'masked diagnostics'
- 'command-line tool'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-parameter-and-login-failure.md
  section: 'Synchronous command line parameter verification or login failure'
  evidence_type: technical-boundary-document
- file: source_file/cli-parameter-semantics.md
  section: 'Synchronize command line parameter semantics'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Command-line parameters login and exit semantics

## Short answer

Classify the last successful phase: current-binary help and parsing, required and mutually exclusive options, local manager connection, remote login, then operation-specific dependencies. A process exit does not mean complete, and the sources do not establish one universal exit-code contract across releases.

## Guidance

Use the current installed help to confirm the operation, option names, value types, and old-versus-new syntax. Test a read-only list before a minimal task. If parsing passes, check the local manager and release family; only then check the remote account, authorization space, and clock. Retain the operation category, masked option names, time, and visible exit result—never values for passwords, tokens, access keys, hosts, ports, accounts, or full paths.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm whether the intended effect is parameter validation, a local-manager connection check, remote login, or creation of one minimal task. Record the current help spelling and masked option names before the command; a visible exit result describes the command phase, not file completion.

## Recovery boundary

Parameter or login diagnosis changes no remote content until a task is accepted. If a minimal task is unexpectedly created, retain its ID, stop further submissions, and use the installed CLI's task-control path rather than guessing a cleanup command.

## Verification

Verify parsing with current help, local-manager reachability with a read-only list, and remote authentication only through the intended minimal operation. If a task exists, require its terminal state and target evidence; otherwise retain the masked exit result and last successful phase.
