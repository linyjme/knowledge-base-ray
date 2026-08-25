---
id: RSKB-SYNC-001
title: What is a sync task, and how does it differ from a transfer?
product: raysync
components: [user-portal, desktop-client]
domain: synchronization
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - What does a Raysync synchronization task do?
  - Is directory synchronization the same as sending files once?
  - When should I use sync instead of a general transfer task?
keywords: [sync task, general transfer, directory alignment, repeated transfer, schedule]
legacy_ids: [FAQ-SYNC-001]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-002, RSKB-SYNC-003, RSKB-SYNC-005]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-001 | What is a sync task, and how is it different from a general transfer task?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What is a sync task, and how does it differ from a transfer?

## Short answer

A sync task keeps a local directory and a server directory aligned according to a direction and schedule. It remains in the sync task list and can run again at a configured time or interval. A general transfer task sends a selected set of files once and is listed separately in the desktop client.

Sync can upload local content, download server content, or operate in both directions. It also has synchronization-specific controls for source updates, modification times, filters, and existing target files. The Raysync client must be running, synchronization must be enabled, and the account must have sync permission.
