---
id: RSKB-ADMIN-022
title: 'Administrator guide: how to troubleshoot a file service connection failure'
product: raysync
components:
- admin-portal
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- What should I do if the file list never loads?
- How do I handle a file service error shown on the page?
- Why can I sign in to the web page but not browse files?
keywords:
- file service connection failure
- file service error
- Rayfile transfer service
- file list
- upload and download
- troubleshoot a
- file service
- connection failure
legacy_ids:
- KB-SERVICE-005
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-005-file-service-connection-failed.md
  section: How to troubleshoot a file service connection failure?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to troubleshoot a file service connection failure

## Short answer

A file service connection failure is not caused only by a stopped service. Network reachability, address and port, HTTPS certificate, user permissions, or client status may also be involved. First determine the failure scope, then troubleshoot from service status through connection conditions.

## Scope and evidence

This applies in version 8.1.8.7 when the web page can be opened but the file list does not load, the page reports a "File Service Error," uploads or downloads cannot start, or the connection repeatedly drops.



## Documented details

1. Refresh the page and record the exact message, time, affected space, and operation. Determine whether one user, one network, or several users are affected.
2. Ask an administrator to check "Rayfile Transfer Service" on the home page. If it shows "Not Running," the administrator should recover it through the product-supported process.
3. Verify that the current server address, protocol, and port match the administrator-provided information and that the browser can open the server page normally.
4. When using HTTPS, check whether the browser reports an expired, untrusted, or domain-mismatched certificate.
5. Confirm that the account can still sign in, can see the target space, and has the permissions required to browse, upload, or download. Do not grant unrelated permissions for troubleshooting.
6. If using the transfer plugin, confirm that it is running and use "Error Detection" to check the domain, proxy, certificate, and server status.

## Interpretation and recovery boundary

Retest the same account on another approved network or browser, or test another compliant account on the same network, to narrow the scope. Do not classify missing account permission, a certificate warning, or an offline client as a stopped file service.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

When the service is running, the network is reachable, connection information is correct, the certificate is valid, and the account has permission, the file list loads and permitted uploads or downloads can start.

## Escalation

If Rayfile Transfer Service remains stopped, several users fail at once, the port or certificate cannot be confirmed, permissions are controlled by organizational policy, or limited retesting still fails, contact an administrator or technical support and provide non-sensitive diagnostic information.

