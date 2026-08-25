---
id: RSKB-TRANSFER-023
title: Which transfer acceleration features are documented?
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
  - What capabilities address huge directories and small-file disk work?
  - Which transport optimizations are listed for current transfer?
  - Do acceleration features promise a specific gain?
keywords: ["transfer acceleration", "millions of files", "small-file optimization", "multi-channel", "GSO"]
legacy_ids: ["RS-FEAT-028", "RS-FEAT-029", "RS-FEAT-053", "RS-FEAT-054"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-008", "RSKB-TRANSFER-014", "RSKB-TRANSFER-022"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-028 | Support high-speed transfer of millions of files in a single directory with UDP
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-029 | Support small file disk IO optimization
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-053 | Support for multi‑channel transfer.
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-054 | Support for GSO (Generic Segmentation Offload).
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Which transfer acceleration features are documented?

## Short answer

The matrix documents UDP high-speed transfer for millions of files in one directory, small-file disk I/O optimization, multi-channel transfer, and GSO. Each is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**

These capability statements provide **no performance guarantee**. Results depend on configuration, server prerequisites, storage, CPU, concurrency, limits, and network.
