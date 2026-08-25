---
id: RSKB-SHARE-019
title: Open a share-download link
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
- How does a recipient open a protected share-download link?
- Where should I enter the password supplied by the share creator?
- Why can a recipient view a link but still be unable to download?
keywords:
- open share link
- password
- download
- How does a recipient open a share-download link?
- sharing
- Raysync
legacy_ids:
- FAQ-LINK-003
safety_tags:
- credentials
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-003 | How does a recipient open a share-download link?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Open a share-download link

## Short answer

Open the link, complete its access checks, and download from the shared file list.

## Role boundary

This is the recipient workflow. The creator, not the recipient, defines the shared content, expiration, password, email restriction, device binding, and download permissions.

## Prerequisites

- Obtain the share-download link and its password, if one is required.
- Have the required organization account or specified email login when the link is restricted.

## Steps

1. Open the share-download link in a browser.
2. Enter the password if prompted and select **Log in**.
3. Complete any organization or specified-email authentication.
4. In the shared file list, select the download control for the required files.

## Version differences

Desktop-client upload/download through Raysync links was added in 8.1.8.4. Browser access remains documented for earlier versions.

## Important notes

The creator may disable downloads, limit download counts, expire the link, bind it to the first device, or restrict it to specified recipients. A valid URL alone may therefore be insufficient.
