---
id: RSKB-ADMIN-027
title: 'Administrator guide: which service operations require an administrator'
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
- Can a regular user restart services?
- Which connection problems must be handled by an administrator?
- Can users modify ports and certificates?
keywords:
- service configuration permission
- safe customer check
- port and certificate
- service restart
- service ownership boundary
legacy_ids:
- KB-SERVICE-010
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-010-operations-requiring-administrator.md
  section: Which service operations require an administrator?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: which service operations require an administrator

## Short answer

A regular user can check the server URL, browser messages, client status, and their own permissions. The user may also refresh the web page or restart their own transfer plugin through its visible product menu. Service restarts, port and address configuration, TLS certificates, peer-to-peer settings, and organizational network policies must be handled by the appropriate administrator. Do not weaken security requirements or broaden access to restore a connection.

## Prerequisites

This applies in version 8.1.8.7 when a user is unsure whether they can handle a stopped service, connection failure, port, HTTPS, or peer-to-peer configuration problem independently.

The user must act only on their own browser session and transfer plugin. Viewing complete server status, stopping or restarting a service, changing server information or peer-to-peer settings, changing ports or network policy, and uploading or updating certificates require the appropriate administrator.

## Effect

Refreshing the page or restarting the user's own transfer plugin changes only that confirmed client-side target. It does not restart a server service or authorize any server, network, certificate, peer-to-peer, License, account, role, space, or permission change.

## Confirmation

Before restarting the transfer plugin, confirm that the visible product menu belongs to the affected user's client and that no server-service control is being selected. Record the time, affected operation, visible error, whether only one user is affected, and the abnormal category reported by the client's Error Detection view.

## Procedure

1. Confirm that the administrator-provided URL is entered correctly, and test whether the page opens in a supported browser.
2. Check the affected user's client status and their account, space, and operation permissions.
3. If the target is the affected user's own transfer plugin, refresh the web page or restart that plugin once through its visible product menu. Do not use a server-service control.
4. Hand off tasks that require viewing complete server status, stopping or restarting a service, or changing server information or peer-to-peer settings to the product administrator.
5. Hand off HTTP/HTTPS or transfer-port changes, listening confirmation, and firewall, proxy, or name-resolution changes to the deployment or network administrator.
6. Hand off TLS certificate upload or update, certificate trust, and validity issues to the certificate administrator. Hand off edition-limited features to the License administrator for evaluation.

## Recovery boundary

Do not try unapproved ports, reduce certificate-validation requirements, or loosen organizational network policy. A client-side refresh or plugin restart has no automatic rollback. If the plugin does not return to an available state, stop repeating the restart and give the recorded, redacted evidence to the product administrator. Do not provide sign-in credentials or sensitive material.

Server, network, certificate, peer-to-peer, and License changes are outside this article's authority. Use the owning administrator's reviewed procedure rather than expanding the client-side action.

## Verification

After the client-side action, verify that the exact user's transfer plugin is available and retry only the target operation. Confirm that no server configuration or another user's state changed. When an administrator configures or restarts through a product-supported entry, the affected user verifies the target operation again.

## Escalation

Escalate to the corresponding administrator when several users fail at once, a service remains stopped, a certificate warning appears, port or network policy is unclear, a saved configuration requires a restart, or the current edition does not support the feature. If the administrator cannot recover it, contact technical support with the product version, user role, impact scope, last successful time, and redacted screenshot or message.
