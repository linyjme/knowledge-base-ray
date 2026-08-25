---
id: RSKB-TROUBLE-022
title: Troubleshoot an expired or disabled link
product: raysync
components:
- user-portal
- desktop-client
domain: troubleshooting
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
- Why does a collaboration link say that it is expired or disabled?
- Who can reactivate a canceled share or invitation?
- What should a recipient do when link access is no longer available?
keywords:
- link expired
- link disabled
- share-download link
- invite-upload link
- Why does a share-download or invite-upload link say it is expired or disabled?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-017
safety_tags:
- credentials
- authorization
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-017 | Why does a share-download or invite-upload link say it is expired or disabled?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot an expired or disabled link

## Short answer

The link creator can set an expiration time. A share-download link can also be disabled, after which it is no longer accessible; invite-upload links can be canceled. The link creator, not the visitor, must issue or re-enable valid access.

## Likely cause

The configured expiration time passed, the creator disabled/canceled the link, download was turned off on a share-download link, or an access condition such as password, specified email, organization login, or first-device binding is not satisfied.

## What the user can check

Use the exact current link and password supplied by the creator, complete the required login/email verification, and confirm you are using the authorized device if binding is enabled. Do not guess credentials.

## When to contact an administrator

Contact the link creator first for validity and access scope. Contact an administrator if device unbinding or organization-wide link policy is involved.

## Version differences

Version 8.1.8.0 added user portal link filters, and 8.1.8.3 added shared-link enable/disable. Recipient-email protection does not have a clean release boundary in the supplied evidence: specified-email access is documented in 6.8.8.2 and recipient-email protection appears again in 8.1.8.3. The sources do not explain whether the later entry changes scope or repeats the earlier capability, so verify the required email option in the deployed interface.

## Important notes

Do not request a policy bypass for restricted content.
