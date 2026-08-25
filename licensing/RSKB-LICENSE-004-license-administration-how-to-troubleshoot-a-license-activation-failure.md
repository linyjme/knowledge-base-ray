---
id: RSKB-LICENSE-004
title: 'License administration: how to troubleshoot a License activation failure'
product: raysync
components:
- admin-portal
domain: licensing
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
- What should I do if an error appears after entering the activation code?
- How do I investigate repeated online activation failures?
- Why did importing the activation file fail?
keywords:
- activation failure
- format error
- invalid License
- unsupported version
- machine mismatch
- troubleshoot a
- License activation
- failure
legacy_ids:
- KB-LICENSE-004
safety_tags:
- authorization
- license-control
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-004-license-activation-failed.md
  section: How to troubleshoot a License activation failure?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to troubleshoot a License activation failure

## Short answer

Use the visible page error to distinguish an input-format, network, activation-information validity, machine-environment change, edition, or administrator-permission issue, then address the corresponding cause. Do not repeatedly try activation codes or files from unknown sources. If you cannot confirm the cause, retain the error text and contact official technical support.

## Prerequisites

This applies to online or offline activation in version 8.1.8.7. Common customer-visible messages include activation-code format error, incorrect activation code, expired License, invalid License, current version not supported, request-file generation failure, and response-file activation failure.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Effect

Retrying online activation or importing an offline response can change the License state for the exact server. A request may also consume a support workflow step, so retry only once after correcting a confirmed transient or formatting issue.

## Confirmation

Confirm the exact server, current License status, applicable version and edition, activation mode, complete visible error, official activation material, and one approved retry before submitting.

## Procedure

1. Record the complete error text and the stage at which it occurred: after input, during online submission, while generating the request file, or while importing the response file.
2. If a format error appears, copy the activation code again from the official delivery information, remove extra spaces or line breaks, and do not edit it manually.
3. If online submission has a connection problem, check the target server’s network, proxy, firewall, and outbound policy, then retry only once.
4. If the code is invalid or expired, confirm that you are using current activation information and contact sales or support to verify the validity period.
5. If the machine environment changed recently, treat it as a possible mismatch, stop repeated activation attempts, and contact support for confirmation.
6. If the current version is not supported, verify the product version, edition, and upgrade target. Do not continue using activation information that does not apply to the current version.
7. If the button is not visible or cannot be used, confirm that the current account has product administrator permission.

## Recovery boundary

Refresh the page to confirm whether the License status changed and avoid duplicate submission caused by stale page information. In an offline scenario, also confirm that the request and response files belong to the same process and were not modified. If the failure persists, do not continue changing the environment or perform any operation not confirmed by official support.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

The administrator can classify the failure clearly and activate successfully after correcting a customer-visible input or environment issue. Official sales or technical support handles cases that require new activation information.

## Escalation

If the error persists, the machine environment changed, the upgraded version is reported as unsupported, or activation validity is uncertain, contact official technical support. Provide the product version, visible status, edition, complete error text, activation method, and recent environment changes. Do not submit the complete activation code or complete activation file.
