---
id: RSKB-TROUBLE-003
title: Troubleshoot stalled or slow transfer tasks
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
- Why is an ordinary transfer slower than expected?
- How can bandwidth limits or packet settings affect transfer speed?
- What evidence should I collect for a task that remains stalled?
keywords:
- slow transfer
- bandwidth limit
- UDP speed
- packet size
- Why is my Raysync transfer slower than expected?
- transfer stuck
- paused
- task details
legacy_ids:
- FAQ-TROUBLE-006
safety_tags:
- authorization
- license-control
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-008 | Why is my Raysync transfer slower than expected?
  evidence_type: generated-faq
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-006 | Why does my general transfer task appear stuck or not progress?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot stalled or slow transfer tasks

## Short answer

Open the desktop client task list and inspect the general transfer task and its file details. Raysync shows progress, speed, file status, transfer count, and an error reason. A general transfer task may be paused, waiting for the configured unchanged-file check, or unable to progress because of connectivity, permission, or server errors.

## Diagnostic boundary

Treat an ordinary slow or stalled transfer separately from the unactivated-server 5 Mbps license cap and from a failed required port. Compare task evidence before assigning one of those narrower causes.

## Likely cause

Documented causes include a paused task, a pre-transfer check waiting for the file to remain unchanged for the configured interval, or a reported transfer error. Error Detection can expose failed port connectivity and produce a diagnostic report.

## What the user can check

Confirm the client is running. Open **Transfer List**, double-click the general transfer task, and inspect its file status, error reason, speed, transmission mode, delay, and packet loss. A Start or Retry control may be available, but do not use it until the task evidence and error reason have been reviewed. Run **Error Detection** if the task still does not progress.

## When to contact an administrator

Contact the administrator if port checks fail, the task reports a server or permission error, or retries fail. Provide the task name, time, status, and client error-detection report.

## Version differences

Version 8.1.8.7 added task-name/status filtering and more detailed failure information in operation logs; client task details already exposed file error reasons.

## Important notes

Do not delete a task until its details needed for diagnosis are recorded.

## Related documented boundaries

- **Why is my Raysync transfer slower than expected?:** Speed can be limited by client maximum-speed settings, administrator global or time-period limits, group/user limits, server bandwidth, network quality, or the unactivated-server 5 Mbps default. Start with bandwidth settings, task evidence, and **Error Detection** rather than firewall port lists.
