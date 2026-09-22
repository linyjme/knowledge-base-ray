---
id: RSKB-START-002
title: Access and sign in to the Raysync user portal
product: raysync
components:
- user-portal
domain: getting-started
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
- How do I reach the user portal and sign in with my assigned account?
- What should I enter when the Raysync login page asks for credentials?
- Why can an administrator-provided portal address matter for sign-in?
- Why does the user portal say Invalid user for an administrator account?
keywords:
- login
- username
- password
- local account
- user portal
- How do I sign in to Raysync?
- URL
- server address
legacy_ids:
- FAQ-START-002
safety_tags:
- credentials
- certificate
supersedes: []
superseded_by: []
related_articles:
- RSKB-ADMIN-056
source_refs:
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-003 | How do I sign in to Raysync?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-002 | How do I access the Raysync user portal?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-004 | What happens on my first login?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Access and sign in to the Raysync user portal

## Short answer

Open the user portal address supplied by your Raysync administrator in a browser. A deployment may use the documented default port or a customized HTTPS address; use only the exact address your organization provides.

## Steps

1. Obtain the Raysync server address from your administrator.
2. Enter the full address in your browser, including the port if one is required.
3. When the Raysync login page opens, use the authentication method assigned to your account.

## Version differences

The default port example is documented across the current user guides. The sources do not identify a different end-user portal navigation flow at the version 8.1.8.0 boundary. A deployment can nevertheless use an administrator-provided address instead of the default example.

## Important notes

Do not substitute the administrator portal address for the user portal address. The default user portal address is `http://[server-IP]:8090`. The default admin console address is `http://[server-IP]:9090/admin`. Port 9090 alone is not that console URL; the page path is `/admin`. An organization-provided hostname or HTTPS address takes precedence over these defaults. `Invalid user: (admin)` on port 8090 means that account name was submitted to the user portal, not to the admin console.

## Related documented boundaries

- **How do I sign in to Raysync?:** Open the Raysync user portal, enter the correct username and password, and select **Login**. If your organization has configured a different default authentication method, use the login option and credentials provided by your administrator.
- **What happens on my first login?:** If the administrator has required a password reset for your first login, Raysync opens the password-reset page after you submit the initial username and password. Set the new password there, then use the new password to complete login. If no first-login reset was configured, Raysync proceeds with the normal login flow.
