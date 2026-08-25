---
id: RSKB-ADMIN-049
title: Which editions support statistics periods and custom notifications?
product: raysync
components:
- admin-portal
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
- Can all Raysync tiers configure reporting periods and custom or system notifications?
- Which editions include both statistics-period settings and notification customization?
- Does the feature matrix limit reporting windows or custom notices to a particular
  tier?
- Are administrator-defined statistics reporting intervals available?
- Are custom notification messages included across product tiers?
- Can the reporting interval for statistics be chosen by an administrator?
- Are customizable notification messages available in each edition?
keywords:
- statistics period
- custom notifications
- system notifications
- reporting window
- edition matrix
legacy_ids:
- RS-FEAT-185
- RS-FEAT-186
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-185 | Set statistics period
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-186 | Support custom notifications and system notifications
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support statistics periods and custom notifications?

## Short answer

The supplied feature matrix documents the following exact availability:

- Set statistics period: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Support custom notifications and system notifications: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Configurable statistics period | Supported | Supported | Supported | Supported |
| Custom and system notifications | Supported | Supported | Supported | Supported |

The source references preserve the canonical feature identifiers and matrix anchors. The notification row has a source milestone, while the statistics-period row has no starting version; neither fact establishes a minimum version for the combined article.

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
