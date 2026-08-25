---
id: RSKB-ADMIN-029
title: 'Choose an SDK CLI HTTP or local entry surface'
product: raysync
components:
- client-manager
- sdk
- cli
- http-api
domain: administration
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
- 'Which integration surface corresponds to an unattended workflow with final-file evidence?'
- 'Is browser automation an appropriate caller for the local HTTP control channel?'
- 'When is a client library, direct file client, or peer-to-peer SDK the matching integration category?'
keywords:
- 'integration surface'
- 'SDK'
- 'CLI'
- 'HTTP API'
- 'graphical interface'
- 'rayfile-c'
- 'P2P SDK'
- 'entry selection'
- 'client library'
- 'local web API'
- 'direct file client'
- 'peer-to-peer SDK'
- 'command-line tool'
legacy_ids: []
safety_tags: []
supersedes: []
superseded_by: []
related_articles:
- RSKB-INTEGRATION-035
- RSKB-INTEGRATION-040
- RSKB-INTEGRATION-002
source_refs:
- file: source_file/interaction-entry.md
  section: 'How to choose the interactive entrance'
  evidence_type: technical-boundary-document
- file: source_file/choose-surface.md
  section: 'Entry selection and minimum acceptance'
  evidence_type: technical-boundary-document
- file: source_file/entry-surfaces.md
  section: 'Local entrance differences and selections'
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Choose an SDK CLI HTTP or local entry surface

## Short answer

Surface choice follows the caller and lifecycle: the graphical interface covers small manual workloads; the CLI or SDK covers unattended orchestration; local HTTP covers controlled third-party programs; rayfile-c covers a direct scripted file operation; and the P2P SDK covers peer-to-peer workflows. The surface changes submission and observation, not the need for final-state and target-file evidence.

## Guidance

Browser pages normally use their WebSocket surface; local HTTP is the local web API for controlled third-party callers, not a browser fallback. The SDK or client library and the CLI or command-line tool coordinate through the local manager. Rayfile-c is the direct file client, while the P2P SDK adds peer identity, authorization, availability, and channel stages. Request acceptance and health status describe intermediate evidence, not completion.

## Boundaries

This article is explanatory. It classifies integration surfaces and does not authorize a request, file operation, task control, settings change, or connectivity trial. Any state-changing trial must use the applicable action article for that surface. The action owners are RSKB-INTEGRATION-005 through RSKB-INTEGRATION-009 for command-line tasks, RSKB-INTEGRATION-010 through RSKB-INTEGRATION-012 for the local HTTP API, RSKB-INTEGRATION-018, RSKB-INTEGRATION-019, RSKB-INTEGRATION-022, or RSKB-INTEGRATION-023 for rayfile-c file actions, and RSKB-INTEGRATION-027 or RSKB-INTEGRATION-029 through RSKB-INTEGRATION-033 for SDK and P2P lifecycles. The installed release's documented contract remains authoritative.
