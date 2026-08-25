---
id: RSKB-INTEGRATION-022
title: 'Manage remote files and directories with rayfile-c'
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
- 'How does a direct file client verify both remote locations after one move or rename?'
- 'What recovery boundary is required before deleting a remote directory?'
- 'How can I verify that a remote copy affected only the intended destination?'
keywords:
- 'rayfile-c remote management'
- 'create directory'
- 'delete object'
- 'rename'
- 'move'
- 'remote copy'
- 'direct file client'
legacy_ids: []
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-remote-management.md
  section: 'rayfile-c Remote directory and file management'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Manage remote files and directories with rayfile-c

## Short answer

Identify one remote object by an approved query, confirm the destination for create, rename, move, or copy, and preview the exact effect. Delete requires explicit authorization, a backup or documented recovery path, and a second confirmation of the object scope.

## Guidance

Do not infer identity from a display name alone. For move or rename, confirm that the destination does not already contain an unintended object; for copy, verify capacity and conflict behavior. After the command, query both old and new locations and check count, size, checksum, and readability. A record of success cannot restore deleted content.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm one remote object and whether the intended effect is create directory, delete, rename, move, or copy. Query the object first and record the exact old and new locations, conflict behavior, and affected scope.

## Recovery boundary

Preserve recoverable content before delete, move, or overwrite. If the destination already contains an unexpected object or a partial move occurs, stop and use the approved remote-storage recovery boundary rather than repeating the command broadly.

## Verification

Query both old and new locations after rename, move, or copy; after delete, verify only the authorized object is absent. Compare count, size, checksum, and readability for surviving or copied content.
