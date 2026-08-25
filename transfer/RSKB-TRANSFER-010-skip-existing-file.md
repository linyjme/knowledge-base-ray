---
id: RSKB-TRANSFER-010
title: Can Raysync skip a file that already exists?
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
  - How can I avoid retransmitting content already at the destination?
  - Is there one universal skip-every-existing-name option?
  - Does incremental comparison replace same-name policy?
keywords: ["skip existing", "only new files", "existing target", "incremental transfer"]
legacy_ids: ["FAQ-TRANSFER-010", "RS-FEAT-030"]
safety_tags: ["authorization", "destructive-operation"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-011", "RSKB-TRANSFER-014", "RSKB-TRANSFER-017"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-010 | Can Raysync skip a file that already exists?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-030 | Skip existing files at high speed during transfer
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Can Raysync skip a file that already exists?

## Short answer

Raysync documents high-speed skipping of existing files, but not one universal skip-every-existing-name rule for every workflow. Only-new, Rsync, filters, and same-name policies are distinct.

Confirm direction and policy before transfer. High-speed skip-existing capability is **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
