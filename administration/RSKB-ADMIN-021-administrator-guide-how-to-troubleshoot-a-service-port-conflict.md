---
id: RSKB-ADMIN-021
title: 'Administrator guide: how to troubleshoot a service port conflict'
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
- What should I do if a service cannot start because its port is occupied?
- How do I investigate when the web page is inaccessible after changing a port?
- Can two services use the same port?
keywords:
- port conflict
- port occupied
- service not running
- network access rule
- port listening
- troubleshoot a
- service port
- conflict
legacy_ids:
- KB-SERVICE-004
safety_tags:
- authorization
- destructive-operation
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-004-service-port-conflict.md
  section: How to troubleshoot a service port conflict?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to troubleshoot a service port conflict

## Short answer

A port conflict may prevent a service from recovering, make an address inaccessible, or cause client connection failures, but these symptoms can also result from network policy or service status. In-product transfer or peer-to-peer ports and deployment-level HTTP/HTTPS access ports have different change scopes. Follow the post-save page prompt for the former; the deployment administrator must apply and verify the latter through an approved process. Do not treat both as a generic "restart the corresponding service" operation.

## Prerequisites

This applies in version 8.1.8.7 when access becomes abnormal after changing an HTTP, HTTPS, transfer, or peer-to-peer port, or when a service continues to show "Not Running."



## Effect

Changing an in-product service port changes the listener used by that service, and the prompted restart temporarily interrupts the affected service. Deployment HTTP or HTTPS ports and firewall policy are separate changes owned by deployment or network administrators.

## Confirmation

Confirm the exact service, current and proposed port, protocol, listener ownership, network rule, active-task impact, approved change window, and supported restart path before making a change.

## Procedure

1. Confirm the protocol, server address, and port in use from administrator-provided information, and rule out input errors or an outdated bookmark.
2. Compare the port plan and confirm that the same port on the same address is not assigned to two services that must listen simultaneously.
3. Open the approved server address in a browser to determine whether the entire site is inaccessible or only a specific transfer function fails.
4. Ask the server administrator to use organization-approved network management tools to confirm that the target service is actually listening on the expected port.
5. Ask the network administrator to confirm that the firewall, proxy, or perimeter policy opens the port only to necessary sources and that requests reach the server.
6. If an in-product transfer or peer-to-peer port was changed, save and restart only through the admin console when prompted, then check the corresponding service status and target function.
7. If a deployment-level HTTP/HTTPS port was changed, the deployment administrator must apply it through the approved change process and verify access with the approved protocol, address, and port. Do not use an in-product transfer-service restart as a general method for applying deployment-port changes.

## Recovery boundary

If ports are unique and the network permits access, continue by checking the certificate domain, protocol selection, and service status. Do not conclude that there is a port conflict from "connection failed" alone, and do not broaden firewall access for trial and error.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

The target service listens on a unique, approved port, the required network path is reachable, the admin page or client can use the corresponding function, and Server Status remains "Running Normally."

## Escalation

Port planning, listening confirmation, and network-policy changes must be performed by the appropriate administrator. The product administrator handles in-product transfer or peer-to-peer ports according to page prompts; the deployment administrator applies and verifies deployment-level HTTP/HTTPS ports through the approved process. Provide the protocol and port, time, impact scope, visible service status, and a redacted error.
