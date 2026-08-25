---
id: RSKB-INTEGRATION-018
title: 'Upload with rayfile-c'
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
- 'How should a direct-file client prove remote count, checksums, and readability after an upload?'
- 'Which conflict check should the direct-file client run before sending several objects to an existing destination?'
- 'Why is a zero process result insufficient when the remote file cannot be read?'
keywords:
- 'rayfile-c upload'
- 'remote destination'
- 'multiple objects'
- 'conflict behavior'
- 'upload acceptance'
- 'target checksum'
- 'direct file client'
- 'directory hierarchy'
- 'trailing separator'
- 'successful send result'
- 'unreadable remote directory'
- 'same-name send conflict'
legacy_ids: []
safety_tags:
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-upload.md
  section: 'Check before operation'
  evidence_type: technical-boundary-document
- file: source_file/rayfile-c-upload.md
  section: 'Command structure'
  evidence_type: technical-boundary-document
- file: source_file/rayfile-c-upload.md
  section: 'Single file, directory and multiple objects'
  evidence_type: technical-boundary-document
- file: source_file/rayfile-c-upload.md
  section: 'Conflicts and file attributes'
  evidence_type: technical-boundary-document
- file: source_file/rayfile-c-upload.md
  section: 'Observe during operation'
  evidence_type: technical-boundary-document
- file: source_file/rayfile-c-upload.md
  section: 'Upload acceptance'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Upload with rayfile-c

## Short answer

Use the installed help for the direct file client, confirm a readable local source and authorized remote destination, and begin with one recyclable file. Decide conflict and metadata behavior before a directory or multi-object upload. Append is not resume.

## Guidance

A directory upload can preserve the source directory, send only its contents, or preserve the complete directory hierarchy; a trailing separator can change that result. Multiple sources require a destination that can contain several objects and must not share one target rename. Observe the sequence scan, connect, then data flow. A process exit does not mean complete.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm whether the upload sends a file, directory, or multiple sources; document the expected remote hierarchy, same-name result, metadata handling, and final object names. A single-file rename is not valid as one target rename for several sources.

## Recovery boundary

Preserve any existing remote object before overwrite and retain the local source until remote acceptance closes. If scan, connection, or data flow stops, keep the source inventory and remote status before a targeted retry. Do not turn append into a guessed resume policy or broaden the object set.

## Verification

Require the documented command result and terminal state, with no unexplained failed, skipped, or cancelled objects. Compare target count, size, checksums, final renamed objects, directory hierarchy, empty directory behavior, symbolic link policy, required metadata, and readability.
