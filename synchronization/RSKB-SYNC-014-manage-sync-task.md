---
id: RSKB-SYNC-014
title: How do I pause, resume, disable, or remove a sync task?
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
  - Where can I stop and restart an existing synchronization job?
  - Does removing a sync task disable synchronization for my account?
  - Why is the sync feature unavailable for every task?
keywords: [pause sync, resume sync, delete task, disable sync, task list]
legacy_ids: [FAQ-SYNC-014]
safety_tags: [authorization]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-001, RSKB-SYNC-002, RSKB-SYNC-013]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-014 | How do I pause, resume, disable, or remove a sync task?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I pause, resume, disable, or remove a sync task?

## Short answer

Open the sync task list. You can pause a task, start it again, edit it, delete its task definition, or open its transfer details. Pausing prevents another run until the task is started again; deleting removes the task from the list.

There is no separately documented end-user global-disable control. If synchronization is unavailable for all tasks, the administrator may have disabled the global sync function or removed the account's **Sync Folder** permission. Pausing or deleting a task does not reverse file deletions that a completed run already performed.
