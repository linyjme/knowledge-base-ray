---
id: RSKB-SHARE-003
title: Protect a link with recipient passwords and expiration dates
product: raysync
components:
- user-portal
domain: sharing
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
- How can I require a password before recipients open a link?
- Can a creator restrict link access to specified recipient emails?
- When does an expiration setting prevent external link access?
keywords:
- link password
- expiration time
- recipient email restriction
- internal members
- external link access
legacy_ids:
- FAQ-LINK-005
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/share-links/KB-SHARE-003-how-to-set-password-expiration-and-limits.md
  section: How to set a share link password, validity period, and usage limits
  evidence_type: product-documentation
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-092 | Setting the expiration date of the external link password
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-005 | How do passwords and expiration dates protect a Raysync link?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-103 | Share or invite internal members
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-108 | Sharing and inviting support access with a specified email address
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-099 | Support for sharing or inviting internal members
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-007 | How do I find internal members when choosing link recipients?
  evidence_type: generated-faq
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-006 | Can I restrict a link to specific recipient email addresses?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Protect a link with recipient passwords and expiration dates

## Short answer

A password makes recipients verify the correct password before opening a share-download or invite-upload link. An expiration time limits how long the link remains valid. These controls can be combined with organization-only scope or specified-recipient email protection.

The documented creation flows generate an access password by default. The creator can copy the link and password and send them to the intended recipient.

## Configure the protection in order

Select the access scope first because it affects the available verification methods and which password options appear. For external access, retain or set a hard-to-guess password and deliver it separately from the link. For **Internal Members**, identity is verified by sign-in and some password options may not appear.

Enable **Link Expiration** and choose a date within the permitted range. An administrator can configure a maximum validity period for download or upload links, so dates beyond that limit may be unavailable. Add specified recipient emails only when that additional email-match restriction is intended.

## Historical boundary

Recipient-email protection is recorded at 6.8.8.2 and again at 8.1.8.3. These claims conflict and remain unresolved, so no introduction-version claim is selected.

## Version differences

Password and expiration controls are present throughout the cited link guides. Specified-recipient email protection is recorded in v6.8.8.2 and again in 8.1.8.3; the sources do not prove a single introduction date.

## Important notes

A password does not distinguish recipients if everyone receives the same credentials. For sensitive content, also restrict the scope or specify recipient emails. When possible, send the password separately from the link; the administrator controls whether share-link emails carry them together or separately.

## Verify saved settings and recover safely

After creation, review the access password, expiration time, scope, and other intended controls in the link details. If the password option disappears, confirm whether **Internal Members** is selected. If an expiration date is unavailable, choose a date within the permitted range rather than removing expiration.

If saving reports a policy restriction, ask an administrator to check the maximum validity period, access scope, and link-security settings. Do not weaken verification or make the link indefinite as a workaround.

## Related documented boundaries

- **Setting the expiration date of the external link password:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Support for sharing or inviting internal members:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **How do I find internal members when choosing link recipients?:** When selecting people within your organization, enter part of the user's account, email address, or name. Raysync's fuzzy search accepts partial or imprecise keywords and returns closely matching members for selection.
- **Can I restrict a link to specific recipient email addresses?:** Yes. Add the intended email address when creating the link. Only a user with the specified email address can satisfy that email-match restriction. If no specified email is configured, only the email-match restriction is removed; the selected scope, organization login, password, expiration, device binding, and download permissions or limits still apply when configured.
