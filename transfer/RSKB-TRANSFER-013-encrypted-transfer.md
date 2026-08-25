---
id: RSKB-TRANSFER-013
title: How do I use encrypted transfer?
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
  - Which documented cryptography protects transfer data?
  - Can an administrator force encryption over a local preference?
  - Do all transfer modes promise identical protection?
keywords: ["encrypted transfer", "TLS", "AES-256", "transfer security"]
legacy_ids: ["FAQ-TRANSFER-013", "RS-FEAT-037", "RS-FEAT-038"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-002", "RSKB-TRANSFER-020"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-013 | How do I use encrypted transfer?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-037 | Support TLS+AES-256 encryption algorithm
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-038 | Support switching non-encrypted/encrypted mode
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I use encrypted transfer?

## Short answer

Use the control documented for the relevant surface:

1. In the desktop client, open **Settings > Advanced Settings** and enable **Priority to use encrypted transfer**.
2. In cloud-style client settings, open **Transfer Security** and enable **Enable encrypted for transfer**.
3. For a sync task, enable encrypted transfer in the task's **Security** settings before starting it.

If an administrator forces encrypted transfer, it remains enabled regardless of a local preference. The matrix documents **TLS plus AES-256** and switching encrypted or non-encrypted mode.

The sources do not make a universal **identical encryption** promise across every mode or protocol. Both capabilities are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
