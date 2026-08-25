---
id: RSKB-STORAGE-012
title: Which editions support local and network-file-system storage?
product: raysync
components:
- file-service
domain: storage
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
- Can all product tiers use server-local disks and mounted NFS or SMB file systems?
- Which editions accept a network share mounted as a directory or drive letter?
- Do local versus network-file-system backends have different tier coverage?
- May file-service storage use mounted NFS shares?
- Do local disks and network-backed storage have identical edition coverage?
keywords:
- local disk backend
- NFS mount
- SMB network share
- drive-letter storage
- edition matrix
legacy_ids:
- RS-FEAT-197
- RS-FEAT-196
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-197 | Network file systems (systems such as NFS/SMB mounted as
    server directories or drive letter)
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-196 | Local disk file system
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support local and network-file-system storage?

## Short answer

The supplied feature matrix documents the following exact availability:

- Network file systems (systems such as NFS/SMB mounted as server directories or drive letter): SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Local disk file system: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Network file systems mounted as server directories or drive letters | Supported | Supported | Supported | Supported |
| Local-disk file system | Supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifiers and matrix anchors. No starting-version note is supplied, so version applicability remains uncertain.

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
