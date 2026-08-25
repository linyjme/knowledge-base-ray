---
id: RSKB-SHARE-004
title: Email and schedule link delivery
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
- Can Raysync email a share or invite link to recipients?
- How do I schedule delivery of a collaboration link for later?
- Why might link and password notifications use separate messages?
keywords:
- separate password email
- link email
- share notification
- Can the link and password be sent in separate emails?
- Sharing supports scheduled sending
- Share download support scheduled sending
- Send mail notification when download start or complete
- Sharing and invitation support notifications to private recipients
legacy_ids:
- FAQ-LINK-008
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-009 | Can the link and password be sent in separate emails?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-101 | Sharing supports scheduled sending
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-105 | Share download support scheduled sending
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-095 | Send mail notification when download start or complete
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-107 | Sharing and invitation support notifications to private recipients
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-011 | Can I schedule when Raysync emails a link?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-093 | Send share/invite link automatically via mail
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-096 | Link and password email are sent separately
  evidence_type: feature-matrix
- file: knowledge-base/share-links/KB-SHARE-008-how-to-send-share-email.md
  section: How to send a share link by email
  evidence_type: product-documentation
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-094 | Send mail notification when upload start or complete
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-008 | Can Raysync email the link to recipients for me?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Email and schedule link delivery

## Short answer

Yes. Enable **Email notifications to partners** while creating a share-download or invite-upload link. The UI also includes **Notify to recipients**, described as sending a separate identical message to a “private recipient” with an option to include the access password. The supplied documentation does not define “private recipient” or explain how that party is designated, so follow the fields shown in your deployed interface rather than assuming a recipient type.

By default, email uses the administrator-configured mail service. If the administrator assigns your personal mailbox as the sender, configure it in **Personal Center > Mail Settings** first.

## Version differences

The cited sources do not document a user-visible version difference in this email-notification option. Email delivery still requires an administrator-configured mail service or an assigned personal mailbox.

## Important notes

Mail delivery depends on valid server or personal mail settings. If email delivery is unavailable, the invitation guide documents **Copy Link and Password** for manual delivery. The sources do not specify what result the creation form displays when email configuration is missing.

## Related documented boundaries

- **Can the link and password be sent in separate emails?:** Yes, for share-download email notification. Raysync account configuration supports either sending the link and password in one email or sending them in different emails. This choice is set for the user by an administrator rather than by the recipient.
- **Sharing supports scheduled sending:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Send mail notification when download start or complete:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Sharing and invitation support notifications to private recipients:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported The source records 6.8.8.2 as an appearance or change milestone, not as proof of the onset of support.
- **Can I schedule when Raysync emails a link?:** Yes. Enable **Send regularly** during share-download or invite-upload link creation and set the desired time. Raysync sends the email notification at that time, telling recipients to open the link.
- **Send share/invite link automatically via mail:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Link and password email are sent separately:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Send mail notification when upload start or complete:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
