---
id: RSKB-INTEGRATION-031
title: 'Use SDK transfer and directory operations'
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
- 'How does one-time client library transfer differ from persistent command-line tool synchronization?'
- 'Which client library directory-callback data must be copied before rename or remove verification?'
- 'How can I retain directory results safely after the callback returns?'
keywords:
- 'SDK transfer'
- 'directory operation'
- 'one-time upload'
- 'callback lifetime'
- 'remote delete'
- 'failure list'
- 'client library'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/normal-transfer-directory.md
  section: 'SDK common transfer and directory operations'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use SDK transfer and directory operations

## Short answer

After manager connection and remote login, the SDK can request one-time upload or download and remote directory list, create, rename, or delete operations. Immediate return means sent or queued, not completed. Copy callback-owned result data before returning.

## Guidance

Confirm transfer direction and a small source and destination. For directory writes, query the exact object first and preserve a recovery path before rename or delete. Associate callbacks, progress, final task details, and failures by task ID. Verify the remote or local target count, size, checksum, permissions, and readability rather than treating creation or a management callback alone as delivery.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm local-manager connection, remote login, one-time transfer direction, or one directory list, create, rename, or delete target. The client library immediate return means sent or queued, not that the file or directory effect is complete.

## Recovery boundary

Keep the task ID and copy callback-owned result data before return. Preserve the remote object before rename or delete, and query the original task after timeout instead of issuing a duplicate write.

## Verification

Associate callbacks, progress, terminal state, and failures by task ID. For transfer, compare target count, size, checksum, permissions, and readability; for directory changes, query the exact resulting object and old location.
