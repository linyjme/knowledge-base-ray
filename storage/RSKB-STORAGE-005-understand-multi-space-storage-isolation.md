---
id: RSKB-STORAGE-005
title: Understand multi-space storage isolation
product: raysync
components:
- user-portal
- file-service
domain: storage
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
- How does Raysync keep storage separate between multiple spaces?
- Why can the same user see different files after switching spaces?
- Which space receives files when a default space is configured?
keywords:
- multiple spaces
- default space
- membership
- storage
- Can one Raysync deployment have multiple spaces?
- space isolation
- access restriction
- separate storage
legacy_ids:
- FAQ-STORAGE-012
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-012 | Can one Raysync deployment have multiple spaces?
  evidence_type: generated-faq
- file: raysync-user-faq/10-storage-and-group-folders.md
  section: FAQ-STORAGE-013 | Are files and permissions isolated between Raysync spaces?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand multi-space storage isolation

## Short answer

Yes. Multiple spaces were added in version 6.2.8.0. A deployment has a default space, and administrators can create additional spaces, assign members and administrators, configure storage, create group folders, and apply space access restrictions. A newly created user is a member of the default space according to the legacy spaces guide.

## Version differences

Legacy documentation groups space storage, members, group folders, and access restrictions under **Spaces**. In the 8.1.8.0 and later documentation, storage and group management appear in separate **Configuration** and **File** areas, while the quick-start storage guide still states that multiple spaces can use different storage.

## Important notes

Seeing one space does not establish membership in every other space; membership can differ by account. If a required work area is missing, provide its name to an administrator so your membership can be checked.

Additional spaces can be configured with storage different from the deployment’s default space.

## Related documented boundaries

- **Are files and permissions isolated between Raysync spaces?:** Spaces are separately administered work areas: administrators assign members, storage, group folders, access restrictions, and file-delivery settings per space. As an end user, you see and operate within the spaces, personal directories, and group libraries made available to your account; membership or permission in one space does not document permission in another.
