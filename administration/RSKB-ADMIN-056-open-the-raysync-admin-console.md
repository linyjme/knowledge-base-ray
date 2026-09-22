---
id: RSKB-ADMIN-056
title: Open the Raysync admin console
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
- What is the Raysync admin console URL?
- Where do I sign in as an administrator instead of an end user?
- Why does the user portal report Invalid user for admin?
keywords:
- admin console
- admin portal
- 9090
- /admin
- Invalid user
- user portal
- 8090
legacy_ids: []
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles:
- RSKB-START-002
source_refs:
- file: user-faq/01-getting-started-and-login.md
  section: FAQ-START-002 | How do I access the Raysync user portal?
  evidence_type: product-confirmation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-09-22'
  verified_by: product-confirmation
---

# Open the Raysync admin console

## Short answer

Open the admin console at `http://[server-IP]:9090/admin`. Open the user portal at `http://[server-IP]:8090`. These are different sign-in pages. Use the server IP or the hostname supplied for that installation. Do not replace it with `localhost` unless the browser is running on the server itself.

## Address rules

- The admin console page path is `/admin`. `http://[server-IP]:9090` without `/admin` is not the admin console address.
- TCP 9090 in the firewall port list is the admin console port. It is not a complete browser address.
- TCP 8090 is the user portal port. Signing in there with an administrator account can return `Invalid user: (admin)` because that page accepts end-user accounts.
- The administrator account name is the one created during setup. Documentation examples that use `admin` are samples, not a guarantee that every installation uses that name.
- A hostname or HTTPS address provided for the installation takes precedence over the default HTTP examples. Do not turn a firewall port such as 9091 into a browser address unless that full address is documented for the installation.

## What to do when login says Invalid user

1. Confirm the browser address is `http://[server-IP]:9090/admin`, not `http://[server-IP]:8090` and not `http://[server-IP]:9090`.
2. Sign in with the administrator account from setup.
3. Use port 8090 only for end-user accounts created in the admin console.
