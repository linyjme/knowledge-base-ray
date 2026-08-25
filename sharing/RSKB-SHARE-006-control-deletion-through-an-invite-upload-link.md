---
id: RSKB-SHARE-006
title: Control deletion through an invite-upload link
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
- What can an invite recipient delete when Allow deletion is enabled?
- Why is deletion through an upload invitation considered destructive?
- Does deleting invited files also remove the invitation link itself?
keywords:
- Add deletion permission to invitation upload
- allow deletion
- invite upload
- destructive permission
- What does Allow deletion mean on an invite-upload link?
- Added deletion permission for invitation upload
- sharing
- Raysync
legacy_ids:
- FAQ-LINK-013
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-102 | Add deletion permission to invitation upload
  evidence_type: feature-matrix
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-013 | What does Allow deletion mean on an invite-upload link?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-106 | Added deletion permission for invitation upload
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Control deletion through an invite-upload link

## Short answer

**Allow deletion** lets people using the invite-upload link delete files in the invitation directory. Without it, recipients can upload but do not receive this deletion permission from the link.

The invitation view may display all files and folders in the selected directory, which makes careful destination selection important.

## Destructive permission boundary

Allow deletion is a destructive permission that lets an invite recipient delete existing or newly uploaded content in the invited directory. It does not delete the invitation link itself.

Before enabling it, confirm that you have permission to create an invitation and the separate deletion permission. Confirm the exact destination, inspect the content already there, confirm the intended recipient is a trusted recipient, and confirm that **Allow deletion** is required for that directory and workflow.

## Recovery boundary

The documentation does not define an undo or recycle mechanism for recipient deletion. Restoring removed content depends on a separately available backup or recycle mechanism; if neither is available, do not assume the content is recoverable.

## Verify the permission safely

After enabling it, use a disposable non-production test item in the invited directory to verify that the intended recipient receives the documented deletion capability. Do not test with existing production content or infer access beyond the invited directory.

## Version differences

Allowing external users to delete files through an invite-upload link was added in v6.7.8.2.

## Important notes

**Destructive permission:** enabling deletion can remove existing or newly uploaded content from the invited directory. Grant it only to trusted recipients and only for a directory where such deletion is acceptable. This setting belongs to invite-upload links; it is unrelated to the share-download option that allows or blocks downloads.

## Related documented boundaries

- **Add deletion permission to invitation upload:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
