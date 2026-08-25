---
id: RSKB-TRANSFER-017
title: How do transfer file filters work?
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
  - How can a task exclude selected names or large files?
  - Is only-new-files the same as a size filter?
  - Which controls restrict the transfer input set?
keywords: ["file filters", "skip specified files", "size filter", "only new files"]
legacy_ids: ["RS-FEAT-031", "RS-FEAT-032", "RS-FEAT-033"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-010", "RSKB-TRANSFER-018"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-031 | Supports skipping specified files during transfer
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-032 | Support skipping files over a specified size during transfer
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-033 | Support only upload or download new files
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do transfer file filters work?

## Short answer

Filtering can skip specified files, skip files over a configured size, or restrict work to new files. These are separate rules and should not be assumed to match identically.

Confirm the resulting file list because filtered items can reduce a successful task result. All three capabilities are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
