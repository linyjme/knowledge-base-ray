---
id: RSKB-TROUBLE-004
title: Troubleshoot port and connectivity failures
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
- Why does Error Detection report a TCP or UDP port failure?
- Which firewall checks help diagnose a transfer connection problem?
- How can I separate port reachability from an ordinary slow transfer?
keywords:
- port failure
- firewall
- Error Detection
- UDP
- TCP
- What should I do when Raysync reports a port or connectivity failure?
- troubleshooting
- Raysync
legacy_ids:
- FAQ-TROUBLE-009
safety_tags:
- license-control
- certificate
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/11-troubleshooting.md
  section: FAQ-TROUBLE-009 | What should I do when Raysync reports a port or connectivity failure?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Troubleshoot port and connectivity failures

## Short answer

Run the desktop client’s **Error Detection** and record the failed service port. For the current firewall guide, the documented minimum HTTP set is TCP 8090, 9090, 2480, and 2442 plus UDP 32001; the minimum HTTPS set is TCP 8091, 9091, 2481, and 2443 plus UDP 32001. Peer-to-peer transfer is consistently documented as TCP 3443, UDP 3478, and UDP 32003. In that HTTP set, 8090 is the user portal port for `http://[server-IP]:8090`, and 9090 is the admin console port for `http://[server-IP]:9090/admin`. A port number by itself is not a browser address.

## Diagnostic boundary

A port or connectivity failure is separate from an ordinary slow transfer and from the unactivated-server 5 Mbps license cap. Record the failed service port instead of inferring a license or bandwidth-setting problem.

## Likely cause

A required server firewall, cloud security-group, or NAT mapping may be missing. The approved client and firewall guides disagree about optional multi-channel port values, and the configuration guide does not provide a third list. Because those sources disagree, this article does not select or reproduce a competing matrix.

## What the user can check

Confirm that you are using the approved server address and network. Run **Error Detection**, including UDP speed detection if UDP transfer is slow, and save its report. Do not probe or change corporate firewall rules yourself.

## When to contact an administrator

Contact the administrator whenever a required port check fails. Provide the failed protocol/port, time, server address, and report so they can verify firewall, NAT, and cloud rules. For multi-channel transfer, the administrator must use the deployment/firewall documentation packaged or published for the installed server build and ask Raysync support if that build-specific documentation remains inconsistent.

## Version differences

Version 8.1.8.7 consolidated WebSocket, HTTP download, and preview ports. Always use the firewall document matching the installed server rather than an older memorized list.

## Important notes

Opening unnecessary ports increases exposure. End users should not choose between conflicting multi-channel sources or request that every value be opened; administrators should apply only the installed-build deployment rules.
