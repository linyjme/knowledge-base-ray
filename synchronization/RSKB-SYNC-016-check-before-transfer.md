---
id: RSKB-SYNC-016
title: Can a sync task check files before transfer?
product: raysync
components: [desktop-client]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Does synchronization support a pre-transfer file check?
  - Can Raysync inspect sync content before sending it?
  - Is check-before-transfer available for a synchronization job?
keywords: [check before transfer, pre-transfer check, sync files, verification, feature availability]
legacy_ids: [RS-FEAT-071]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-002, RSKB-SYNC-017]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-071 | Support Check before transfer
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can a sync task check files before transfer?

## Short answer

Yes. The feature matrix lists **Check before transfer** for synchronization in Enterprise, Cloud, and Multiple Spaces editions and lists it as unsupported in SMB.

The matrix establishes capability and edition availability, but it does not document an end-user procedure, the checks performed, or the result shown when a check fails. Confirm the deployed edition and use the controls presented by that version rather than assuming an undocumented workflow.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB. The equivalent transfer-domain feature also supports SMB.
