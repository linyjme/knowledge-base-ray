---
id: RSKB-SECURITY-008
title: Understand externally managed permissions
product: raysync
components:
- user-portal
domain: security
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
- Why can an external authentication service control my file permissions?
- Which permissions come from LDAP, OIDC, or HTTP authentication?
- Who can change access when Raysync does not own the external policy?
keywords:
- external authentication
- LDAP
- OIDC
- HTTP
- permissions
- roles
- Who controls my Raysync permissions when I use external authentication?
- security
legacy_ids:
- FAQ-SECURITY-016
safety_tags:
- credentials
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-016 | Who controls my Raysync permissions when I use external authentication?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand externally managed permissions

## Short answer

It depends on the authentication mode. With external HTTP authentication, permissions can be controlled either by the external HTTP service or by Raysync. When Raysync controls them, the external user is created in Raysync and Raysync permissions apply. When the external service controls them, Raysync’s default permission settings do not take effect.

For LDAP/AD, email, OIDC, external HTTP with Raysync-controlled permissions, and system authentication, administrators can assign default permissions or roles to newly logged-in accounts. Accounts that have already logged in must be changed in the account list. LDAP/AD users log in with the account form required by the configured directory; the documentation specifically says AD users use `SamAccountName` at the user portal.

## Version differences

Before 8.1.8.0, the feature is described as **Default Permission**. In later documentation it is **Permission Setting**, using default user and group roles. The 8.1.8.0 and later LDAP/AD guide also documents selecting a default authentication method and group filtering.

## Important notes

Authentication proves identity; it does not guarantee access to every Raysync file or feature. If login succeeds but an action is unavailable, ask the administrator which system owns your permissions and whether your already-created account or group role needs adjustment.
