---
id: RSKB-TRANSFER-022
title: Can an upload preserve the source directory structure?
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
  - Will an uploaded tree retain its complete hierarchy at the target?
  - Is keeping the top source folder the same as relative paths?
  - Which editions document full upload structure retention?
keywords: ["source directory structure", "upload hierarchy", "relative paths", "preserve folders"]
legacy_ids: ["RS-FEAT-051"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-019", "RSKB-TRANSFER-023"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-051 | Reserve the complete structure of the source directory when uploading to the target
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can an upload preserve the source directory structure?

## Short answer

The matrix documents retaining the complete source directory structure on upload. Confirm whether the deployed option includes the top source folder or only descendants; the feature statement does not define that detail.

It is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.** Transfer RS-FEAT-051 pairs with sync RS-FEAT-074: transfer supported in SMB while sync unsupported in SMB.
