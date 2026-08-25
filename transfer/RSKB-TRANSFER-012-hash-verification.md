---
id: RSKB-TRANSFER-012
title: What does hash verification do?
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
  - How can I compare local and server file integrity?
  - Is post-transfer size checking the same as a checksum?
  - How does verification differ from a preflight check?
keywords: ["hash verification", "file integrity", "size and time", "post-transfer check"]
legacy_ids: ["FAQ-TRANSFER-012", "RS-FEAT-035", "RS-FEAT-036"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-006", "RSKB-TRANSFER-011", "RSKB-TRANSFER-018"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-012 | What does hash verification do?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-035 | File size and time automatic proofreading after the transfer is completed
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-036 | Hash automatic proofreading after the transfer is completed
    evidence_type: feature-matrix
  - file: source_file/completion-validation.md
    section: How to verify the completion result
    evidence_type: technical-boundary-document
  - file: source_file/target-verification.md
    section: Target file verification is inconsistent
    evidence_type: technical-boundary-document
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What does hash verification do?

## Short answer

Hash verification compares file hashes. It is different from automatic **size and time** proofreading after completion, and both differ from **Check before transfer**. These checks are not interchangeable.

A successful task or successful final state alone does not prove the target is correct. Independently verify that the target exists, has the expected type and expected size, and matches a checksum or hash when required. This independent delivery verification is distinct from the transfer checks above.

Size and time proofreading and hash proofreading are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
