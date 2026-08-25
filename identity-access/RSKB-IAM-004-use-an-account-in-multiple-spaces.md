---
id: RSKB-IAM-004
title: Use an account in multiple spaces
product: raysync
components:
- user-portal
domain: identity-access
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
- Can the same Raysync account belong to more than one space?
- How do I know which space is currently selected for my files?
- Why can my permissions differ between two spaces?
keywords:
- multiple spaces
- space member
- default space
- Can my account belong to more than one space?
- space permissions
- allowed path
- speed limit
- sync permission
legacy_ids:
- FAQ-ACCOUNT-008
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-008 | Can my account belong to more than one space?
  evidence_type: generated-faq
- file: raysync-user-faq/08-user-account-and-profile.md
  section: FAQ-ACCOUNT-009 | Why can I have different permissions in different spaces?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use an account in multiple spaces

## Short answer

Space membership is assigned by administrators. A new user is a member of the default space, and space administrators can add or remove members in other spaces. The cited sources do not document a self-service **Join space** action, so request membership from the relevant administrator.

When your account is added to another space, that space can have its own storage, home or virtual directories, access restrictions, permissions, speed limits, and group folders.

## Version differences

Multiple-space support was added in version 6.2.8.0. The end-user consequence is membership-based access to each assigned space.

## Important notes

Being able to log in does not automatically grant access to every space. Access comes from membership and the settings assigned within that space.

## Related documented boundaries

- **Why can I have different permissions in different spaces?:** Permissions and transfer configuration can be assigned per space membership. A space administrator can configure your home and virtual directories, forbidden and allowed paths, file-operation permissions, upload rules, speed limits, transfer formats and filters, notifications, and storage limit for that space.
