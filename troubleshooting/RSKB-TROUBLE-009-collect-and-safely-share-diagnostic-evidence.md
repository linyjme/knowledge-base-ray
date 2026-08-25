---
id: RSKB-TROUBLE-009
title: Collect and safely share diagnostic evidence
product: raysync
components:
- client-manager
- file-service
- node-scheduler
- typhoonv6
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
- What sanitized evidence lets another engineer reconstruct a transfer failure timeline?
- Which diagnostic materials must stay out of public tickets and ordinary chat?
- How should stable placeholders preserve chronology without revealing customer identities?
- How should I redact client logs before sharing them?
- What is safe for an engineer to attach to a support case?
keywords:
- sanitized diagnostics
- stable placeholders
- problem timeline
- log excerpt
- controlled support channel
- evidence inventory
legacy_ids: []
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: source_file/collect-safe-diagnostics.md
  section: Collect TyphoonV6 security diagnostic information
  evidence_type: technical-boundary-document
- file: source_file/what-information-can-be-shared.md
  section: What information can be shared when troubleshooting?
  evidence_type: technical-boundary-document
- file: source_file/diagnostic-collection.md
  section: How to collect diagnostic information
  evidence_type: technical-boundary-document
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Collect and safely share diagnostic evidence

## Short answer

Preserve the scene before any restart or change. Share only the smallest redacted timeline, status, result, and target evidence needed to identify the failed stage; keep originals local and use a controlled channel for approved sensitive material.

## Symptoms

Support cannot distinguish request, task, connection, file-write, or verification failure from a single generic message, or the available bundle includes private environment details.

## Checks

Record product versions, platforms, roles, start and end times with time zone, impact, recent change, and one minimum reproduction. Collect role status, request or command result, state transitions, failed or skipped file summary, target count, size and available checksum. Keep an original copy, then inspect every external copy for addresses, accounts, secrets, certificate contents, customer data, topology, and unrelated events.

## Interpretation

Useful evidence answers whether the request arrived, whether a task started, where the connection failed, whether data was written, and whether the target was verified. Stable placeholders preserve cross-log correlation; removal of chronology or error category makes the bundle misleading.

## Backup or recovery boundary

Evidence collection is non-destructive. The original copy is the recovery boundary and stays under local access control. Do not delete, rewrite, or compress away the only failure scene before a verified sanitized copy and material inventory exist.

## Corrective action

An authorized evidence owner must confirm the exact target time window, roles, and material scope. Confirm the effect of redaction, make a copy, replace sensitive values with stable placeholders, re-read the result, and use only the organization-approved controlled channel.

## Verification

Post-action verification checks that the sanitized target bundle remains chronologically complete, each item names source role and collection time, placeholders are consistent, and no secret or customer content remains.

## Evidence to collect

Usually share versions, platforms, role status, time zone, impact, masked error categories, state sequence, and minimum reproduction result. Do not share full settings, private addresses, real accounts, passwords, tokens, private keys, packet captures, dumps, customer data, or full logs by default.

## Escalation

Escalate immediately through security procedures for data loss, unauthorized access, or suspected disclosure. Ask support to approve scope, retention, and secure transport before sending packet captures or detailed dumps.
