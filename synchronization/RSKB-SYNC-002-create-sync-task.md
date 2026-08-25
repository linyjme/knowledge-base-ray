---
id: RSKB-SYNC-002
title: How do I create a sync task?
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
  - Where can I set up directory synchronization?
  - What must I configure before saving a sync job?
  - Which prerequisites are required to create synchronization?
keywords: [create sync task, source path, target path, sync permission, client]
legacy_ids: [FAQ-SYNC-002]
safety_tags: [authorization, destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-003, RSKB-SYNC-004, RSKB-SYNC-005, RSKB-SYNC-013]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-002 | How do I create a sync task?
    evidence_type: generated-faq
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I create a sync task?

## Short answer

Install and start the Raysync client, sign in to the user portal, and confirm that the administrator has enabled synchronization and granted your account **Sync Folder** permission. Open **Sync**, select **Create Sync Task**, and then set the task name, mode, source path, target path, and frequency.

## Authorization and preconditions

Use an account with **Sync Folder** permission after the administrator enables synchronization. Keep the client running, and confirm that both source and target paths are accessible under the intended account.

## Exact target and effect

Record the exact task name, mode, source path, target path, and frequency. The task applies the selected direction, same-name behavior, filters, synchronized deletion, and post-sync processing to those paths; those options can change or remove content.

## Confirmation

Before selecting **Create**, confirm the authoritative side, exact paths, schedule, encryption, existing-target behavior, filters, and every deletion or source-processing option.

## Recovery boundary

Keep a verified backup or approved recovery path for valuable source and target content before enabling synchronized deletion, overwrite, or post-sync cleanup. The supplied task-creation evidence does not define a universal recovery control.

## Post-action verification

After creation, check that the sync task list shows the intended name, mode, paths, schedule, and status. Verify transfer details and the expected target content before relying on later automatic runs.

Before selecting **Create**, review encryption, file handling, existing-target behavior, and filters. In particular, confirm any synchronized-deletion or post-sync source-processing option because those settings can remove files. After creation, use the sync task list to check task status and transfer details.
