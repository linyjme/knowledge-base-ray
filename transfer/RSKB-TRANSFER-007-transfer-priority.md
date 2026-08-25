---
id: RSKB-TRANSFER-007
title: How does transfer priority affect my tasks?
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
  - Why does another user job receive more bandwidth?
  - Can I reorder the client list to change role priority?
  - Who controls bandwidth scheduling priority?
keywords: ["transfer priority", "role priority", "bandwidth allocation", "task speed"]
legacy_ids: ["FAQ-TRANSFER-007"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-008", "RSKB-TRANSFER-009"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-007 | How does transfer priority affect my tasks?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How does transfer priority affect my tasks?

## Short answer

When enabled, role-based transfer priority can affect how available bandwidth is allocated. It is assigned through a user role, not by moving a task in the local list, and it does not promise a particular speed. Actual throughput also depends on limits, storage, CPU, and network conditions.

