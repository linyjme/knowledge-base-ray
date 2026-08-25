---
id: RSKB-SHARE-002
title: Create an invite-upload link
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
- How do I create a link that lets recipients upload into a folder?
- Which destination does an invite creator choose for incoming files?
- Why should I review deletion permission before publishing an upload invitation?
keywords:
- Create link to invite upload files
- How to create an upload invitation link
- invite-upload link
- upload directory
- Create Link
- How do I create an invite-upload link?
- sharing
- Raysync
legacy_ids:
- FAQ-LINK-002
safety_tags:
- credentials
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-089 | Create link to invite upload files
  evidence_type: feature-matrix
- file: knowledge-base/share-links/KB-SHARE-002-how-to-create-upload-invitation-link.md
  section: How to create an upload invitation link
  evidence_type: product-documentation
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-002 | How do I create an invite-upload link?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Create an invite-upload link

## Short answer

Create the invite-upload link from the directory that should receive the uploaded content.

## Historical boundary

The creator chooses the invite destination and access controls; the recipient can only use the resulting invitation under those controls. Invite-link new-folder creation is recorded in both 6.2.8.0 and 6.3.8.0. The duplicate milestones do not prove a single introduction point.

## Prerequisites

- You can access the destination folder and have permission to create an invitation.
- If Raysync will email the link, the assigned administrator or personal mail service must already be configured.
- Enable deletion only when you also have deletion permission and the intended recipient is trusted to remove content.

## Allow deletion safety boundary

**Allow deletion** permits the intended recipient to delete existing or newly uploaded content in the invited directory. It does not delete the invitation link itself. Before you create the link or enable this permission, confirm the exact destination, review the content already there, confirm the intended recipient, and confirm that **Allow deletion** is enabled only when that effect is required.

The documentation does not define an undo or recycle mechanism for recipient deletion. Restoring removed content depends on a separately available backup or recycle mechanism; if neither is available, do not assume the content is recoverable.

After enabling the permission, use a disposable non-production test item in the invited directory to verify that the intended recipient receives the documented deletion capability. Do not use existing production content for this check or treat it as proof of access outside the invited directory.

## Steps

1. Open the destination folder and choose **Invite to upload**.
2. Choose the invitation scope and configure any available recipient email restriction.
3. Set the password and expiration time. Leave **Allow deletion** off unless the reviewed workflow requires recipient deletion and the safety boundary above has been satisfied.
4. Configure email, scheduled delivery, and upload notifications if needed.
5. Select **Create Link**, then use **Copy Link and Password** or the configured email option.

## Version differences

Invite-upload creation of a new folder is recorded in both v6.2.8.0 and v6.3.8.0. Scheduled link notification and recipient deletion permission were added in v6.7.8.2. Specified-recipient email protection is recorded in v6.8.8.2 and again in 8.1.8.3; the sources do not prove a single introduction date. Version 8.1.8.0 added filtering of invite-link lists and admin-side link deletion.

## Important notes

The invite page may show all files and folders already in the invited directory. Choose the destination carefully and grant deletion only when the recipient is trusted.

## Related documented boundaries

- **Create link to invite upload files:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
