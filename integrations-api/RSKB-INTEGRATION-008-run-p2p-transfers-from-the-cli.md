---
id: RSKB-INTEGRATION-008
title: 'Run P2P transfers from the CLI'
product: raysync
components:
- client-manager
- cli
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
- 'Which stages should a command-line tool operator check when a visible peer-to-peer channel writes no file?'
- 'How can a command-line tool prepare a small peer-to-peer transfer without exposing authorization material?'
- 'What trigger and target evidence belongs to a scheduled peer-to-peer transfer?'
keywords:
- 'CLI P2P'
- 'peer authorization'
- 'peer online'
- 'channel establishment'
- 'scheduled P2P'
- 'target verification'
- 'command-line tool'
- 'peer-to-peer'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/cli-p2p.md
  section: 'Synchronization command line P2P operation guide'
  evidence_type: technical-boundary-document
- file: source_file/p2p-transfer.md
  section: 'SDK and command line P2P transfer'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Run P2P transfers from the CLI

## Short answer

Enable and verify receiving authorization, obtain peer identity and access material through a controlled system, confirm the peer is visible, then submit a minimal transfer with explicit direction and paths. Peer online does not mean complete, and channel ready does not mean complete.

## Guidance

Troubleshoot in stages: authorization and identity, peer availability, channel establishment, file read/write, terminal task result, then the target. Scheduled P2P also requires trigger and next-run checks. Never place peer keys in scripts, tickets, or logs. Acceptance requires the terminal state, failure set, target count and size, key checksums, and readability.

## Authorization and target

Only an authorized operator may act. Confirm the exact target, installed release, caller, task identifier, direction, source and destination, affected objects, and maintenance scope. Keep credentials in an approved secret store and use placeholders such as `<host>`, `<token>`, and `<path>` in commands, logs, and tickets.

## Effect and confirmation

Confirm receiving authorization, peer identity, direction, relative target, and whether the job is ordinary or scheduled. The intended effect starts only after registration, matching, channel readiness, and file execution each reach their required stage.

## Recovery boundary

Keep peer credentials out of artifacts and retain the original task ID after timeout or disconnect. Restore receiver monitoring or supported network conditions before retrying; do not replace peer identity with an address or assume automatic offline recovery.

## Verification

Verify receiver registration, peer visibility, channel readiness, terminal task state, and failure set in order. Then compare target count, size, checksums, and readability; scheduled P2P also requires trigger and next-run evidence.
