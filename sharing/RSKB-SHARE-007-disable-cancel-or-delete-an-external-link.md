---
id: RSKB-SHARE-007
title: Disable, cancel, or delete an external link
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
- What is the difference between disabling and deleting an external link?
- How can a creator stop access without removing the link record?
- Why does a canceled link remain visible in link management?
keywords:
- cancel link
- delete link
- link record
- What is the difference between canceling and deleting a link?
- disable link
- enable link
- inactive link
- Can I disable a link and enable it again later?
legacy_ids:
- FAQ-LINK-014
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-015 | What is the difference between canceling and deleting a link?
  evidence_type: generated-faq
- file: raysync-user-faq/07-share-and-invite-links.md
  section: FAQ-LINK-014 | Can I disable a link and enable it again later?
  evidence_type: generated-faq
- file: knowledge-base/share-links/KB-SHARE-004-how-to-cancel-delete-or-unbind-link.md
  section: How to disable, delete, or unbind a share link
  evidence_type: product-documentation
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-109 | Enabling and disabling external links
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Disable, cancel, or delete an external link

## Short answer

Regular users can usually disable or re-enable their own links. End users can also cancel their own share-download link or invite-upload link. Delete and Unbind depend on the displayed action, the user's role, and administrator permission.

Find the exact record by its creation time and status in **Download Share** or **Upload Invitation**. Do not rely on a similar link name alone.

## Exact effects

- A **Disable** action makes the link inaccessible while its record remains. **Enable** restores access only if its other validity and access conditions still pass.
- **Cancel** makes the link invalid while its record remains. In the current documented lifecycle, **Enable** can restore that retained record if its other conditions remain valid.
- **Delete** permanently removes the record.
- **Unbind** clears only the device binding; it does not delete the link or change its content. It applies only to a download link for which binding is enabled and already established.

## Confirm the exact record

Before Disable, Cancel, Delete, or Unbind, confirm the exact target link or record, including its link type, creation time, and current status. In the confirmation dialog or confirmation box, verify that the displayed record is the intended one. Use **Delete** only when the action is available to the authorized role and the prompt confirms that deletion cannot be undone.

## Version differences

Enable/disable shared-link functionality is listed in the 8.1.8.3 release. Earlier guides document canceling links but do not explicitly document re-enabling them.

## Important notes

Disable is reversible: Enable can restore the retained record when its other validity conditions pass. Cancel is also reversible through Enable in the current documented lifecycle. Delete cannot be undone or recovered through Enable. Unbind changes only the binding relationship and is not a substitute for disabling or deleting the link.

## Verify the resulting state

Refresh the management list and check the same record's status and validity after each action:

- After **Disable**, confirm status **Disabled** and that the link is inaccessible.
- After **Cancel**, confirm that the link is inaccessible while its record remains.
- After **Enable**, confirm status **In Use** and that the link is accessible only if its other conditions are valid.
- After **Delete**, confirm that the record disappears from the correct list.
- After **Unbind**, confirm that the device binding is cleared, then check that the link's status and validity are otherwise unchanged.

If the wrong record changed, a restriction remains, or a required Delete or Unbind action is unavailable, stop and ask an administrator to check the link type, creation time, status, and binding state.

## Related documented boundaries

- **What is the difference between canceling and deleting a link?:** Deleting the link record requires an authorized administrator and is not an end-user procedure.
- **Enabling and disabling external links:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported The source records 8.1.8.3 as an appearance or change milestone, not as proof of the onset of support.
