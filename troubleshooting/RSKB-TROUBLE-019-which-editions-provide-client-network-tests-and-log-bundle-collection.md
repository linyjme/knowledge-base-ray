---
id: RSKB-TROUBLE-019
title: Which editions provide client network tests and log-bundle collection?
product: raysync
components:
- desktop-client
- client-manager
domain: troubleshooting
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
- Which editions include port diagnosis, UDP speed testing, and sanitized client log
  bundles?
- Can every product tier locate network failures and package client diagnostics?
- Are automatic log compression and network self-tests limited by Raysync edition?
- Can the client create a sanitized compressed log package for support?
- Which editions include UDP network throughput testing?
- Can the client package sanitized logs for a support request?
keywords:
- client port diagnosis
- UDP speed test
- client log bundle
- automatic log compression
- network failure location
legacy_ids:
- RS-FEAT-020
- RS-FEAT-023
- RS-FEAT-022
- RS-FEAT-019
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-020 | UDP speed test
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-023 | Clean client logs and automatically compress logs
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-022 | Collecting client logs
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-019 | Automatically locate the cause of network connection failure,
    port detection
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions provide client network tests and log-bundle collection?

## Short answer

The supplied feature matrix documents the following exact availability:

- UDP speed test: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Clean client logs and automatically compress logs: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Collecting client logs: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Automatically locate the cause of network connection failure, port detection: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| UDP speed test | Supported | Supported | Supported | Supported |
| Clean and automatically compress client logs | Supported | Supported | Supported | Supported |
| Collect client logs | Supported | Supported | Supported | Supported |
| Locate network-connection failures with port detection | Supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifiers and matrix anchors. Row-level milestones record appearance or change only; the port-detection row has no starting version, so its version applicability remains uncertain.

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
