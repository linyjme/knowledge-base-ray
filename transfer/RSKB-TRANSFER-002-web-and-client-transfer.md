---
id: RSKB-TRANSFER-002
title: What is the difference between web and client transfer?
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
  - Should I choose browser-only transfer or the desktop client?
  - Which transfer mode works without a running client?
  - Why is one transfer mode missing from my portal?
keywords: ["web transfer", "client transfer", "browser transfer", "desktop client"]
legacy_ids: ["FAQ-TRANSFER-002", "RS-FEAT-027"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-001", "RSKB-TRANSFER-003", "RSKB-TRANSFER-005"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-002 | What is the difference between a web transfer and a client transfer?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What is the difference between web and client transfer?

## Short answer

Web transfer uses the user portal HTTP web mode without a running desktop client. Client transfer uses the installed Raysync client for client-dependent capabilities. The server can expose either mode or both, so the visible choice depends on server configuration and edition.

For HTTP web capability, **Supported in SMB, Enterprise, and Multiple Spaces; unsupported in Cloud.** Do not generalize this entry into a claim that Cloud lacks every browser or transfer workflow.
