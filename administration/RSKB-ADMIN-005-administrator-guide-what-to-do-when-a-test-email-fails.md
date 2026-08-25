---
id: RSKB-ADMIN-005
title: 'Administrator guide: what to do when a test email fails'
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
- What should I do when a test email fails?
- How do I troubleshoot repeated SMTP test errors?
- Why can’t I save the email configuration or send a test email?
keywords:
- test email failure
- SMTP connection failure
- authentication failure
- incorrect account or password
- port and encryption mismatch
- DNS
- network policy
- visible error
legacy_ids:
- KB-EMAIL-005
safety_tags:
- authorization
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/email-configuration/KB-EMAIL-005-test-email-failed.md
  section: What to do when a test email fails
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: what to do when a test email fails

## Short answer

Troubleshoot the SMTP address, port, encryption method, account credentials, sender policy, DNS, and network in that order, and retain the error visible on the page. Change only one setting at a time and test again so that you can identify the stage that failed.

## Prerequisites

This applies to administrators who see a connection failure, authentication failure, sending failure, or another page error after clicking “Send Test Email” in version 8.1.8.7.



## Effect

A test sends one message through the configured SMTP path. Correcting SMTP values changes the global sender configuration used by later system email, so limit changes to the exact failed field and approved provider values.

## Confirmation

Confirm the intended SMTP server, port, encryption method, sender account, approved test recipient, and one test window before changing a value or sending the test.

## Procedure

1. Host: Verify the spelling of “SMTP Address” and the provider’s requirements. Do not enter the incoming-mail server address in the outgoing-mail server field.
2. Port: Confirm that “SMTP Port” is a sending port currently allowed by the provider and accessible from the organization’s network.
3. Encryption: Confirm that SSL/TLS, STARTTLS, or no encryption is paired with the appropriate port. Do not weaken security to work around an error.
4. Credentials: Verify “SMTP Email” and “SMTP Password.” A password is required for Login. If the provider requires an app-specific password or separate SMTP enablement, follow its administration process. For Open, confirm that the email server explicitly permits passwordless connections.
5. Sender policy: Confirm that the sender information belongs to the account or is authorized for delegated sending, and rule out an unauthorized alias or domain mismatch.
6. DNS and network: Confirm that the admin environment can resolve the SMTP address, and ask the network administrator to check firewall, proxy, and outbound policies.
7. Record the test time and the error displayed on the page, then send one more test email.

## Recovery boundary

Ask the email administrator whether the account is locked, SMTP sending is enabled, or connection or sending rate limits have been triggered. You can also use another organization-approved test recipient to distinguish a sending failure from recipient-side filtering.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

After the relevant setting is corrected, the page reports success, which means the email server accepted the send request. Then check the inbox, spam folder, quarantine area, or delivery records visible to the email administrator. The email may still not appear immediately because of recipient filtering, a bounce, or delivery delay. If the page still reports an error, continue troubleshooting based on the new visible error instead of repeatedly changing several settings.

## Escalation

Contact the appropriate administrator when network policies must be changed, an account must be unlocked, SMTP permission must be enabled, an app-specific password must be configured, or sender policies must be adjusted. Provide the product version, test time, SMTP host domain, port, encryption method, and complete error visible on the page. Always redact the password.
