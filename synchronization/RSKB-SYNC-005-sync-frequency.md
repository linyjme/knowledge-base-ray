---
id: RSKB-SYNC-005
title: How often can a sync task run?
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
  - Can synchronization run once or on a recurring schedule?
  - How do daily interval and weekly sync schedules differ?
  - Why can I not change my task frequency?
keywords: [sync frequency, interval, daily schedule, weekly schedule, once]
legacy_ids: [FAQ-SYNC-005]
safety_tags: []
supersedes: []
superseded_by: []
related_articles: [RSKB-SYNC-001, RSKB-SYNC-006, RSKB-SYNC-007]
source_refs:
  - file: raysync-user-faq/05-file-synchronization.md
    section: FAQ-SYNC-005 | How often can a sync task run?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-056 | Setting sync frequency
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How often can a sync task run?

## Short answer

A sync task can run once at a specified time, daily at a fixed time, repeatedly at an interval, or weekly on selected days at a specified time. An interval task can show **Idle** until its next run, while a daily task can show **Schedule** before its time and **Idle (completion time)** after that day's run.

The **Once** schedule was added in version 6.0.0.8 and weekly synchronization in version 6.3.8.0. An administrator can enforce a sync-task frequency; when that policy applies, the user cannot change the frequency while creating or editing the task.

## Availability

Supported in Enterprise, Cloud, and Multiple Spaces; unsupported in SMB.
