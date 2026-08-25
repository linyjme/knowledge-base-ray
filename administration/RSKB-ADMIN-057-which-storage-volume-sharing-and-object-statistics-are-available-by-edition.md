---
id: RSKB-ADMIN-057
title: Which storage-volume sharing and object statistics are available by edition?
product: raysync
components:
- admin-portal
- file-service
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
- Can every Raysync edition report storage, volume, share-link, and object-store statistics?
- Which product tiers expose capacity and sharing analytics together?
- Are object-storage metrics edition-limited compared with volume and link statistics?
- Which statistics report shared-link activity and storage-volume usage?
- Are object-storage and mounted-volume metrics available in each plan?
keywords:
- storage statistics
- volume analytics
- share-link statistics
- object-store metrics
- edition matrix
legacy_ids:
- RS-FEAT-267
- RS-FEAT-265
- RS-FEAT-264
- RS-FEAT-266
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-267 | Object storage statistics
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-265 | Volume Statistics
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-264 | Storage Statistics
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-266 | Share Link Statistics
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which storage-volume sharing and object statistics are available by edition?

## Short answer

The supplied feature matrix documents the following exact availability:

- Object storage statistics: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Volume Statistics: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Storage Statistics: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Share Link Statistics: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Object-storage statistics | Supported | Supported | Supported | Supported |
| Volume statistics | Supported | Supported | Supported | Supported |
| Storage statistics | Supported | Supported | Supported | Supported |
| Share-link statistics | Supported | Supported | Supported | Supported |

The source references preserve each canonical feature identifier and matrix anchor. Only the object-storage row has a recorded milestone; it does not establish a minimum version for every capability in this article.

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
