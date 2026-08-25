---
id: RSKB-ADMIN-053
title: Which server deployment and availability modes are supported by edition?
product: raysync
components: [admin-portal, file-service]
domain: administration
access_level: internal
audience: [administrator, internal-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- How are standalone and standby rows compared with application balancing?
- Which load evidence belongs to a named active topology?
- Why must server patterns be qualified independently?
keywords: [standalone standby, application balancing, load, active topology, server pattern]
legacy_ids: [RS-FEAT-208, RS-FEAT-209, RS-FEAT-210, RS-FEAT-211, RS-FEAT-212]
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-048]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-208 | Standalone deployment', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-209 | Dual server and standby deployment', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-210 | Application layer load balancing mode deployment', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-211 | Support 4-layer load balancing mode deployment (LV5, F5 load balancer)', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-212 | Multi-port integration', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-213 | High availability deployment', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which server deployment and availability modes are supported by edition?

## Short answer

The supplied evidence distinguishes named topology rows; it does not provide one safely generalizable high-availability entitlement.

## Terminology and boundaries

**Single server**, **active standby**, **application balancing**, and **network balancing** name four distinct topology intents corresponding to the source rows. **Entitlement** means the exact edition-and-topology combination approved after qualification. The aliases do not collapse the quarantined generic claim into a public contract.

## Edition evidence

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Standalone deployment | Supported | Supported | Not supported | Supported |
| Dual-server standby | Not supported | Supported | Not supported | Supported |
| Application-layer load balancing | Not supported | Supported | Not supported | Supported |
| Layer-four load balancing | Not supported | Supported | Not supported | Supported |
| Multi-port integration | Supported | Supported | Supported | Supported |

RS-FEAT-213 is quarantined conflict evidence only: its generic high-availability claim says SMB is supported while the three specific topology rows say SMB is not supported. The generic claim is not a retrieval intent; no claim is selected as an entitlement until the exact topology scenarios pass GATE-RS-FEAT-213-VS-209, GATE-RS-FEAT-213-VS-210, and GATE-RS-FEAT-213-VS-211 for Raysync 8.1.8.7.

## Publication boundary

This uncertain internal matrix is not a supported public contract. It does not authorize deployment, failover, load-balancer, port, or database changes.
