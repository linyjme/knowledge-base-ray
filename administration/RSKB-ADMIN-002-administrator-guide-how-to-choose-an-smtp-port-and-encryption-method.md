---
id: RSKB-ADMIN-002
title: 'Administrator guide: how to choose an SMTP port and encryption method'
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
- How should I choose the SMTP port and encryption method?
- Which port should I enter in Email Settings?
- Should I select SSL/TLS or STARTTLS?
keywords:
- SMTP port
- encryption method
- SSL/TLS
- STARTTLS
- no encryption
- connection failure
- email service provider
- choose an
legacy_ids:
- KB-EMAIL-002
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-002-how-to-select-port-and-encryption.md
  section: How to choose an SMTP port and encryption method
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to choose an SMTP port and encryption method

## Short answer

The port and encryption method must be a matching combination specified by the email service provider. There is no universal port that works for every email service. Email Settings may offer SSL/TLS, STARTTLS, or no encryption, but the available options vary by email type and do not mean that the provider supports every combination.

## Prerequisites

This applies when configuring a new email account, responding to changed provider requirements, or troubleshooting an SMTP connection failure in version 8.1.8.7. Use the current parameters supplied by the email service provider or your organization’s email administrator.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **choose an SMTP port and encryption method** in the intended deployment, edition, and component.

## Effect

The port and encryption method must be a matching combination specified by the email service provider. There is no universal port that works for every email service. Email Settings may offer SSL/TLS, STARTTLS, or no encryption, but the available options vary by email type and do not mean that the provider supports every combination.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. In “Email Settings,” select the “Email Type” you actually use. Select “Other Email” for a provider that is not preset.
2. Obtain the SMTP address, port, and encryption method from the provider’s documentation or the email administrator, and confirm that all three belong to the same connection configuration.
3. Enter the port under “SMTP Port,” then select the corresponding SSL/TLS, STARTTLS, or provider-approved unencrypted method under “Encryption Method.”
4. Save the configuration and send a test email. If the provider changes its port or security requirements, update both settings together and test again.

## Recovery boundary

First rule out an incorrect port, then confirm that an SSL/TLS port has not been paired with STARTTLS. Even if the network policy allows only one port, do not use a mismatched encryption method; ask the network or email administrator to allow the connection required by the provider.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

When the settings match, the system can connect to the email server and proceed with authentication. After the test reports success, the destination mailbox can receive the test email.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If you cannot confirm the provider’s requirements, the port is blocked by network policy, or the organization prohibits an encryption method, contact the email or network administrator. Provide the email type, SMTP address, port, selected encryption method, and visible page error. Do not provide account credentials.

