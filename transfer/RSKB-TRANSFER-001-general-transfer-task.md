---
id: RSKB-TRANSFER-001
title: What is a general transfer task?
product: raysync
components: [user-portal, desktop-client]
domain: transfer
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - What does a one-time Raysync transfer do?
  - When should I use an ordinary transfer rather than sync?
  - Is an upload or download a recurring job?
keywords: ["general transfer", "one-time upload", "one-time download", "transfer task"]
legacy_ids: ["FAQ-TRANSFER-001"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-002", "RSKB-TRANSFER-003"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-001 | What is a general transfer task?
    evidence_type: generated-faq
  - file: source_file/normal-transfer.md
    section: Normal upload and download
    evidence_type: technical-boundary-document
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What is a general transfer task?

## Short answer

A general transfer task is a one-time upload or download between local and server storage. It is separate from recurring synchronization and peer-to-peer transfer. Availability and direction depend on server configuration, permissions, and the transfer entry offered to the user.

A request being accepted does not prove that the file arrived. Monitor the task through its final state and verify the target when the result matters.
