---
id: RSKB-ADMIN-050
title: Which editions support client hash encryption and Rsync settings?
product: raysync
components:
- admin-portal
- desktop-client
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
- Can administrators enforce client hashing, encryption, and Rsync policy in every
  edition?
- Which product tiers support centrally forcing client integrity and delta-transfer
  settings?
- Is the client hash-encryption-Rsync policy limited by Raysync edition?
- Where can administrators enforce client Rsync behavior from central policy?
- Can client-side hashing and encryption be required by an administrator?
keywords:
- forced client policy
- hash setting
- transfer encryption setting
- Rsync setting
- edition matrix
legacy_ids:
- RS-FEAT-189
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-189 | Support forcibly enable/disable client hash, encryption,
    rsync settings
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support client hash encryption and Rsync settings?

## Short answer

The supplied feature matrix documents the following exact availability:

- Support forcibly enable/disable client hash, encryption, rsync settings: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Administrator-enforced client hash, encryption, and Rsync settings | Supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifier and matrix anchor. The recorded source milestone is change evidence only, not a guaranteed minimum supported version.

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
