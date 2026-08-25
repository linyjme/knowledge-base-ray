---
id: RSKB-TROUBLE-014
title: Diagnose a connected proxy with no traffic
product: raysync
components:
- client-manager
- file-service
domain: troubleshooting
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Why does the proxy show connected while application requests carry no useful traffic?
- Which counters separate a wrong local entry from a missing return path or unavailable
  target service?
- What proves transport and target response after a connection indicator turns healthy?
keywords:
- proxy connected no traffic
- local proxy entry
- bidirectional counters
- return path
- target service health
- empty response
legacy_ids: []
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/proxy-connected-but-no-traffic.md
  section: What to do if the proxy is connected but there is no traffic
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Diagnose a connected proxy with no traffic

## Short answer

Connected proves only the connection phase. Confirm that the application uses the correct local entry, then correlate client and server bidirectional counts and target-service response.

## Symptoms

The proxy reports connected but a minimum application request times out, returns empty, or leaves send and receive counters unchanged.

## Checks

Use one non-sensitive request through the correct local entry. Compare client connection and bidirectional counts before and after, then server session and counts in the same window. Check the return path, name resolution, route, access policy, target service health, application response handling, and whether retries or long connections obscure the observation.

## Interpretation

No client counter change indicates the application or local entry. Client send without server record indicates the connection path. Server one-way traffic indicates the return path. Bidirectional server traffic without an application result indicates target-service or response handling. Worker process presence alone is not application readiness.

## Backup or recovery boundary

Keep the original entry, counter snapshot, request result, and target policy as the recovery baseline. Do not change undisclosed settings or global policy, and suspend automatic retries while isolating one target.

## Corrective action

An authorized operator must confirm the exact target application, local entry, proxy type, service, and minimum request. Confirm the expected effect, correct one evidenced entry, route, policy, or target-service cause, and repeat the same request once.

## Verification

Post-action verification requires the same target request to show matching client and server bidirectional counts, a valid response, terminal application result, and any expected target-side effect.

## Evidence to collect

Collect redacted entry type, time window, response category, before-and-after counters, return-path category, and target health result. Use `<host>`, `<service>`, and `<path>` placeholders; omit request content and customer data.

## Escalation

Escalate when counts diverge without a policy explanation, the target is healthy but no response returns, or the connected state cannot be correlated with the request timeline.
