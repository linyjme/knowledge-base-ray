---
id: RSKB-IAM-017
title: Which editions support simultaneous account sessions?
product: raysync
components:
- admin-portal
domain: identity-access
access_level: public
audience:
- administrator
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Does any edition limit how many terminals can use one account simultaneously?
- Are concurrent sessions for a single account unlimited in Cloud?
- What session limit does the matrix give SMB and Multiple Spaces?
keywords:
- simultaneous account sessions
- concurrent terminal access
- edition session limits
- administrator login policy
legacy_ids:
- RS-FEAT-017
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-017 | Simultaneous login and access of single account and multiple terminals
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which editions support simultaneous account sessions?

## Short answer

Simultaneous use of one account from multiple terminals is documented as SMB: Unlimited; Enterprise: Unlimited; Cloud: Unlimited; Multiple Spaces: Unlimited. A blank cell remains unspecified and must not be read as unsupported.

## Scope and evidence

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

## Documented details

- Knowledge base ID: RS-FEAT-017
- Capability domain: Client App
- Original source text: Simultaneous login and access of single account and multiple terminals
- Description: This entry describes the Raysync capability "Simultaneous login and access of single account and multiple terminals." Use the edition availability field below for exact edition differences.
- Edition availability: SMB: Unlimited; Enterprise: Unlimited; Cloud: Unlimited; Multiple Spaces: Unlimited
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 17
- Search keywords: Raysync, Client App, Simultaneous login and access of single account and multiple terminals, SMB, Enterprise, Cloud, Multiple Spaces

## Interpretation and recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The administrator verifies the edition cell and applies only the explicitly documented availability statement.

## Escalation

Escalate with the product version, edition, component, and observed result; do not include credentials or private data.
