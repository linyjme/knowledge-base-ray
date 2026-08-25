---
id: RSKB-ADMIN-003
title: 'Administrator guide: how to configure sender information correctly'
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
- How do I configure sender information correctly?
- What should I enter as the sender name?
- Must the SMTP email and sender address match?
keywords:
- sender
- sender name
- sender address
- SMTP email
- sender mismatch
- email rejection
- email alias
- configure sender
legacy_ids:
- RS-FEAT-141
- KB-EMAIL-003
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-141 | Set notification email sender
  evidence_type: feature-matrix
- file: knowledge-base/email-configuration/KB-EMAIL-003-how-to-configure-sender.md
  section: How to configure sender information correctly
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to configure sender information correctly

## Short answer

“SMTP Email” should contain the actual email account used to connect and authorized to send messages, while “Sender Name” identifies the sender to recipients. Some email providers validate sender information. An email may be rejected if the sender name is treated as the sender address, or if the sender address, SMTP account, and authorized alias do not comply with the provider’s policy.

## Prerequisites

This applies to administrators configuring a sender for the first time, changing the SMTP account, or seeing visible errors such as an unauthorized sender or address mismatch in version 8.1.8.7.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **configure sender information correctly** in the intended deployment, edition, and component.

## Effect

“SMTP Email” should contain the actual email account used to connect and authorized to send messages, while “Sender Name” identifies the sender to recipients. Some email providers validate sender information. An email may be rejected if the sender name is treated as the sender address, or if the sender address, SMTP account, and authorized alias do not comply with the provider’s policy.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. In “Email Settings,” enter the full email account that the provider permits to send through SMTP under “SMTP Email.”
2. Under “Sender Name,” enter a name that recipients can easily recognize. If the provider requires an email address in this field, enter the SMTP email or an authorized sender alias as instructed.
3. If you need to use a sender address different from the SMTP account, first ask the email administrator to confirm that the address is authorized as an alias or delegated sender identity.
4. After saving, send tests to one approved internal address and one approved external address, then check the sender displayed in each email.

## Feature-matrix evidence

- Knowledge base ID: RS-FEAT-141
- Original source text: Set notification email sender
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Source version note: No starting-version note in the source
- Source location: Raysync Feature list.xlsx / English-New / row 141

## Recovery boundary

Temporarily change the sender name to the format recommended by the provider and test again. Verify that the SMTP email is spelled correctly, the alias is enabled, and the sender domain permits the account to send on its behalf. Do not impersonate a sender with an unauthorized address.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

When the configuration complies with the provider’s policy, the test email is accepted, recipients see the expected sender name and address, and subsequent notifications are not rejected because of a sender identity mismatch.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the error mentions an unauthorized sender, prohibited delegation, or a domain policy rejection, contact the email administrator. Provide the test time, SMTP email domain, intended sender address, and a non-sensitive summary of the bounce message. Do not submit the password or sensitive information from complete email headers.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.
