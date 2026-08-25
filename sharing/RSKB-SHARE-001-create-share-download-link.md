---
id: RSKB-SHARE-001
title: Create a share-download link
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
- How do I create a link that lets recipients download selected files?
- Which options can a share creator set before publishing a download link?
- Where can I add an alias for files exposed through a share?
keywords:
- Creat link to share download files
- How to create a download share link
- Setting file aliases when generating shared download links
- share-download link
- share files
- recipient download
- How do I create a share-download link?
- sharing
legacy_ids:
- FAQ-LINK-001
safety_tags:
- credentials
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-090 | Creat link to share download files
  evidence_type: feature-matrix
- file: knowledge-base/share-links/KB-SHARE-001-how-to-create-download-share-link.md
  section: How to create a download share link
  evidence_type: product-documentation
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-091 | Setting file aliases when generating shared download links
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-001 | How do I create a share-download link?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Create a share-download link

## Short answer

Create a share-download link from selected files or folders, then distribute the generated link to intended download recipients.

## Role boundary

The creator chooses content and access controls. A recipient can only open the resulting share-download link under those controls; recipient access is covered separately.

## Prerequisites

- You can access the files or folders and have permission to share them.
- If Raysync will email the link, the assigned administrator or personal mail service must already be configured.

## Steps

1. Select one or more files or folders and choose **Share to download**.
2. Choose the sharing scope and configure download permission and download times.
3. Configure any available recipient email restriction, password, expiration time, and file alias.
4. Configure email, scheduled delivery, and download notifications if needed.
5. Select **Create**, then copy or send the generated link and access password.

## Version differences

Download-time limits and scheduled link-sharing notifications were added in version 6.7.8.2. Specified-recipient email protection is recorded in version 6.8.8.2 and again in version 8.1.8.3; the sources do not establish version 8.1.8.3 as its sole introduction date. In version 8.1.8.0 and later, user portal link lists also support filtering.

## Important notes

Choose **Anyone with the link** only when broad access is acceptable. Use organization login, recipient email, password, and expiration controls for more restricted sharing.

## Related documented boundaries

- **Creat link to share download files:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Setting file aliases when generating shared download links:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
