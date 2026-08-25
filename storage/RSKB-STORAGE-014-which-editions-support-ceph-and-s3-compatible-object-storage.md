---
id: RSKB-STORAGE-014
title: Which editions support ceph and S3-compatible object storage?
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
- Can every Raysync tier use a Ceph object gateway or another S3-compatible service?
- Which editions document self-managed Ceph and third-party S3 API storage?
- Are DigitalOcean, Linode, Vultr, Wasabi, Backblaze, and MinIO covered through compatibility
  entries?
keywords:
- Ceph object gateway
- S3-compatible storage
- self-managed Ceph
- object storage compatibility
- edition matrix
legacy_ids:
- RS-FEAT-205
- RS-FEAT-206
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-205 | Ceph-class object storage like DigitalOcean/Linode/Vultr,
    and support Ceph object storage built by themselves (users need to configure Cephde
    S3 object gateway)
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: 'RS-FEAT-206 | S3 API compatible cloud services(For example: Wasabi, Backblaze,
    MinIO, Meituan Cloud, Didi Cloud and other object storage)'
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support ceph and S3-compatible object storage?

## Short answer

The supplied feature matrix documents the following exact availability:

- Ceph-class object storage, including self-managed Ceph through a configured S3 object gateway: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- S3 API-compatible cloud services, including Wasabi, Backblaze, MinIO, Meituan Cloud, and Didi Cloud: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Ceph object storage through an S3 gateway | Supported | Supported | Supported | Supported |
| S3 API-compatible object-storage services | Supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifiers, source wording, and matrix anchors. No starting-version notes are supplied, so version applicability remains uncertain.

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
