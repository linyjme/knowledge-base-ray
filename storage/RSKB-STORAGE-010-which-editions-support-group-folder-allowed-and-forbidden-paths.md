---
id: RSKB-STORAGE-010
title: Which editions support group-folder allowed and forbidden paths?
product: raysync
components:
- admin-portal
- file-service
domain: storage
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Can SMB restrict a group folder with allowed and forbidden paths?
- Why are group-folder path rules unavailable in Cloud?
- Can administrators in Multiple Spaces define both allow and deny paths for group files?
keywords:
- group-folder path rules
- allowed forbidden paths
- edition directory restrictions
- administrator path policy
legacy_ids:
- RS-FEAT-163
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-163 | Support setting forbidden access paths and allowed access paths
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support group-folder allowed and forbidden paths?

## Short answer

Allowed and forbidden access paths for group folders are documented as SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-163
- Capability domain: Group Folders
- Original source text: Support setting forbidden access paths and allowed access paths
- Description: This entry describes the Raysync capability "Support setting forbidden access paths and allowed access paths." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Multiple Spaces
- Explicitly unsupported editions: Cloud
- Source version note: 6.7.8.3
- Source location: Raysync Feature list.xlsx / English-New / row 163
- Search keywords: Raysync, Group Folders, Support setting forbidden access paths and allowed access paths, SMB, Enterprise, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
