---
id: RSKB-SECURITY-001
title: Verify HTTPS and troubleshoot portal certificates
product: raysync
components:
- user-portal
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
- Why does the browser warn that the Raysync portal certificate is invalid?
- How can I confirm that the portal connection is using HTTPS?
- Is browser certificate trust separate from transfer encryption?
keywords:
- Upload server certificate to enable encrypted web access via domain name
- HTTPS
- TLS
- user portal
- secure connection
- '8091'
- How do I know whether my Raysync web session uses HTTPS and TLS?
- TLS 1.3
legacy_ids:
- FAQ-SECURITY-001
safety_tags:
- credentials
- certificate
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-115 | Upload server certificate to enable encrypted web access via domain name.
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-001 | How do I know whether my Raysync web session uses HTTPS and TLS?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-251 | TLS 1.3
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-116 | Prohibit non-SSL security connection
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-002 | Why does my browser show a certificate warning for the Raysync user portal?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Verify HTTPS and troubleshoot portal certificates

## Short answer

Use the HTTPS address supplied by your administrator. Raysync documents the user portal format as `https://<domain>:8091/`. The `https://` scheme indicates that the browser session uses HTTPS encryption. File-transfer encryption is a separate control, so an encrypted transfer does not turn an `http://` portal session into HTTPS.

## Security boundary

A browser or portal HTTPS certificate protects the web session. Transfer encryption is a separate control and must not be inferred from the browser certificate state. The legacy source says an uploaded server certificate enables encrypted web access without a version boundary, while the 8.1.8.0 source separates portal HTTPS certificates from transfer TLS. These claims conflict and remain unresolved, so no historical certificate-scope claim is selected.

## Version differences

Before version 8.1.8.0, the legacy guide describes certificate services broadly as supporting encrypted web access and file-transfer encryption. The 8.1.8.0 and later guide explicitly separates HTTPS portal access from TCP TLS file transfer. In every documented version, certificate provisioning is an administrator prerequisite; an end user needs the approved HTTPS user portal address.

## Important notes

Only the 8.1.8.0 and later guide explicitly states that the built-in Raysync certificate is for transfer encryption only. In that guide family, HTTPS web-session encryption requires an administrator-provided TLS certificate, normally a public-CA certificate matching the service domain. The legacy guide uses broader wording and should not be silently reinterpreted as the newer certificate model. If non-TLS connections are prohibited, the user portal cannot be opened over HTTP.

## Related documented boundaries

- **TLS 1.3:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Prohibit non-SSL security connection:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Why does my browser show a certificate warning for the Raysync user portal?:** Do not treat the warning as a normal login step. In the 8.1.8.0 and later guide, the built-in Raysync certificate is only for transfer encryption; HTTPS web-session encryption requires a certificate supplied by the administrator, typically issued by a public certificate authority and matching the service domain. The legacy guide uses broader wording for encrypted web access and file-transfer encryption and does not state that newer built-in-certificate limitation. Use the exact approved HTTPS address rather than bypassing the warning.
