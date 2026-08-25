---
id: RSKB-IAM-023
title: Which editions support a custom HTTP user system?
product: raysync
components:
- admin-portal
domain: identity-access
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
- Can Enterprise connect to a custom identity system over HTTP?
- Is an HTTP-based external user directory supported by Cloud?
- Do SMB or Multiple Spaces include custom HTTP user integration?
keywords:
- custom HTTP user system
- external identity interface
- Enterprise HTTP integration
- administrator user-system connection
legacy_ids:
- RS-FEAT-130
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-130 | User system customization connection with Http interface
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support a custom HTTP user system?

## Short answer

Connecting a custom user system through an HTTP interface is documented as SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-130
- Capability domain: User Management
- Original source text: User system customization connection with Http interface
- Description: This entry describes the Raysync capability "User system customization connection with Http interface." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 130
- Search keywords: Raysync, User Management, User system customization connection with Http interface, Enterprise

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
