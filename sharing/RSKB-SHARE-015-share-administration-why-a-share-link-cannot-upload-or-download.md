---
id: RSKB-SHARE-015
title: 'Share administration: why a share link cannot upload or download'
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
- Why is download unavailable through an otherwise valid external link?
- Which invitation permission prevents an external visitor from uploading?
- How can insufficient storage or browser networking block link transfers?
keywords:
- cannot upload
- cannot download
- preview only
- insufficient capacity
- browser network
- link restriction
- share link
- transfer unavailable
legacy_ids:
- KB-SHARE-007
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/share-links/KB-SHARE-007-share-upload-or-download-not-allowed.md
  section: Why a share link cannot upload or download
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Share administration: why a share link cannot upload or download

## Short answer

Common causes include a mismatched link type or permission, an expired or canceled link, “Preview Only” download permission, an exhausted download count, insufficient destination-space capacity or a policy restriction, and browser or network problems. Troubleshoot from link status through the local environment.

## Scope and evidence

This applies in version 8.1.8.7 when a link opens but the upload/download button is unavailable, the operation is denied, or transfer cannot start.

Changing whether a link can be used does not delete or remove the shared files or uploaded content. Link access and content deletion are separate controls and require separate authorization.

## Documented details

1. Check the page purpose: Download Share is for previewing or downloading, while Upload Invitation uploads to a specified directory. Do not look for the opposite operation in the wrong link type.
2. Ask the creator to confirm that the link remains “In Use,” has not passed its expiration time, and that your account or email belongs to the invitation scope.
3. For downloading, confirm that permission is “Preview and Download,” not “Preview Only,” and check whether the total link count or per-person count has reached its limit.
4. For uploading, confirm that the creator’s destination directory still exists, is writable, and has available capacity. “Allow Delete” is a separate setting and does not affect upload permission itself.
5. Refresh the page and complete the required verification again. Retry in a supported browser and confirm that the current network can access the site. If transfer starts and then stops, record the visible message and time.

## Interpretation and recovery boundary

Ask the creator to verify details using the same link and reproduce with a small non-sensitive test file. Do not share accounts, disable necessary verification, or request unrelated directory permissions just to complete the transfer.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

When link type, status, identity, permission, count/capacity, and network conditions are satisfied, the page displays the corresponding action and transfer can start. Access remains explicitly denied when security or policy conditions are not met.

## Escalation

If the creator confirms correct settings but the button is still absent, space capacity or role cannot be confirmed, several compliant users fail, or the page reports a global policy or service outage, ask an administrator to check user permissions, space/group roles, capacity, and service status. Provide the version, link type, operation, time, and visible message.
