---
id: RSKB-ADMIN-011
title: 'Administrator guide: how to create an event notification rule'
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
- How do I create an event notification rule?
- Where do I add an event notification?
- How can I make a file event trigger an HTTP callback?
keywords:
- add event
- event rule
- HTTP callback
- executable program
- enable event
- save rule
- create an
- event notification
legacy_ids:
- KB-EVENT-003
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/event-notifications/KB-EVENT-003-how-to-create-event-notification.md
  section: How to create an event notification rule
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to create an event notification rule

## Short answer

An administrator can add a rule on the “Events” page under “System Configuration,” select the event type and event action, configure the receiving endpoint, and save. The receiving endpoint here is an executable program or HTTP callback service, not an email recipient. To send email to people, configure a preset notification point and recipient scope under “Notifications > System Notifications.”

## Prerequisites

This applies to version 8.1.8.7 environments that are authorized to use custom events and whose system administrator and receiving-endpoint owner have confirmed the security requirements. Availability of this entry depends on the product version and authorization.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **create an event notification rule** in the intended deployment, edition, and component.

## Effect

An administrator can add a rule on the “Events” page under “System Configuration,” select the event type and event action, configure the receiving endpoint, and save. The receiving endpoint here is an executable program or HTTP callback service, not an email recipient. To send email to people, configure a preset notification point and recipient scope under “Notifications > System Notifications.”

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Go to “System Configuration > More Settings > Event Settings” and select “Add Event.”
2. Select the exact “Event Type” and enter a unique, recognizable “Event Name.” You can use “Notes” to describe its purpose.
3. Under “Event Action,” select “Executable Program” or “HTTP Callback.” For an executable program, enter the trusted program location and required parameters. For an HTTP callback, enter the callback address, Headers, Body, and timeout supplied by the receiving-endpoint owner.
4. Select “Enable Event” as needed. Verify the receiving endpoint in a controlled scope before using it for production operations.
5. After saving, return to the list and check the event name, type, action, and status. You can use the page’s “Test” action to verify the configuration.

## Recovery boundary

Confirm that the event name is unique, all required fields are complete, and the receiving endpoint for the selected action is available. Ask the receiving-endpoint owner to check timeout settings and visible errors. Do not place unnecessary sensitive information in notification content.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

After a successful save, the new rule appears in the list. When the rule is enabled and a subsequent event type matches, the system attempts to perform the selected action. A successful save or test does not guarantee that the receiving endpoint completed processing.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the entry is restricted, you cannot create a rule, you cannot determine a secure receiving endpoint, or testing repeatedly fails, contact an administrator. Provide the product version, event name, event type, action type, test time, and a redacted message.

