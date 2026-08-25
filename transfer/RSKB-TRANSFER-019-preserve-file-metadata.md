---
id: RSKB-TRANSFER-019
title: Which file metadata can a transfer preserve?
product: raysync
components: [desktop-client]
domain: transfer
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Can destination timestamps remain the same as the source?
  - When can ACL attributes survive a transfer?
  - What Linux-specific owner behavior is documented?
keywords: ["file metadata", "preserve timestamps", "file ACL", "Linux owner group"]
legacy_ids: ["RS-FEAT-039", "RS-FEAT-041", "RS-FEAT-050"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-018", "RSKB-TRANSFER-022"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-039 | Support for preserving file timestamps after transfer is completed
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-041 | Automatically update file owner and file owner's user group (Linux server only)
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-050 | Support file ACL attribute (it can be preserve on the same system)
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Which file metadata can a transfer preserve?

## Short answer

The matrix documents preserving timestamps, updating owner and group on a **Linux server only**, and preserving ACL attributes on the **same system**. It does not establish cross-platform identity or ACL equivalence.

Each is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.** Transfer RS-FEAT-050 pairs with sync RS-FEAT-072: transfer supported in SMB while sync unsupported in SMB.
