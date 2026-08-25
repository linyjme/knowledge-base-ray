---
id: RSKB-INTEGRATION-010
title: 'HTTP control surface and secure client settings'
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
- 'How can a third-party program protect the manager local web API control plane?'
- 'What must be preserved before changing a transport or proxy setting through HTTP?'
- 'How does a local web API caller verify client-settings persistence after an approved restart?'
keywords:
- 'manager HTTP'
- 'client settings'
- 'TLS'
- 'firewall'
- 'settings rollback'
- 'third-party integration'
- 'local web API'
legacy_ids: []
safety_tags: 
- authorization
- credentials
- certificate
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-039
- RSKB-INTEGRATION-040
source_refs:
- file: source_file/http-control-surface.md
  section: 'Third-party program HTTP control plane capabilities and boundaries'
  evidence_type: technical-boundary-document
- file: source_file/http-settings-and-security.md
  section: 'HTTP client settings, connection security and sensitive information protection'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# HTTP control surface and secure client settings

## Short answer

Manager HTTP is a local control surface for approved third-party programs. Confirm the enabled protocol and listener from the deployment, restrict callers with controlled networking and host firewalls, use approved TLS and hostname validation, and read a masked settings snapshot before changing one related group.

## Guidance

HTTP can create, query, and control tasks and can read or change selected client settings. It is distinct from browser WebSocket and Controller TCP. Confirm the current release's documented method, path, JSON shape, value range, persistence, and restart requirement. Never downgrade TLS, guess ports, enumerate hidden routes, or copy authentication and endpoint values into logs.

## Authorization and target

Only an authorized operator may act. Confirm the exact target manager, caller, documented method, task or setting, affected scope, and installed contract. Store secrets outside the request example and use `<host>`, `<token>`, and `<path>`; never record a real account, password, access key, certificate, device or group identifier, port, endpoint, or full local path.

## Effect and confirmation

Confirm one documented settings group, its current masked value, caller scope, TLS posture, and whether persistence or restart is part of the intended effect. A transport acknowledgement does not prove that the new value is active or durable.

## Recovery boundary

Keep the masked prior setting and documented restart condition. If connectivity or behavior regresses, stop additional settings writes, restore only that reviewed group through the supported contract, and repeat the same minimal observation.

## Verification

Re-read the changed setting, verify its effective scope, and repeat the check after any documented restart. For a task affected by the setting, separately require terminal state, failures, target count, checksum, and readability.
