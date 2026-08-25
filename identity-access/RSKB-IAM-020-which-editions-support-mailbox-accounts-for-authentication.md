---
id: RSKB-IAM-020
title: Which editions support mailbox accounts for authentication?
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
- Is Enterprise the only edition that authenticates against a mailbox server?
- Can an existing email account be used to sign in to Cloud?
- Does SMB support mailbox-account authentication for transfer users?
keywords:
- mailbox account authentication
- existing email login
- edition identity integration
- administrator mailbox setup
legacy_ids:
- RS-FEAT-127
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-127 | Connection to mailbox server, can use the existing mailbox account as the transfer system account
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support mailbox accounts for authentication?

## Short answer

Using existing mailbox accounts as transfer-system accounts is documented as SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-127
- Capability domain: User Management
- Original source text: Connection to mailbox server, can use the existing mailbox account as the transfer system account
- Description: This entry describes the Raysync capability "Connection to mailbox server, can use the existing mailbox account as the transfer system account." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Explicitly supported editions: Enterprise
- Explicitly unsupported editions: SMB, Cloud, Multiple Spaces
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 127
- Search keywords: Raysync, User Management, Connection to mailbox server, can use the existing mailbox account as the transfer system account, Enterprise

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
