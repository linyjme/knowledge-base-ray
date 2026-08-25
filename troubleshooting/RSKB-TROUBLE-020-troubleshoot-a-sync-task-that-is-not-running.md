---
id: RSKB-TROUBLE-020
title: Troubleshoot a sync task that is not running
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why is my synchronization task staying Idle?
- How can a schedule prevent a sync task from running now?
- What client and permission checks apply when synchronization never starts?
keywords:
- sync not running
- Idle
- Schedule
- sync permission
- desktop client
- Why is my sync task not running?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-015
safety_tags:
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-015 | Why is my sync task not running?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot a sync task that is not running

## Short answer

A sync task can be waiting normally for its next interval or scheduled time. The client labels these states **Idle**, **Schedule**, or **Idle (completion time)**. Sync also requires administrator permission, the global sync switch, and a running client.

## Likely cause

The next scheduled time has not arrived, the client is not running, your account lacks sync permission, the global sync function is disabled, or the task configuration/path no longer permits the operation.

## What the user can check

Open the client’s sync task list, read the status, schedule, source, and target paths, and confirm the client remains connected. Do not treat a documented waiting status as a failure.

## When to contact an administrator

Contact the administrator if sync permission or the global switch is disabled, paths are inaccessible, or the task shows an error after its scheduled time. Provide task details and the error-detection report.

## Version differences

Version 8.1.8.3 added real-time sync updates; that mode supports upload and local storage only. Version 8.1.8.7 improved desktop-client sync.

## Important notes

> **Warning:** Sync processing modes can delete data. **Delete target file synchronously when source deleted** propagates a source deletion to the target. Other documented modes can automatically delete source files or move them and clear them later. Verify the source, target, and processing mode before any retry; do not execute the retry as a test.

Do not use a retry as a test if you do not understand the configured deletion behavior. Preserve the task details and ask the administrator before changing a shared or business-critical sync task.
