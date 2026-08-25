---
id: RSKB-ADMIN-018
title: 'Administrator guide: how to check transfer service status'
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
- Where does Server Status show Rayfile health?
- Which indicator confirms that the P2P component is running?
- Does the administrator status view report a healthy FTP service?
keywords:
- server status
- Rayfile transfer service
- peer-to-peer transfer service
- FTP transfer service
- running normally
- component health
- service status
legacy_ids:
- KB-SERVICE-001
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/service-configuration/KB-SERVICE-001-how-to-check-service-status.md
  section: How to check transfer service status?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Administrator guide: how to check transfer service status

## Short answer

An administrator can view the Rayfile Transfer Service, Peer-to-Peer Transfer Service, and FTP Transfer Service under “Server Status” on the admin console home page. “Running Normally” means only that status detection shows the corresponding service is running; it does not prove that the network, certificate, permissions, or end-to-end function is available. “Not Running” means that the item is currently stopped, but does not by itself prove that the entire server or network has failed.

## Scope and evidence

This applies when checking whether the services for web file access, peer-to-peer transfer, or FTP transfer are running in version 8.1.8.7. Administrator permission to sign in to the admin console is required.



## Documented details

1. Sign in to the admin console and open the home page.
2. Under “Server Status,” check all three services separately instead of recording only one.
3. The page refreshes status automatically. You can also wait several seconds and refresh the page to confirm whether the status remains consistent.
4. If an item shows “Running Normally,” perform a limited target verification with a small non-sensitive file or the affected feature. Do not end troubleshooting based only on the status.
5. If an item shows “Not Running,” record the service name, discovery time, affected operation, and visible page message, then let an administrator decide whether to use the in-product restart operation.

## Interpretation and recovery boundary

If status cannot load, changes repeatedly, or is normal while the feature remains unavailable, also check whether the browser can access the server, whether the protocol and port are correct, and whether the certificate, permissions, and client status are valid. Do not treat a single status as the root cause.

This article does not authorize a state change. If the exact version, edition, target, or observed behavior differs from the supplied evidence, do not infer a broader capability or alter production state to make the description fit.

## Verification

Each of the three services displays “Running Normally” or “Not Running.” After a service recovers, its status changes to “Running Normally.” The current usage path is confirmed as recovered only after the limited target-function verification also succeeds.

## Escalation

If you cannot access the home page, an item remains “Not Running,” several items are unavailable at once, or the feature still fails after recovery, contact an administrator or technical support. Provide the product version, time, all three visible statuses, affected operation, and a redacted error.
