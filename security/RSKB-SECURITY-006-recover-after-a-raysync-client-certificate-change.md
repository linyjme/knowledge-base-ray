---
id: RSKB-SECURITY-006
title: Recover after a Raysync client certificate change
product: raysync
components:
- desktop-client
domain: security
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
- Why did the desktop client stop connecting after a certificate change?
- How do I recover the browser plug-in after custom client certificates are replaced?
- When should I restart the Raysync client for new certificate settings?
keywords:
- Support for custom client certificates
- client certificate
- browser plug-in
- restart client
- encrypted connection
- What is the Raysync client certificate, and what should I do after it changes?
- security
- Raysync
legacy_ids:
- FAQ-SECURITY-015
safety_tags:
- certificate
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-123 | Support for custom client certificates.
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-015 | What is the Raysync client certificate, and what should I do after it changes?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Recover after a Raysync client certificate change

## Short answer

The client certificate establishes the encrypted connection between the browser and the browser plug-in client. In the 8.1.8.0 and later guide, the server includes this certificate; online services update it annually, while an offline service needs an administrator to upload a new certificate when it expires. After a new certificate is uploaded, exit the browser plug-in client and start it again from the web page.

## Version differences

The legacy guide describes automatic retrieval from Raysync’s default storage for an online server and administrator upload for an offline server. The release list records support for custom client certificates in 8.1.8.6.

## Important notes

Do not confuse the client certificate with the TLS certificate shown by the user portal HTTPS address. If restarting the browser plug-in client does not restore its connection, contact the administrator; certificate upload and source selection are not end-user tasks.

## Related documented boundaries

- **Support for custom client certificates.:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported The source records 8.1.8.6 as an appearance or change milestone, not as proof of the onset of support.
