---
id: RSKB-INTEGRATION-023
title: 'Set rayfile-c conflict verification and metadata policies'
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
- 'Which direct file client conflict policy avoids accidental same-name overwrite?'
- 'How do verification and metadata options change transfer acceptance?'
- 'Why must symbolic-link or compression behavior be proven with a small sample?'
keywords:
- 'rayfile-c conflict policy'
- 'same-name file'
- 'verification'
- 'metadata'
- 'symbolic link'
- 'compression'
- 'direct file client'
- 'changed timestamps and permissions'
legacy_ids: []
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/rayfile-c-transfer-policies.md
  section: 'rayfile-c conflict, verification and metadata strategy'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Set rayfile-c conflict verification and metadata policies

## Short answer

Choose same-name behavior, rename rules, content verification, timestamp and permission handling, symbolic-link behavior, and compression deliberately. Test one representative collision and one metadata-sensitive object before a broad transfer.

## Guidance

Overwrite can destroy the prior destination; skip can leave stale content; automatic rename can change the expected tree. Append is not resume. Preserve a recovery copy before destructive conflict behavior. Acceptance must compare the selected policy with the actual target name, count, size, checksum, timestamps or permissions, links, and readability.

## Authorization and target

Only an authorized operator may act. Confirm the exact target service, identity, operation, source and destination, selected objects, conflict behavior, and expected result. Use placeholders such as `<host>`, `<token>`, and `<path>`; never put real credentials, endpoints, accounts, ports, identifiers, or full paths in documentation, command history, or support notes.

## Effect and confirmation

Confirm the same-name action, automatic rename, verification, timestamp, permission, access-control, symbolic-link, and compression policy for the selected objects. Append is not resume, and each policy changes a different acceptance dimension.

## Recovery boundary

Keep the prior destination before overwrite or metadata replacement. If names, links, or attributes differ from the reviewed policy, stop before expanding the transfer and restore only through the approved target recovery path.

## Verification

Compare actual target names, count, size, checksums, timestamps, permissions, access control, links, compression outcome, and readability with the selected policy. Record content verification separately from metadata preservation.
