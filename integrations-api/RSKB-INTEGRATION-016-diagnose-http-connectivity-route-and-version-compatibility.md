---
id: RSKB-INTEGRATION-016
title: 'Diagnose HTTP connectivity route and version compatibility'
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
- 'How do local web API diagnostics separate certificate-hostname failures from version drift?'
- 'Which masked evidence helps support compare a caller with the installed API contract?'
- 'What contract tests should run before upgrading a third-party HTTP integration?'
keywords:
- 'HTTP diagnostics'
- 'unknown interface'
- 'TLS hostname'
- 'version drift'
- 'contract test'
- 'redacted support bundle'
- 'local web API'
legacy_ids: []
safety_tags: 
- authorization
- certificate
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-040
source_refs:
- file: source_file/http-diagnostics-and-support-bundle.md
  section: 'HTTP self-test, network testing and diagnostic material collection'
  evidence_type: technical-boundary-document
- file: source_file/http-unreachable-or-unknown-interface.md
  section: 'manager HTTP cannot connect, protocol does not match, or the interface does not exist'
  evidence_type: technical-boundary-document
- file: source_file/http-version-and-route-compatibility.md
  section: 'manager HTTP interface version and client compatibility'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose HTTP connectivity route and version compatibility

## Short answer

First confirm that the caller should use manager HTTP, then verify the running role, approved listener, HTTP versus HTTPS, certificate and hostname, documented method and path, content type, and request shape. Do not scan for similar internal routes when the installed contract reports an unknown interface.

## Guidance

Before an upgrade, inventory the manager and caller versions and run contract tests for a read-only query, minimal create, status query, stop or cleanup, and an invalid parameter. Mark unexecuted combinations NOT RUN. Collect only masked protocol category, release, path category, status, business summary, and timeline. Redact accounts, credentials, certificates, full host and port, full request, paths, file contents, device or group identifiers, and raw logs. A health check does not mean complete.

## Authorization and target

Only an authorized operator may act. Confirm the exact target manager, caller, documented method, task or setting, affected scope, and installed contract. Store secrets outside the request example and use `<host>`, `<token>`, and `<path>`; never record a real account, password, access key, certificate, device or group identifier, port, endpoint, or full local path.

## Effect and confirmation

Confirm the caller surface, running role, release pair, approved listener, protocol, certificate hostname, method, path category, content type, and request shape. The intended diagnostic effect is a supported read-only contract result, not route discovery.

## Recovery boundary

Diagnostics should not alter tasks or settings. If a check reaches an unknown interface, certificate error, or incompatible response shape, stop enumeration, retain the masked stage result, and return to the official contract or rollback caller version.

## Verification

Verify one officially supported read-only query with a parseable business result. Record PASS, FAIL, BLOCKED, or NOT RUN for contract cases and retain only redacted protocol category, release, path category, status, and timeline.
