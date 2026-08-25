---
id: RSKB-TRANSFER-004
title: Where can I see transfer progress and task details?
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
  - How can I tell whether a submitted job is actually moving data?
  - Where are file-level status and error reasons shown?
  - What evidence proves that a transfer has finished?
keywords: ["transfer progress", "task details", "final state", "target verification"]
legacy_ids: ["FAQ-TRANSFER-004"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-003", "RSKB-TRANSFER-015"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-004 | Where can I see transfer progress and task details?
    evidence_type: generated-faq
  - file: source_file/task-lifecycle.md
    section: Task life cycle
    evidence_type: technical-boundary-document
  - file: source_file/task-lifecycle(1).md
    section: "Cross-project task life cycle: from request to file result"
    evidence_type: technical-boundary-document
  - file: source_file/task-lifecycle(2).md
    section: Native task life cycle
    evidence_type: technical-boundary-document
  - file: source_file/state-and-exit-codes.md
    section: Task status and synchronization command line exit code FAQ
    evidence_type: technical-boundary-document
  - file: source_file/submission-no-progress.md
    section: The task has been submitted but there is no progress
    evidence_type: technical-boundary-document
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# Where can I see transfer progress and task details?

## Short answer

Use the client Transfer List for client transfers and the portal transfer list for web uploads. Open task details for file-level status, byte progress, failures, and error reasons.

Keep these boundaries distinct: **request accepted**, **task created**, **worker started**, visible **progress**, the task **final state**, and independent **target verification**. Each is separate evidence. Re-query stale status before creating duplicates.
