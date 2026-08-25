---
id: RSKB-SHARE-020
title: Open an invite-upload link
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
- How does a recipient upload files through an invitation link?
- Can an invite visitor create a new folder in the upload location?
- Why might an upload recipient be unable to delete existing files?
keywords:
- open invite link
- upload
- new folder
- How does a recipient open an invite-upload link?
- sharing
- Raysync
legacy_ids:
- FAQ-LINK-004
safety_tags:
- credentials
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-004 | How does a recipient open an invite-upload link?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Open an invite-upload link

## Short answer

Open the invitation, complete its access checks, and upload into the displayed destination directory.

## Role and historical boundaries

This is the recipient workflow; the creator defines the invite destination and controls. Invite-link new-folder creation is recorded at 6.2.8.0 and again at 6.3.8.0. The two milestones do not prove a single introduction point.

## Prerequisites

- Obtain the invite-upload link and its password, if one is required.
- Have the required organization account or specified email login when the invitation is restricted.

## Steps

1. Open the invite-upload link in a browser.
2. Enter the password if prompted and select **Log in**.
3. Complete any organization or specified-email authentication.
4. Select **Upload** and choose the files to add.
5. If **New Folder** is available, create a folder first and upload into it as needed.

## Version differences

Invite-upload links are recorded as gaining new-folder creation in v6.2.8.0 and again in v6.3.8.0. From 8.1.8.4, the desktop client can detect a copied Raysync link and initiate the corresponding upload. Browser access is documented generally.

## Important notes

Deletion is available to recipients only if the creator enabled **Allow deletion**. Visibility of existing content does not by itself grant deletion permission.
