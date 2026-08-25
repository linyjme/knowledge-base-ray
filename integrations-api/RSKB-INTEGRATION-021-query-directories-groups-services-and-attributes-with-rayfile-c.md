---
id: RSKB-INTEGRATION-021
title: 'Query directories groups services and attributes with rayfile-c'
product: raysync
components:
- cli
- file-service
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
- 'Which rayfile-c read-only query should I use before changing a remote directory?'
- 'How can a read-only direct-file-client result distinguish directory, group, namespace, service, and attribute data?'
- 'What makes a sanitized direct-file-client query safe to share with support?'
keywords:
- 'rayfile-c query'
- 'directory listing'
- 'attributes'
- 'group namespace'
- 'service information'
- 'read-only operation'
- 'direct file client'
legacy_ids: []
safety_tags:
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-query-operations.md
  section: 'rayfile-c Directory, attribute, group and service information query'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Query directories groups services and attributes with rayfile-c

## Short answer

Select the query category before running it: directory contents, object attributes, group or namespace data, or service information. Use the installed help and minimum scope, then verify that the result type and target match the intended question.

## Guidance

A successful query does not authorize a subsequent write. Confirm the requested object identity and distinguish an empty valid result from a parse, permission, or connection failure. Redact names, accounts, group and device identifiers, full paths, endpoints, and raw service configuration before retaining evidence.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm whether the direct file client is expected to return a directory, object attributes, a group or namespace, or service information. The intended effect is read-only evidence for that result category; it is not authorization for a file or directory change.

## Recovery boundary

No data recovery is expected from a read-only query. If the result category, identity, or authorization differs from the request, stop, preserve a redacted result summary, and correct the query category without attempting a write.

## Verification

Verify the command result, returned category, intended object identity, and whether an empty result is valid. Retain only the minimum redacted directory, attribute, group, namespace, or service summary needed for diagnosis.
