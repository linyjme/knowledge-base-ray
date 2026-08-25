---
id: RSKB-ADMIN-046
title: Which real-time server monitoring and topology-map capabilities are available
  by edition?
product: raysync
components:
- admin-portal
- node-scheduler
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why can every product tier show live server status while SMB lacks the topology
  map?
- Which Raysync tiers include both host monitoring and a live network topology view?
- Can an SMB deployment display the same topology visualization as Enterprise or Cloud?
keywords:
- server telemetry
- live topology map
- SMB topology limitation
- node monitoring
- edition matrix
legacy_ids:
- RS-FEAT-178
- RS-FEAT-188
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-178 | Server real-time monitoring
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-188 | Support real-time network topology map
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which real-time server monitoring and topology-map capabilities are available by edition?

## Short answer

The supplied feature matrix documents the following exact availability:

- Server real-time monitoring: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Support real-time network topology map: SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Server real-time monitoring | Supported | Supported | Supported | Supported |
| Real-time network topology map | Not supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifiers and matrix anchors. Version notes describe when an individual row appeared or changed; they do not establish a minimum version for the combined article.

## Backup or recovery boundary

No backup or recovery operation is authorized. Preserve the observed edition, version, and current configuration, and do not alter production to make it match the matrix.

## Corrective action

This article is explanatory and does not authorize a UI, command, or state change. The responsible product owner may compare entitlement evidence and open a version-and-edition verification request.

## Verification

Verify the exact edition cell for every required capability and record any mismatch as an unresolved version or entitlement question; feature presence alone does not establish support for a different edition.

## Evidence to collect

Collect only the product version, edition, capability name, and observed availability. Do not include credentials, private addresses, customer data, or full logs.

## Escalation

Escalate to Raysync support when the deployed version and edition are known but behavior differs from the exact matrix entry. Keep any source milestone separate from the requested current-support decision.
