---
id: RSKB-CLIENT-003
title: Sign in from the Raysync desktop client
product: raysync
components:
- desktop-client
domain: client
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- What server address should I enter when the desktop client asks me to sign in?
- Why does the Raysync client reject credentials that work in the portal?
- Can a local account connect directly through the desktop client?
keywords:
- server address
- account password
- login connection
- local authentication
legacy_ids:
- FAQ-CLIENT-008
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-008 | How do I sign in from the Raysync desktop client?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Sign in from the Raysync desktop client

## Short answer

Start the desktop client, enter the Raysync server address, choose **Next** if shown, then enter your account and password and select **Log In**. The documented default address format is `http://[server-IP]:8090`.

## Steps

1. Open the installed desktop client.
2. Enter the server address supplied by your administrator.
3. Select **Next**.
4. Enter your account and password.
5. Select **Log In** to connect and begin high-speed transfers.

## Version differences

Version 8.1.8.0 added multiple authentication methods to the browser plug-in. That release note does not establish third-party authentication support for the desktop client. The desktop-client sources document only the server-address plus account-and-password flow.

## Important notes

The server address may differ from the default example. Use the account and password supplied for desktop-client access. If your organization requires a third-party method, ask the administrator whether it applies only to the browser plug-in or whether a supported desktop-client procedure is available; the supplied desktop sources do not specify one.
