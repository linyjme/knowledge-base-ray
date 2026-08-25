---
id: RSKB-TRANSFER-015
title: Where can I see transfer logs and failure details?
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
  - How do I inspect a failed file error reason?
  - What sanitized evidence should I retain for support?
  - Where can the client run error detection?
keywords: ["transfer logs", "failure details", "error reason", "diagnostic report"]
legacy_ids: ["FAQ-TRANSFER-015"]
safety_tags: ["sensitive-diagnostics"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-004", "RSKB-TRANSFER-006"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-015 | Where can I see transfer logs and failure details?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Where can I see transfer logs and failure details?

## Short answer

Open the transfer list and task details for file-level status and error reasons. Client Error Detection can check versions, connectivity, startup privilege, UDP speed, and configuration.

Retain task ID, direction, timestamps, sanitized error summary, and relevant logs. Do not publish credentials, internal addresses, real file contents, or unrestricted original logs.
