---
id: RSKB-STORAGE-006
title: Which editions support user home storage and allowed paths?
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
- Can Cloud assign custom home storage and several virtual directories to a user?
- Do all editions support wildcard-based allowed and forbidden user paths?
- Are per-user home-directory restrictions available in SMB and Multiple Spaces?
keywords:
- user home storage
- allowed virtual paths
- edition directory controls
- administrator home assignment
legacy_ids:
- RS-FEAT-138
- RS-FEAT-139
- RS-FEAT-140
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-138 | Custom user's home directory storage space, and support multiple virtual directories
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-139 | Set the user's forbidden access path, support wildcards
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-140 | Set the user's allowed access path, support wildcards
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support user home storage and allowed paths?

## Short answer

Custom user home storage with virtual directories, forbidden paths with wildcards, and allowed paths with wildcards are each documented as SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-138
- Capability domain: User Management
- Original source text: Custom user's home directory storage space, and support multiple virtual directories
- Description: This entry describes the Raysync capability "Custom user's home directory storage space, and support multiple virtual directories." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 138
- Search keywords: Raysync, User Management, Custom user's home directory storage space, and support multiple virtual directories, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-139
- Capability domain: User Management
- Original source text: Set the user's forbidden access path, support wildcards
- Description: This entry describes the Raysync capability "Set the user's forbidden access path, support wildcards." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 139
- Search keywords: Raysync, User Management, Set the user's forbidden access path, support wildcards, SMB, Enterprise, Cloud, Multiple Spaces

- Knowledge base ID: RS-FEAT-140
- Capability domain: User Management
- Original source text: Set the user's allowed access path, support wildcards
- Description: This entry describes the Raysync capability "Set the user's allowed access path, support wildcards." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 140
- Search keywords: Raysync, User Management, Set the user's allowed access path, support wildcards, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
