---
id: RSKB-START-007
title: Understand user-interface security and link changes by release
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
- Why do older instructions use different portal or administrator labels?
- Which release milestones changed link controls and login security?
- What is known about the disputed history of client-free web task controls?
keywords:
- 8.1.8.1
- pause transfer
- cancel transfer
- Turkish
- What changed for end users in Raysync 8.1.8.1?
- legacy instructions
- 8.1.8.0
- renamed areas
legacy_ids:
- FAQ-VERSION-002
safety_tags:
- credentials
- certificate
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-003 | What changed for end users in Raysync 8.1.8.1?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-002 | Why do administrator-provided Raysync instructions use different labels after version 8.1.8.0?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-008 | Which Raysync version added a Japanese interface?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-010 | Why did my Raysync login or certificate behavior change after an upgrade?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-006 | Will Raysync 8.1.8.6 change my login verification or transfer priority?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-004 | Why is an 8.1.8.3 link or P2P log control missing in 8.1.8.2?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-005 | What changed with malicious-IP protection in Raysync 8.1.8.4?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-009 | Which Raysync version supports the collaboration-link control I need?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-027 | Support file transfer with http web (support drag file and pause, cancel a task)
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand user-interface security and link changes by release

## Short answer

Version 8.1.8.0, released on 2025-03-05, reorganized administrator navigation. As an end user, you may therefore receive prerequisite instructions, support questions, or policy explanations that use either legacy labels or the newer guide-family labels. A mismatch between the words in an older article and the administrator’s current screen does not by itself mean the requested user action is unavailable.

Follow the user-facing action your administrator gives you?for example, retry login, collect a task error, or confirm a group library?while the administrator translates the server-side prerequisite for the installed version. You do not need admin-portal access to perform that translation.

## Unresolved web-task history

The historical claim for pausing or canceling a web transfer without the client is unresolved: the release FAQ records 8.1.8.1, while the feature matrix records 6.3.8.0. The evidence is insufficient, and no version is selected as the introduction point.

## Version differences

The legacy guide family is explicitly labeled for versions before 8.1.8.0, while the matching later guide family applies from 8.1.8.0. The release entry says administrator navigation was optimized; it does not claim that every user portal label changed at the same boundary. Confirm the server version before deciding which prerequisite wording applies.

## Important notes

Do not request elevated access merely because a help article names an administrator area. Give the administrator the article title, feature name, server version if known, and your user-visible symptom. The administrator can locate the corresponding current control. Keep user portal and admin portal roles distinct.

## Related documented boundaries

- **What is documented for web-task controls around Raysync 8.1.8.1?:** The release FAQ associates pause or cancel controls for client-free web transfer tasks with 8.1.8.1, while the feature matrix associates the same capability with 6.3.8.0. These are competing historical claims, so the introduction point is unresolved and no introduction version is selected. The 8.1.8.1 release entry also records Turkish localization as an optional interface language.
- **Which Raysync version added a Japanese interface?:** Raysync 8.1.8.7, released on 2026-07-07, added Japanese interface support for both the desktop client and user portal. In the user portal, language can be switched from the upper-right area of the login page; in the desktop client, language can be switched in Settings.
- **Why did my Raysync login or certificate behavior change after an upgrade?:** First identify the changed experience. Administrator two-factor authentication is documented from 8.1.8.3. Malicious-IP login restrictions begin at 8.1.8.4. User two-factor authentication, including the documented Authenticator App option where supported and enabled, begins at 8.1.8.6. Do not describe 8.1.8.6 as introducing administrator two-factor authentication anew.
- **Will Raysync 8.1.8.6 change my login verification or transfer priority?:** Raysync 8.1.8.6, released on 2026-03-19, is the documented boundary for user two-factor authentication and user transfer priority. Where the deployment supports and enables it, a user can be asked for email verification or an Authenticator App code. Administrator two-factor authentication was already introduced in 8.1.8.3; 8.1.8.6 does not introduce that administrator capability for the first time.
- **Why is an 8.1.8.3 link or P2P log control missing in 8.1.8.2?:** The control may belong to 8.1.8.3 rather than 8.1.8.2. Use 8.1.8.3 when you need the documented direct/relay connection type in a peer-to-peer transfer log or the ability to enable and disable a share-download link. Version 8.1.8.2 does not claim those controls; its relevant changes are log-list classification, virtual-path interaction, and the Linux desktop client.
- **What changed with malicious-IP protection in Raysync 8.1.8.4?:** Raysync 8.1.8.4 was released on 2025-06-30 and introduced a malicious-IP login restriction policy. It also added an email alert to administrators for malicious-IP blacklist events.
- **Which release records each collaboration-link change?:** The release history records **Allow deletion** for an external invite-upload user at 6.7.8.2; anyone-with-link email verification and a private-recipient option at 6.8.8.2; user-portal link filters at 8.1.8.0; enable or disable control for an existing share-download link at 8.1.8.3; and link upload or download in the desktop client at 8.1.8.4. These are milestone and change records, not universal minimum-support guarantees. Specified-email access at 6.8.8.2 and recipient-email protection at 8.1.8.3 are competing descriptions whose scope is unresolved, so no version is selected as the first or minimum support boundary for that protection.
