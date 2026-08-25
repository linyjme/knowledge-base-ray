---
id: RSKB-INTEGRATION-027
title: 'Diagnose SDK P2P connectivity'
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
- 'Which client-library peer-to-peer stage failed when a token arrives without tunnel readiness?'
- 'How should I test a temporarily offline receiver without promising automatic recovery?'
- 'What anonymized evidence helps separate matching, tunnel, and file-permission failures?'
keywords:
- 'SDK P2P connectivity'
- 'receiver registration'
- 'match timeout'
- 'token not ready'
- 'relative target'
- 'anonymized timeline'
- 'client library'
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
- file: source_file/p2p-connectivity.md
  section: 'P2P cannot connect'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose SDK P2P connectivity

## Short answer

Locate the failure stage: receiver registration and identity, online or historical lookup, token coordination, channel readiness, root-relative path and permission, data flow, then target acceptance. Token receipt or matching success is not proof that the network channel or file operation succeeded.

## Guidance

Bring the receiver online and keep monitoring, then retry one small file with a confirmed relative target. Change only supported proxy, network, and platform settings; do not reintroduce historical forwarding behavior or alter callback ABI. Record stage, platform, network and storage categories, and a redacted timeline. The source's regression coverage is incomplete, so automatic offline retry and Browse behavior are not guaranteed.

## Authorization and target

Only an authorized integrator may act. Confirm the exact target manager and handle, installed SDK release, operation and task ID, identity, source and destination, and affected objects. Use placeholders such as `<host>`, `<token>`, and `<path>`; never record a real endpoint, port, account, password, token, access key, device or group identifier, full path, function pointer, raw request, certificate, or log.

## Effect and confirmation

Confirm the P2P stage under review: receiver registration, identity matching, historical offline lookup, token coordination, channel readiness, root-relative path, or file execution. The intended effect is a supported stage correction followed by one small peer-to-peer transfer.

## Recovery boundary

Keep the original stage timeline and avoid automatic resubmission after offline, timeout, or token-without-ready. Restore receiver monitoring or one supported network condition first; do not change callback ABI or reintroduce historical forwarding.

## Verification

Verify registration, matching, token, ready event, first data, terminal task state, and target file in order. Record incomplete Browse coverage explicitly and retain only anonymized platform, network, storage, and stage evidence.
