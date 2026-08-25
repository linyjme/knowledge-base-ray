---
id: RSKB-ADMIN-020
title: 'Administrator guide: how to configure and verify HTTP and HTTPS access'
product: raysync
components:
- admin-portal
domain: administration
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
- Which TLS certificate and ports must be prepared for portal HTTPS?
- How is non-TLS web access prohibited after secure access is verified?
- Does the chosen HTTP or HTTPS port match the deployment firewall?
keywords:
- HTTP
- HTTPS
- TLS certificate
- prohibit non-TLS connections
- access port
- secure web access
- verify HTTP
- HTTPS verification
legacy_ids:
- KB-SERVICE-003
safety_tags:
- authorization
- certificate
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-003-how-to-configure-http-and-https.md
  section: How to configure and verify HTTP and HTTPS access?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to configure and verify HTTP and HTTPS access

## Short answer

HTTP and HTTPS must use access ports approved by the deployment administrator and not occupied by another service. HTTPS also requires complete TLS certificate material that is valid, unexpired, and matches the access domain. In version 8.1.8.7, certificates can be uploaded on the “TLS Certificate” page under “Certificate Management,” and supported editions can select “Prohibit Non-TLS Connections.”

## Prerequisites

This applies when an administrator enables encrypted access for the admin or user portal, updates a certificate, or restricts unencrypted access. The Trial edition does not support “Prohibit Non-TLS Connections.” Deployment-level access-port changes must be performed by the deployment administrator.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **configure and verify HTTP and HTTPS access** in the intended deployment, edition, and component.

## Effect

HTTP and HTTPS must use access ports approved by the deployment administrator and not occupied by another service. HTTPS also requires complete TLS certificate material that is valid, unexpired, and matches the access domain. In version 8.1.8.7, certificates can be uploaded on the “TLS Certificate” page under “Certificate Management,” and supported editions can select “Prohibit Non-TLS Connections.”

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Ask the deployment administrator to confirm the access domain, HTTP/HTTPS ports, and permitted network scope. Ensure that the ports are unique and not occupied.
2. Go to “Certificate Management,” select “TLS Certificate,” and submit the complete organization-approved certificate material.
3. Check the certificate validity period and domain displayed on the page. Do not enable encrypted-only access if the certificate is invalid, not yet valid, expired, or does not match the access domain.
4. If the edition supports it and the organization requires HTTPS only, select “Prohibit Non-TLS Connections” and save.
5. If the page provides an in-product restart entry, follow the prompt to restart, then verify the expected HTTP/HTTPS behavior using approved addresses. In safe mode, or when only a restart prompt appears without an in-product entry, do not restart outside the product interface. The deployment administrator must follow the approved process and contact technical support if needed.

## Recovery boundary

Verify that the domain, protocol, and port used by the browser exactly match the administrator-provided information, and check the certificate validity period and network policy. A certificate warning, connection timeout, and stopped service are different clues and cannot substitute for one another.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

The HTTPS address opens, and the browser shows a trusted certificate whose domain matches. After “Prohibit Non-TLS Connections” is enabled, the unencrypted entry no longer provides access. If it is not enabled, availability of both entries depends on the deployment configuration.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. Port selection or changes, network-policy adjustments, certificate acquisition, certificate-trust problems, and service restarts all require an administrator. Deployment-level HTTP/HTTPS port changes and effective-state verification must be completed by the deployment administrator through an organization-approved process. Provide the access method, time, browser-visible message, and product version. Do not send sensitive certificate material.
