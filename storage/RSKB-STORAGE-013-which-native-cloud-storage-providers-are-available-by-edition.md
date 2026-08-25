---
id: RSKB-STORAGE-013
title: Which native cloud storage providers are available by edition?
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
- Which editions natively list Wasabi, Backblaze, AWS S3, Azure Blob, Google Cloud
  Storage, Tencent COS, and MinIO?
- Can every Raysync tier connect to the seven documented cloud object-storage providers?
- Is native cloud storage provider availability different for SMB, Enterprise, Cloud,
  or Multiple Spaces?
keywords:
- native cloud storage
- AWS S3
- Azure Blob
- Google Cloud Storage
- Tencent COS
- Wasabi Backblaze MinIO
legacy_ids:
- RS-FEAT-203
- RS-FEAT-202
- RS-FEAT-199
- RS-FEAT-204
- RS-FEAT-200
- RS-FEAT-201
- RS-FEAT-198
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-203 | Tencent COS
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-202 | Google cloud storage
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-199 | Backblaze
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-204 | MinIO
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-200 | AWS S3
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-201 | Azure Blob
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-198 | Wasabi
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which native cloud storage providers are available by edition?

## Short answer

The supplied feature matrix documents the following exact availability:

- Tencent COS: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Google cloud storage: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Backblaze: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- MinIO: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- AWS S3: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Azure Blob: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Wasabi: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Tencent COS | Supported | Supported | Supported | Supported |
| Google Cloud Storage | Supported | Supported | Supported | Supported |
| Backblaze | Supported | Supported | Supported | Supported |
| MinIO | Supported | Supported | Supported | Supported |
| AWS S3 | Supported | Supported | Supported | Supported |
| Azure Blob | Supported | Supported | Supported | Supported |
| Wasabi | Supported | Supported | Supported | Supported |

The source references preserve each canonical provider row and matrix anchor. No starting-version notes are supplied, so version applicability remains uncertain.

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
