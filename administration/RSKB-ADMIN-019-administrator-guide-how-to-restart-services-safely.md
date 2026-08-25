---
id: RSKB-ADMIN-019
title: 'Administrator guide: how to restart services safely'
product: raysync
components:
- admin-portal
domain: administration
access_level: public
audience:
- administrator
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- How do I restart a service after it becomes abnormal?
- Can I restart Rayfile from the admin page?
- What should I consider before restarting server services?
keywords:
- restart service
- maintenance window
- active task
- server status
- recovery verification
- restart services
- safely
legacy_ids:
- KB-SERVICE-002
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-002-how-to-restart-service-safely.md
  section: How to restart services safely?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to restart services safely

## Short answer

Only an administrator should restart services through the “Restart Service” operation provided by the admin console. A full restart affects access to all related services, while an individual restart mainly affects the selected Rayfile, peer-to-peer, or FTP service. Either operation may interrupt related sign-ins, file browsing, or transfers, so confirm the scope, check tasks, and choose a maintenance window first.

## Prerequisites

This applies in version 8.1.8.7 when the page explicitly says a restart is required, or when a transfer service shows “Not Running” under “Server Status” and an administrator has completed the basic checks.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **restart services safely** in the intended deployment, edition, and component.

## Effect

Only an administrator should restart services through the “Restart Service” operation provided by the admin console. A full restart affects access to all related services, while an individual restart mainly affects the selected Rayfile, peer-to-peer, or FTP service. Either operation may interrupt related sign-ins, file browsing, or transfers, so confirm the scope, check tasks, and choose a maintenance window first.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Check Server Status and record the service to recover. If only Rayfile, peer-to-peer, or FTP is affected, prefer the individual restart entry provided for that status item to avoid expanding the impact. Evaluate a full restart only when several related services or a global configuration must recover together.
2. Open “Real-time Tasks” in the admin console and check for active transfers. If any exist, wait for completion or postpone the restart to an approved maintenance window, and notify affected users.
3. Use “Restart Service” on the admin console home page, or click the corresponding service status and select “Restart Service” in the confirmation dialog. Do not click repeatedly.
4. Wait until the page reports a successful restart or finishes reloading, then check “Server Status.”
5. Verify with a small non-sensitive file or the originally affected feature, and notify users to resume only after recovery is confirmed.

## Recovery boundary

If the restart does not complete for an extended period, the status remains “Not Running,” or the problem quickly returns, stop repeated restarts. Retain the visible error, time, and impact scope, and continue classifying the issue by network, certificate, and configuration conditions.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The service is briefly unavailable during restart. After completion, the page is accessible, the corresponding service shows “Running Normally,” and the limited verification succeeds. A restart does not guarantee that an incorrect port, network, certificate, or permission configuration is fixed.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. Regular users, anyone who cannot determine the impact on active tasks, and anyone who cannot see the in-product restart entry should contact an administrator. In safe mode, or when the page shows only a restart prompt without an in-product entry, do not attempt a restart outside the product interface; hand it to the deployment administrator or technical support. If repeated attempts fail or several services are unavailable, the administrator should escalate to technical support.

