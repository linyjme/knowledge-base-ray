---
id: RSKB-ADMIN-010
title: 'Administrator guide: which event notification types are supported in 8.1.8.7'
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
- Which event notification types are supported in 8.1.8.7?
- Which trigger conditions can I select when adding an event?
- Which notification points are available on the System Notifications page?
keywords:
- event type
- notification point
- file operation
- transfer task
- peer-to-peer transfer
- system notification
- which event
- notification types
legacy_ids:
- KB-EVENT-002
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-002-supported-event-types.md
  section: Which event notification types are supported in 8.1.8.7
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: which event notification types are supported in 8.1.8.7

## Short answer

On the custom “Events” page in version 8.1.8.7, you can select events for file operations, web transfer tasks, standard client transfers, client synchronization, and client peer-to-peer transfers. The “System Notifications” page provides a separate set of preset email notification points. Only items actually listed on the page can be configured directly.

## Scope and evidence

This applies when an administrator needs to confirm whether an event can be used for a custom callback or system email notification in version 8.1.8.7. Some types trigger only when the corresponding feature is enabled, the relevant operation actually occurs, and the current version and permissions allow it.



## Documented details

1. Custom file events include: file upload completed/failed, file download completed/failed, file deletion completed, folder deletion/creation/rename completed, and file rename completed.
2. Web task events include: web upload task completed/failed and web download task completed/failed.
3. Client task events include: standard upload completed/failed, standard download completed/failed, synchronization upload completed/failed, synchronization download completed/failed, bidirectional synchronization completed/failed, peer-to-peer send completed/failed, and peer-to-peer receive completed/failed.
4. Visible system email notification points include: locked-account sign-in, IP address added to the blocklist, member added to a group file library; transfer started, succeeded, or failed; peer-to-peer sender or recipient success/failure; user or group storage utilization reaching a threshold; and virus file detected.
5. The same business outcome may appear as separate system notification points for the creator, sender, recipient, space administrator, or administrator. Follow the labels displayed on the page.

## Interpretation and recovery boundary

If the target type is not listed, first confirm whether you are on the “Events” or “System Notifications” page, then verify the product version, feature switches, and authorization. Do not substitute a similar type for an unverified event.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The selected event type matches only when the corresponding scenario actually occurs. A disabled feature, an unmet storage threshold, or an operation whose success/failure status differs from the selected point does not trigger that notification point.

## Escalation

If the list differs from this document, the target module is unavailable, or the actual event status cannot be determined, ask the administrator to provide the product version, page name, expected event, and actual result so technical support can confirm version applicability.

