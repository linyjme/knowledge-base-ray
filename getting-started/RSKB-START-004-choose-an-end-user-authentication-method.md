---
id: RSKB-START-004
title: Choose an end-user authentication method
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
- Which authentication option should an end user choose on the login page?
- Can I sign in through OIDC or another organization SSO provider?
- Why does my deployment show a different login method than local accounts?
keywords:
- OIDC
- OpenID Connect
- SSO
- Okta
- OneLogin
- Google
- Microsoft Entra ID
- How do I sign in with OpenID Connect?
legacy_ids:
- FAQ-START-007
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-009 | How do I sign in with OpenID Connect?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-008 | How do I sign in with LDAP or Active Directory?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-010 | How do I use email authentication or sign in with an external HTTP account?
  evidence_type: generated-faq
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-007 | Which authentication methods can an end user use?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Choose an end-user authentication method

## Short answer

Depending on administrator configuration, an end user may sign in with a local Raysync account or through LDAP/OpenLDAP, Windows Active Directory, OpenID Connect, email-based authentication, an external HTTP authentication service, or Unix/Linux system authentication. Only methods enabled for the deployment and account are available.

## Version differences

Version 8.1.8.0 adds multiple authentication methods to the browser plug-in. Version 8.1.8.3 adds support for an administrator-selected default authentication method, so the login choice shown first can vary by deployment.

## Important notes

Authentication method does not by itself determine file permissions. For external HTTP accounts, permissions may remain in the external service or be synchronized into and controlled by Raysync, depending on the integration mode. Unix system authentication requires the Raysync service to have been started with root or sudo authority; this is an administrator prerequisite.

## Related documented boundaries

- **How do I sign in with OpenID Connect?:** Use the OpenID Connect sign-in option on the Raysync user portal, then authenticate on your organization's identity-provider page. After successful identity-provider authentication, the configured OIDC callback returns you to the Raysync user portal.
- **How do I sign in with LDAP or Active Directory?:** Open the Raysync user portal and use the LDAP/AD login method made available by your administrator. For a Windows Active Directory domain account, enter the user's `SamAccountName` as the username and use the domain password. OpenLDAP users use the credentials defined by the configured directory integration.
- **How do I use email authentication or sign in with an external HTTP account?:** For email authentication, use the email-related login method shown by your organization; the available sources do not document a separate end-user sequence or credential format. For external HTTP, use the external service credentials on the Raysync login page only when your administrator confirms that the integration is configured for Raysync-controlled permissions.
