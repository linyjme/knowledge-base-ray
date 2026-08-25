---
id: RSKB-SHARE-018
title: 'Share administration: which permissions and policies restrict share links'
product: raysync
components:
- admin-portal
- user-portal
domain: sharing
access_level: public
audience:
- administrator
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why don’t I have a Download Share button?
- Who can create an upload invitation link?
- Why can’t files be shared in a group?
keywords:
- sharing permission
- invitation permission
- space role
- feature switch
- security policy
- which permissions
- and policies
- restrict share
legacy_ids:
- KB-SHARE-010
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/share-links/KB-SHARE-010-share-permission-and-policy-restrictions.md
  section: Which permissions and policies restrict share links
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Share administration: which permissions and policies restrict share links

## Short answer

Share links are jointly controlled by user operation permissions, personal-space or group roles, Download Share/Upload Invitation feature switches, and administrator security policies. If any required condition is missing, an entry may be hidden, options may be unavailable, or visitors may still be unable to upload or download after verification.

## Scope and evidence

This applies in version 8.1.8.7 when users, group members, or administrators cannot create, manage, or access a share link and the link content and network show no obvious problem.

Changing whether a link can be used does not delete or remove the shared files or uploaded content. Link access and content deletion are separate controls and require separate authorization.

## Documented details

1. To create a download link, confirm that the current space or group grants “Share” permission. To create an upload invitation, confirm that it grants “Invite” permission. Roles may differ between groups.
2. Confirm that you have the required read, write, or upload permission for the selected content or destination. Whether invited visitors can delete content also depends on “Allow Delete” at creation time and the creator’s own deletion permission.
3. If “Share Links,” “Download Share,” or “Upload Invitation” is unavailable, ask the administrator to check user-portal menus and related global feature switches and use the currently visible supported entry.
4. Ask the administrator to verify security settings such as maximum link validity period, external-person email verification, and first-device binding. These change selectable validity periods or the access process.
5. For Internal Members or Specified Email Addresses, check accounts, email addresses, and member lists. For download links, also check “Preview Only/Preview and Download” and count limits.

## Interpretation and recovery boundary

Compare the behavior in the personal space and target group, and record whether a button is missing, which setting is unavailable, and the visitor’s message. Do not share a privileged account, broaden unrelated directory permissions, or disable necessary security controls to solve it.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

After role, directory permission, feature switches, and security policies are satisfied, users see and use only authorized link capabilities. Restricted options remain hidden or unavailable as an expected permission-control result.

## Escalation

An administrator must evaluate changes to roles, global switches, email verification, device binding, maximum validity period, or other organizational security policies. Provide the product version, account type, space/group name, expected operation, and visible message. Administrators should follow the least-privilege principle.

