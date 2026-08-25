---
id: RSKB-ADMIN-026
title: 'Administrator guide: how to distinguish network, certificate, and service-status problems'
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
- How do I tell whether a connection failure is caused by the network or the service?
- Is a browser certificate warning related to a stopped server service?
- Does a web page timeout mean there is a certificate problem?
keywords:
- network problem
- certificate problem
- service status
- connection timeout
- certificate warning
- distinguish network
- certificate
- and service-status
legacy_ids:
- KB-SERVICE-009
safety_tags:
- sensitive-diagnostics
- certificate
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-009-network-certificate-or-service-problem.md
  section: How to distinguish network, certificate, and service-status problems?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to distinguish network, certificate, and service-status problems

## Short answer

Assess browser access, certificate messages, server status, and impact scope together. A timeout or complete inaccessibility is more consistent with a network-path problem; an explicit not-yet-valid, expired, untrusted, or domain-mismatch message is more consistent with a certificate problem; and an item shown as “Not Running” is more consistent with its corresponding service. No single symptom is enough to confirm the root cause directly.

## Scope and evidence

This applies in version 8.1.8.7 when a web page cannot open, HTTPS shows a warning, the file service is abnormal, a client connection fails, or a transfer cannot start and the correct troubleshooting direction must be selected first.



## Documented details

1. Test browser access using the complete administrator-provided URL and record whether it times out, refuses the connection, shows a certificate warning, opens the sign-in page, or fails only after sign-in.
2. If the same address times out for several compliant users or networks, check the address, name resolution, proxy, firewall, and port reachability. If only one network fails, prioritize that network’s policy.
3. If the browser explicitly reports a certificate that is not yet valid, expired, untrusted, or domain-mismatched, ask the administrator to check the certificate and actual access domain.
4. If the web page opens but a specific transfer function fails, ask the administrator to check the independent Rayfile, peer-to-peer, and FTP statuses.
5. If status is normal but the client still fails, use client “Error Detection” to compare the domain, proxy, certificate, and server status, and check account permissions.
6. Change only one approved condition at a time before retesting so the evidence remains clear.

## Interpretation and recovery boundary

Compare the same user on different networks, different users on the same network, and approved HTTP and HTTPS entries. Record differences and do not change trust, proxy, or security policies yourself.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

The issue can be classified more specifically as a network path, certificate, service status, or account/client problem and handled by the appropriate administrator. After recovery, browser access, service status, and the target operation all pass verification.

## Escalation

If network policy, certificate, port, or service status must change, or several areas are abnormal at the same time, contact an administrator or technical support. Provide the version, protocol and port from the URL, time, impact scope, and a redacted visible message.

