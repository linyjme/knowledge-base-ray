---
id: RSKB-SYNC-017
title: Can synchronization preserve file ACL attributes?
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
  - Can a sync job retain file access-control attributes?
  - Are source permissions preserved on the target system?
  - Does ACL preservation guarantee identical permissions across platforms?
keywords: [file ACL, access control, permission attributes, same system, compatible systems]
legacy_ids: [RS-FEAT-072]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-016]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-072 | Support file ACL attribute (it can be preserve on the same system)
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can synchronization preserve file ACL attributes?

## Short answer

Yes, within the documented boundary. The feature matrix lists file ACL attribute preservation for Enterprise, Cloud, and Multiple Spaces editions, not SMB, and explicitly limits preservation to the same system.

Treat this as requiring compatible systems and a verified access-control policy. The evidence does not establish cross-platform equivalence, identity mapping, or an end-user configuration procedure. Confirm source and target compatibility and verify the resulting permissions before relying on ACL preservation for protected content.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB. The equivalent transfer-domain ACL feature also supports SMB.
