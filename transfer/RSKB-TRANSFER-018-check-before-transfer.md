---
id: RSKB-TRANSFER-018
title: What does checking before transfer do?
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
  - What preflight capability is documented before data moves?
  - Is a pre-transfer check equivalent to final integrity validation?
  - Which editions include transfer prechecking?
keywords: ["check before transfer", "pre-transfer check", "preflight inspection", "transfer validation"]
legacy_ids: ["RS-FEAT-049"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-012", "RSKB-TRANSFER-017"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-049 | Support Check before transfer
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What does checking before transfer do?

## Short answer

The matrix documents Check before transfer, but does not define its algorithm, pass criteria, UI path, or guarantee final target correctness. Treat it separately from post-transfer size/time and hash verification.

It is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.** Transfer RS-FEAT-049 pairs with sync RS-FEAT-071: transfer supported in SMB while sync unsupported in SMB.
