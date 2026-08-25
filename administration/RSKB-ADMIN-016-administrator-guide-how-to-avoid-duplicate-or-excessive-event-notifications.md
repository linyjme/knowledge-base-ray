---
id: RSKB-ADMIN-016
title: 'Administrator guide: how to avoid duplicate or excessive event notifications'
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
- How do I avoid duplicate or excessive event notifications?
- Why did the same event trigger several notifications?
- How do I investigate two similar notifications sent to one mailbox?
keywords:
- duplicate notification
- overlapping rule
- duplicate recipient
- trigger condition
- notification frequency
- scope too broad
- avoid duplicate
- or excessive
legacy_ids:
- KB-EVENT-008
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-008-how-to-avoid-duplicate-notifications.md
  section: How to avoid duplicate or excessive event notifications
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to avoid duplicate or excessive event notifications

## Short answer

First check whether several enabled rules match the same event. Then check whether the same email address is included in several notification points through different roles, such as creator, sender, recipient, or administrator. Retain only necessary rules, narrow their scope, and verify success/failure conditions to reduce duplicate or excessive notifications.

## Prerequisites

This applies in version 8.1.8.7 when one operation produces several callbacks, one person receives several similar system emails, or high-frequency operations generate too many notifications. Similar content is not necessarily a duplicate when different notification points target different roles.



## Effect

Disabling a rule or notification point stops its future actions or messages; narrowing scope changes future recipients, and changing a threshold changes when storage alerts occur. These changes do not remove previously sent messages or event history.

## Confirmation

Confirm each exact overlapping rule or notification point, its business owner, affected recipients, required success or failure conditions, and the one change to test before saving.

## Procedure

1. In the custom “Events” list, check all enabled rules by event type. If several rules of the same type are allowed, every matching rule may perform its own action.
2. Under “System Notifications,” separately review user and administrator, success and failure, and peer-to-peer sender and recipient notification points. Disable items that the business does not need.
3. Check the transfer-user, recipient-administrator, and file-library scopes to avoid overly broad coverage, then determine whether the same email address belongs to several event roles.
4. Enable “Do not send email notifications for instant-transfer files” only as needed for the “Notify creator when a transfer task succeeds” and “Notify space administrator when a transfer task succeeds” points. Do not assume this setting applies to failure notifications or peer-to-peer send/receive notifications. Set reasonable thresholds for storage notifications.
5. Change only one item at a time, verify with a new event that has a clear timestamp, and record the email subject, notification point, and trigger count.

## Recovery boundary

Compare the subject, event time, and target role of each email to determine whether it is the same event repeated or several events or notification points. Do not hide an unidentified overlapping configuration by disabling all notifications.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

After overlapping rules and unnecessary roles are removed, each subsequent event triggers only the actions required by the business. A person who genuinely has several recipient roles may still receive similar messages intended for different roles.

## Escalation

If you cannot view all rules, cannot determine recipient roles, the notification volume affects normal use, or duplicates continue after adjustments, contact an administrator. Provide the redacted subject, time, rule or notification point name, and occurrence count.
