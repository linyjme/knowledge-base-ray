---
id: RSKB-SHARE-005
title: Set share-download limits and first-device binding
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
- How many downloads can a share-link creator allow?
- Why is a protected download link bound to the first recipient device?
- Can I disable downloading while leaving a share link record available?
keywords:
- Support download links to bind the first device
- download times
- disable download
- organization scope
- How do share-download limits work?
- How to set a share link password, validity period, and usage limits
- first device
- device binding
legacy_ids:
- FAQ-LINK-010
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-097 | Support download links to bind the first device
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-010 | How do share-download limits work?
  evidence_type: generated-faq
- file: knowledge-base/share-links/KB-SHARE-003-how-to-set-password-expiration-and-limits.md
  section: How to set a share link password, validity period, and usage limits
  evidence_type: product-documentation
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-012 | What does binding a share link to the first device do?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-100 | Sharing supports limited download times
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-104 | Share download supports limiting the number of downloads
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Set share-download limits and first-device binding

## Short answer

The creator can turn downloads off or set a number of download times. For **Anyone with the link**, the documented count is shared across all visitors to the link. For **Only people in your organization**, the limit applies individually to each visiting user.

The limit is part of the share-download link settings that the link creator chooses. Recipients cannot increase or reset it.

## Before changing the link

The link creator must have permission to manage the exact share-download link. An administrator must have enabled first-device binding before the creator can use that option. Before saving, confirm the exact target link and access scope: **Anyone with the link** or **Only people in your organization**.

## Exact effects and scope

- Turning **Allow users to download** off prevents download even when the link itself opens.
- For **Anyone with the link**, one limit is shared by the whole link across all visitors.
- For **Only people in your organization**, the limit is counted per visiting user.
- First-device binding locks the link to the first device that opens it. A later device receives the documented already-bound result.

## Device-binding boundary

First-device binding makes the link locked to the first device that opens it. A message that the link is already bound is different from an expired, disabled, or canceled link.

## Version differences

Download-time limits on share links were added in v6.7.8.2. Version 8.1.8.0 added filtering for share/invite links in the user portal.

## Important notes

Download limits belong to share-download links; invite-upload links instead control upload and optional deletion.

## Recovery and administration boundary

Recipients and ordinary users cannot increase or reset the configured limit. The documentation does not provide a reset for the downloaded count. If a download permission or limit is fixed or restricted by policy, an administrator can review that policy or saving restriction, but this does not promise a count reset. If access must move from the first device, an authorized administrator can unbind the link; unbinding changes the device binding, not the configured download limit.

## Verify the saved settings

After saving, open **Share Link details** for the same link and review its access scope, download permission, downloaded count, and total count. If downloading is still possible when it should be blocked or exhausted, confirm that the download setting was saved before asking an administrator to review a policy restriction.

## Related documented boundaries

- **Support download links to bind the first device:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **What does binding a share link to the first device do?:** When first-device binding is enabled, a share-download link can be opened only on the first device that accesses it. A second device receives a message that the link is already bound.
- **Sharing supports limited download times:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
