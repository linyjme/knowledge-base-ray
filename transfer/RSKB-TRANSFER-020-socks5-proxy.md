---
id: RSKB-TRANSFER-020
title: Can a transfer use a SOCKS5 proxy?
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
  - Is proxy support documented for file transfer?
  - What prerequisites must be confirmed before routing through SOCKS5?
  - Does a supported proxy guarantee performance?
keywords: ["SOCKS5 proxy", "proxy transfer", "network prerequisite", "proxy policy"]
legacy_ids: ["RS-FEAT-046"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-013", "RSKB-TRANSFER-021"]
source_refs:
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-046 | Support SOCKS5 proxy
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can a transfer use a SOCKS5 proxy?

## Short answer

Yes. SOCKS5 proxy is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.** The entry does not document a universal UI path, address, authentication method, or automatic fallback.

Confirm proxy availability, credentials handling, policy, routing, and reachability. Capability does not guarantee throughput.
