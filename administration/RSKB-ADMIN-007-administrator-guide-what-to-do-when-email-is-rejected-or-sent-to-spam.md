---
id: RSKB-ADMIN-007
title: 'Administrator guide: what to do when email is rejected or sent to spam'
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
- What should I do when email is rejected or sent to spam?
- Why are system emails always treated as spam?
- How do I handle a bounce from the receiving email server?
keywords:
- email rejection
- spam
- allowlist
- approved sender list
- domain policy
- rate limit
- bounce
- email administrator
legacy_ids:
- KB-EMAIL-007
safety_tags:
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-007-email-rejected-or-marked-as-spam.md
  section: What to do when email is rejected or sent to spam
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what to do when email is rejected or sent to spam

## Short answer

First look for the message in the spam folder or quarantine area and add the trusted sender to the allowlist. Then ask the email administrator to check the sender address, sender-domain policy, and sending rate limits. Being placed in spam and being rejected by the server are different outcomes; handle each according to its bounce or quarantine message.

## Prerequisites

This applies in version 8.1.8.7 when the page reports a successful test or send operation but the message is placed in spam or quarantine, or when the sender receives an error such as rejection, unauthorized sender, or rate-limit exceeded.



## Effect

An allowlist change affects how the receiving mail system treats future messages from the approved sender or domain. Each diagnostic test sends a real email; neither action should broaden trust beyond the confirmed sender.

## Confirmation

Confirm the exact rejected message, approved sender identity, receiving policy owner, narrow allowlist target, and approved test recipients before making a change.

## Procedure

1. Check the recipient mailbox’s spam folder, quarantine area, and automatic categories, and search by the expected sender and send time.
2. After confirming that the email was sent by an organization-approved system, add the sender address or sender domain to the receiving system’s allowlist. Do not create an overly broad allowlist rule.
3. Verify that “SMTP Email” and the sender information represent an identity approved by the organization and comply with the provider’s delegation and domain policies.
4. If a bounce exists, read the visible reason, such as unauthorized sender, nonexistent recipient, policy rejection, or excessive sending frequency.
5. If a large volume was sent in a short period, stop repeated testing, wait for the rate-limit window to end, and ask the email administrator to confirm the permitted sending rate.
6. Send one test to an approved internal address and one to an approved external address to determine whether the issue is caused by an individual recipient rule or the entire sender domain.

## Recovery boundary

Do not try to solve the issue by repeatedly resending, spoofing the sender address, or disabling necessary security checks. Retain the bounce summary, quarantine reason, and test time, and compare whether the issue affects only a specific recipient domain or all recipients.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

After the sender identity and domain policy are valid, the sending rate is compliant, and the recipient permits the source, email can reach the inbox without being immediately rejected or quarantined.

## Escalation

Contact the email administrator for domain-level allowlists, sender-domain policies, email reputation, quarantine release, or rate limits. Provide the sender domain, recipient domain, send time, and a non-sensitive summary of the bounce or quarantine error. Do not provide passwords or sensitive email content.
