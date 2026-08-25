---
id: RSKB-INTEGRATION-029
title: 'Manage SDK connection and login lifecycle'
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
- 'Which SDK lifecycle sequence creates callbacks, connects locally, and authenticates remotely?'
- 'Why can a local manager connection succeed while directory or transfer login fails?'
- 'What session state must a client library rebuild after an unexpected connection-close event?'
keywords:
- 'SDK lifecycle'
- 'local manager connection'
- 'remote login'
- 'connection close'
- 'handle cleanup'
- 'reconnect'
- 'client library'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/connection-failure.md
  section: 'What to do if the connection fails or is disconnected soon?'
  evidence_type: technical-boundary-document
- file: source_file/connection-lifecycle.md
  section: 'SDK connection and login life cycle'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Manage SDK connection and login lifecycle

## Short answer

Create the interface object, attach user data and callbacks, connect to the local manager, log in to the remote service when needed, submit requests, process asynchronous results, then disconnect and destroy the handle. Local connection does not prove remote authentication.

## Guidance

After a connection-close event, stop submitting through the old handle, preserve callback-owned data until safe, and rebuild both manager and login state. Diagnose local portal failure separately from remote authentication, path, permission, encryption, proxy, or network interruption. Verify recovery with two consecutive small transfers and their final target results; never disable security controls to bypass the failure.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm the client library lifecycle target: interface creation, callback and user-data registration, local-manager connection, remote login, request execution, or cleanup. Local connection and remote authentication are separate effects.

## Recovery boundary

After a connection-close event, stop using the old handle and retain callback-owned data until safe. Recreate the handle, callbacks, local connection, and remote login in order; do not submit through a closed session.

## Verification

Verify local connection separately from remote login, then complete two small directory or transfer operations with callbacks, terminal states, failures, and target evidence before restoring the original scale.
