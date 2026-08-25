---
id: RSKB-TRANSFER-016
title: What should I know about a server-issued task?
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
  - What must an endpoint user prepare for centrally created work?
  - Who chooses paths and schedules for an administrator task?
  - Why verify deletion and overwrite options before staying online?
keywords: ["server-issued task", "online client", "administrator task", "default server"]
legacy_ids: ["FAQ-TRANSFER-016"]
safety_tags: ["authorization", "destructive-operation"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-005", "RSKB-TRANSFER-021"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-016 | What should I know about a server task issued by an administrator?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# What should I know about a server-issued task?

## Short answer

Install and start the client, configure the correct default server, sign in, and keep the endpoint online. The administrator creates and monitors the task.

**Data-loss warning:** such tasks can include overwrite, deletion propagation, or source cleanup. Verify paths, direction, schedule, deletion options, and same-name policy first. Creation does not prove worker start, progress, final success, or target correctness.
