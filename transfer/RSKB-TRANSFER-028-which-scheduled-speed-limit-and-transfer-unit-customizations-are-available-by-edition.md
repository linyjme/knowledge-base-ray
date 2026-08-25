---
id: RSKB-TRANSFER-028
title: Which scheduled speed-limit and transfer-unit customizations are available
  by edition?
product: raysync
components:
- admin-portal
- desktop-client
domain: transfer
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
- Can every edition schedule maximum-speed periods and display custom transfer units?
- Which tiers allow a configured speed limit below one megabit together with unit
  customization?
- Are time-based bandwidth caps and transfer-unit labels edition-specific?
- Can an administrator schedule changes to a bandwidth limit?
- Does the product support a low configurable transfer-speed ceiling?
- Can bandwidth limits change according to a schedule?
- How low may the configured transfer-speed limit go?
keywords:
- scheduled speed limit
- sub-megabit cap
- custom transfer unit
- bandwidth period
- edition matrix
legacy_ids:
- RS-FEAT-180
- RS-FEAT-179
- RS-FEAT-181
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-180 | Custom transfer units
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-179 | Custom maximum speed time period
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-181 | Can set the limited transfer speed to less than 1M
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which scheduled speed-limit and transfer-unit customizations are available by edition?

## Short answer

The supplied feature matrix documents the following exact availability:

- Custom transfer units: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Custom maximum speed time period: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Transfer limits below the source's “1M” threshold: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. The source does not define the unit represented by “1M.”

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Custom transfer units | Supported | Supported | Supported | Supported |
| Scheduled maximum-speed periods | Supported | Supported | Supported | Supported |
| Transfer limits below the source's “1M” threshold | Supported | Supported | Supported | Supported |

The source does not define the unit represented by 1M, so do not interpret it as a specific bit or byte rate. The source references preserve the canonical feature identifiers, literal wording, and matrix anchors. Row-level milestones are change evidence only.

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
