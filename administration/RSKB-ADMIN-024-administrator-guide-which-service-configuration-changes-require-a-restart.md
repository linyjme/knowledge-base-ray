---
id: RSKB-ADMIN-024
title: 'Administrator guide: which service configuration changes require a restart'
product: raysync
components:
- admin-portal
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Must I restart after saving service settings?
- Which configurations display a service restart prompt?
- When does a changed peer-to-peer address take effect?
keywords:
- configuration takes effect
- restart required
- restart prompt
- peer-to-peer configuration
- TLS certificate
- which service
- configuration changes
- require a
legacy_ids:
- KB-SERVICE-007
safety_tags:
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-007-when-configuration-requires-restart.md
  section: Which service configuration changes require a restart?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: which service configuration changes require a restart

## Short answer

The following are verified but non-exhaustive examples in version 8.1.8.7: peer-to-peer service address or port, TLS certificate, "Prohibit Non-TLS Connections," server information on the home page, and options under "More Settings" that display a restart prompt. The primary rule is to follow the current page prompt after saving. Server-status viewing refreshes automatically and does not require a restart.

## Prerequisites

This applies when an administrator needs to determine when a saved service-related setting takes effect. This document lists only verified version 8.1.8.7 behavior and does not mean that other pages, versions, or settings follow the same rule.



## Effect

A prompted restart temporarily interrupts the affected service and applies the confirmed saved setting. Viewing service status is read-only and does not itself require a restart; unrelated services must not be restarted preemptively.

## Confirmation

Confirm the exact saved setting, visible restart prompt, affected service, active transfers, expected interruption, maintenance window, and post-restart check before accepting the restart.

## Procedure

1. Read the page result after saving. Do not proactively restart repeatedly before confirming that it is required.
2. After changing the peer-to-peer transfer service address or port, restart Peer-to-Peer Transfer Service through the confirmation dialog.
3. After updating the TLS certificate or changing "Prohibit Non-TLS Connections," restart services as prompted on the page.
4. After changing an editable item under "Server Information" on the home page, complete the operation through the restart confirmation or pending-restart reminder on the home page.
5. After changing an option under "More Settings" that displays a restart prompt, such as "Enable File Close," "Enable Event Notifications," "Support Multiple IP Addresses," or "Allow Process Count Configuration," follow the save result and page prompt.
6. To view current server status only, wait for automatic refresh or refresh the page manually.
7. Before restarting, open "Real-time Tasks" and check active transfers and usage impact. After restarting, check service status and verify the setting that was changed.

## Recovery boundary

If the restart prompt remains, the configuration returns to its old value, or the service does not recover, do not restart repeatedly. Record the setting name, save result, restart prompt, service status, and time for administrator review.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

A configuration that requires a restart operates with the new setting after a successful restart, and the pending-restart reminder disappears. Status viewing directly displays the current result. If the page does not explain how a setting takes effect, follow that page's prompt and the version documentation.

## Escalation

Service configuration and restarts are administrator operations. Regular users should record the symptom and avoid active tasks. In safe mode, or when only a restart prompt appears without an in-product entry, do not restart outside the product interface; contact the deployment administrator or technical support. Escalate when page prompts conflict or interruption impact cannot be confirmed.
