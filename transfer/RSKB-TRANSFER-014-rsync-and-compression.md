---
id: RSKB-TRANSFER-014
title: What do Rsync verification and data compression do?
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
  - How does incremental comparison differ from compression?
  - Will a partially changed file send changed data or the whole file?
  - Does Rsync decide the overwrite policy?
keywords: ["Rsync verification", "data compression", "changed portions", "whole-file retransmission"]
legacy_ids: ["FAQ-TRANSFER-014", "RS-FEAT-040", "RS-FEAT-042"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-010", "RSKB-TRANSFER-012", "RSKB-TRANSFER-023"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-014 | What do Rsync verification and data compression do?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-040 | Automatic selection of compression scheme based on file type during transfer
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-042 | Support Rsync algorithm to upload and download files
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What do Rsync verification and data compression do?

## Short answer

Rsync compares local and server data; compression reduces transmitted representation and does not verify integrity. Same-name policy remains separate.

The FAQ says matching portions can be skipped and **changed portions** transferred, but also describes **whole-file** retransmission after a differing overall check. The **sources do not specify** the exact condition selecting them, so this ambiguity remains unresolved.

Compression selection and Rsync are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
