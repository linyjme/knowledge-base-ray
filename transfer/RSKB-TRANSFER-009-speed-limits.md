---
id: RSKB-TRANSFER-009
title: How do upload and download speed limits work?
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
  - Why is observed throughput below my client maximum?
  - Can a local bandwidth setting exceed an administrator cap?
  - What differs between a configured limit and achieved speed?
keywords: ["upload speed limit", "download speed limit", "bandwidth cap", "minimum speed"]
legacy_ids: ["FAQ-TRANSFER-009", "RS-FEAT-044"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-007", "RSKB-TRANSFER-008"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-009 | How do upload and download speed limits work?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-044 | Support limit upload and download maximum and minimum speed
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do upload and download speed limits work?

## Short answer

The client can configure maximum speeds and documented minimum send and receive settings; the server can impose stronger caps. A configured limit is **not guaranteed throughput** and cannot override an administrator cap.

Maximum and minimum speed limits are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
