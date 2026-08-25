---
id: RSKB-START-005
title: Sign out of Raysync
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
- How do I sign out of the Raysync user portal safely?
- Where is the logout action when I need to switch accounts?
- Does exiting the desktop client also end my portal session?
keywords:
- log out
- sign out
- switch account
- exit client
- profile
- How do I sign out of Raysync?
- getting started
- Raysync
legacy_ids:
- FAQ-START-011
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/01-getting-started-and-login.md
  section: FAQ-START-011 | How do I sign out of Raysync?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Sign out of Raysync

## Short answer

In the user portal, select your username in the upper-right corner and choose **Log Out**. In the desktop client, open **Profile** and select **Switch Account** to log out of the current account and sign in with another one.

## Version differences

The sources do not document a version-specific change to the user portal logout flow. The current desktop-client guide distinguishes switching accounts from exiting the program.

## Important notes

Logging out is not the same as shutting down the desktop client. **Switch Account** logs out the current account. **Exit Client** closes the Raysync client. The user portal **Log Out** action ends the web session, but a running client may remain active until you log out or exit there as appropriate.
