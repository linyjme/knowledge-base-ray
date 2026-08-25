---
id: RSKB-INTEGRATION-019
title: 'Download with rayfile-c'
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
- 'How can a direct-file client prove that every directory object was retrieved intact?'
- 'Which safeguards protect a local destination when a direct-file client retrieves several remote sources?'
- 'How should a direct file client verify a local destination when a retrieval leaves nested items absent?'
keywords:
- 'rayfile-c download'
- 'local destination'
- 'directory download'
- 'file attributes'
- 'download acceptance'
- 'readability'
- 'direct file client'
- 'multiple remote sources'
- 'partial temporary file'
- 'retrieve missing local files'
- 'nested directory tree'
- 'retrieve several remote sources'
legacy_ids: []
safety_tags:
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-download.md
  section: 'Use rayfile-c to perform downloading'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Download with rayfile-c

## Short answer

Confirm the authorized remote source, writable local destination, free space, and conflict behavior in the direct file client, then retrieve a small object first. Multiple remote sources require a local directory and cannot share one target filename. Append is not resume.

## Guidance

Distinguish remote enumeration, local directory creation, data transfer, and final disk placement. Local security software, an in-use destination, insufficient space, or slow storage can leave a partial temporary file near the end. Directory acceptance covers the full inventory, empty directories, and linked-object handling rather than one spot check.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm the remote inventory, the local directory, expected conflict result, cross-platform names, and whether content and metadata have separate acceptance outcomes. For several remote sources, the intended effect is several local objects under the confirmed directory.

## Recovery boundary

Back up an existing local destination before overwrite. After interruption, retain partial files, confirm that the remote source version is unchanged, and establish documented resume conditions before retrying. The operator must not delete the only partial result merely because the command ended or the file remains in-use.

## Verification

Require terminal command status and the complete failed and skipped set. Compare remote and local inventories, count, size, checksums, business readability, partial temporary files, in-use files, and each required timestamp, permission, or link attribute.
