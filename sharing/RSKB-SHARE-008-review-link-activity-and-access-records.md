---
id: RSKB-SHARE-008
title: Review link activity and access records
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
- Where can a creator review downloads or uploads made through a link?
- Which access records show recipient addresses or network information?
- How do I filter collaboration-link activity before investigating an event?
keywords:
- View records such as the number of shared downloads and IPs
- activity records
- download notifications
- upload notifications
- link filtering
- What link activity and records can I review as an end user?
- How to view share records and access information
- sharing
legacy_ids:
- FAQ-LINK-016
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-098 | View records such as the number of shared downloads and IPs
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-016 | What link activity and records can I review as an end user?
  evidence_type: generated-faq
- file: knowledge-base/share-links/KB-SHARE-009-how-to-view-share-records.md
  section: How to view share records and access information
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Review link activity and access records

## Short answer

Open **Share Links** and use **Download Share** or **Upload Invitation** to find current or historical records. Filter by time range and link status, then open **Details** for the target record. Link creators see their own records; administrators may see records within their assigned permission scope.

## Details and activity fields

The list and **Details** can show shared content or invitation directories, location, creation time, expiration time, access scope, status, notifications, and other fields authorized for the current account. Depending on role and configuration, details can also include the link, creator, download permission and count, invitation deletion permission, or device-binding status.

For a download share, select the downloaded count or **View Download Count**, when available, to review the accounts, access sources, downloaded files or directories, and times permitted by current permissions.

## Version differences

User portal filtering for share and invite link lists was added in version 8.1.8.0. The current link guides also document optional notifications when a download or upload starts and completes.

## Important notes

The sources do not document a full per-action audit trail for ordinary users. The list and details expose only data authorized for the current account. Other creators, access sources, device information, and account activity can be outside an end user's visibility scope.

Access records can contain personal data. Handle account names, access sources, file names, and times under organizational policy; do not copy them into unrestricted tickets or messages. If information beyond your scope is required, ask an administrator to check role and data-visibility permissions.

## Related documented boundaries

- **View records such as the number of shared downloads and IPs:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
