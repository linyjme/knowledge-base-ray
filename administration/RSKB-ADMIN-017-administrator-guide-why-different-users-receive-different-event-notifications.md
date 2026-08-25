---
id: RSKB-ADMIN-017
title: 'Administrator guide: why different users receive different event notifications'
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
- Why do different users receive different event notifications?
- Why did some users receive email for the same transfer while others did not?
- Why are the notifications received by an administrator and a creator different?
keywords:
- notification difference
- rule scope
- membership
- event role
- email information
- permission difference
- why different
- users receive
legacy_ids:
- KB-EVENT-009
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-009-why-users-receive-different-notifications.md
  section: Why different users receive different event notifications
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: why different users receive different event notifications

## Short answer

System notifications are evaluated separately according to notification-point scope, role in the event, space or file-library membership, account email address, and administrative permissions. Two users involved in the same operation may be the creator, sender, recipient, or administrator respectively, so the type, content, and number of notifications they receive may differ.

## Scope and evidence

This applies in version 8.1.8.7 when only some users receive email for the same event, or when different users see different system notification settings and receive different content. Page visibility and configurable scope depend on the account’s role and permissions.



## Documented details

1. Identify each user’s role in the event: creator, peer-to-peer sender, recipient, regular member, space administrator, or recipient administrator.
2. Open the corresponding notification point settings and check the transfer-user, recipient-administrator, and file-library scopes. Do not use membership in another space or file library to infer this result.
3. Check whether each account has a valid email address, whether several accounts share the same address, or whether one person is included in the notification scope through several roles.
4. Confirm that each user can view and configure only the content allowed by their permissions. If an entry or object is not visible, ask an authorized administrator to check it.
5. Compare notification subject, role, email domain, and filtering result for the same trigger time to distinguish rule differences from email delivery differences.

## Interpretation and recovery boundary

Choose one user who received the message and one who did not, then compare the notification point, event role, space or file-library membership, email status, and spam handling item by item. Do not grant unnecessary administrator permissions for troubleshooting.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

Whether the system attempts to submit email depends on the notification point status, event role, rule scope or membership, and a valid recipient address. Whether the submitted email ultimately reaches the inbox depends on spam filtering, provider rejection, delivery delay, and other factors. Compare these two stages separately.

## Escalation

If you cannot view membership or notification scope, need to change roles or email addresses, or outcomes remain different for an extended period despite identical conditions, contact the administrator and email administrator. Provide the product version, notification point, account role, space or file-library name, and trigger time. Do not provide passwords.

