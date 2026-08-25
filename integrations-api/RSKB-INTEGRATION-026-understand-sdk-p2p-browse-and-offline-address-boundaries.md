---
id: RSKB-INTEGRATION-026
title: 'Understand SDK P2P browse and offline-address boundaries'
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
- 'How does ready-gated peer-to-peer browsing differ from an ordinary client-library transfer job?'
- 'What does an offline peer address establish when the receiving device is unavailable?'
- 'Why must a browse caller wait for readiness before listing a peer directory?'
keywords:
- 'SDK P2P'
- 'P2P browse'
- 'offline address'
- 'peer ready'
- 'permission switches'
- 'historical boundary'
- 'client library'
- 'peer-to-peer'
- 'ready Browse session'
- 'ordinary peer transfer cannot start'
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/p2p.md
  section: 'P2P task capability boundary'
  evidence_type: technical-boundary-document
- file: source_file/p2p-boundaries.md
  section: 'P2P, Browse and offline addresses'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand SDK P2P browse and offline-address boundaries

## Short answer

Ordinary P2P transfers files, peer availability reports registration or visibility, Browse operates in a separate ready-gated session, and offline-address lookup is only historical location evidence. These source boundaries combine code review with incomplete historical scenarios and are not a current environment guarantee.

## Guidance

A Browse open result creates the session object; explicit ready success precedes list or management requests, and each permission remains independent. Paths normally stay relative to the receiving root. An offline address does not replace peer identity, prove that a device will reconnect, or guarantee automatic retry. Peer online does not mean complete, and channel ready does not mean complete.

## Boundaries

This article is explanatory. It preserves reviewed design and historical evidence boundaries; it does not claim that incomplete network, platform, permission, or lifecycle matrices passed in the current environment. It does not authorize a P2P or Browse write. All examples contain placeholders such as `<host>`, `<token>`, and `<path>`.
