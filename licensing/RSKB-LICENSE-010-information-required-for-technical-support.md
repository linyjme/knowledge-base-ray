---
id: RSKB-LICENSE-010
title: 'License administration: what information is required when contacting technical support about a License issue'
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
- Which information should I provide in a License support ticket?
- How should I describe an activation failure when contacting support?
- Which License information can be submitted safely?
keywords:
- technical support
- product version
- error information
- activation method
- machine identifier
- what information
- is required
- when contacting
legacy_ids:
- KB-LICENSE-010
safety_tags:
- authorization
- license-control
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-010-information-required-for-license-support.md
  section: What information is required when contacting technical support about a License issue?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: what information is required when contacting technical support about a License issue

## Short answer

First provide the product version, edition, and summary status under “License Information”: “Activated” or “Not Activated.” Record any expiration or invalid warning separately. If an operation fails, also provide the complete error text, activation method, and time. Provide a non-sensitive machine identifier shown on the page only when the page or official support form explicitly requests it. Do not submit the complete activation code, request file, or response file in an ordinary ticket body.

## Prerequisites

This applies to activation failure, abnormal status, expiration, renewal, upgrade, or machine-change issues in version 8.1.8.7. Submit information through an official support channel and follow the organization’s data-classification and file-transfer requirements.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Effect

Submitting a diagnostic record or requested file discloses the selected information to official technical support. It does not change the License by itself, but an unredacted or misrouted submission can expose activation material or customer data.

## Confirmation

Confirm the exact support case, designated secure channel, requested non-sensitive fields or file, redaction, authorized recipient, and organizational approval before submitting anything.

## Procedure

1. Record the current product version and the edition displayed on the page, such as Free, Professional, or Enterprise.
2. Separately record the summary status under “License Information,” using only “Activated” or “Not Activated.”
3. Separately record whether the page displays an expired or invalid warning. If an operation fails, copy the complete error text returned by that operation. Do not rewrite a warning or error as the summary status.
4. State whether online or offline activation was used, the step that failed, the time, and whether the failure can be reproduced reliably.
5. State whether a recent upgrade, renewal, or server, virtual machine, or system environment change occurred. Describe only the change type and time.
6. Before taking a screenshot, redact the complete activation code and unrelated customer information. Retain only the page title, summary status, edition, and warning or error area.
7. Provide a customer-visible, non-sensitive machine identifier or a file required for the current offline process through the designated secure channel only when the official support process explicitly requests it.

## Recovery boundary

When support requests more information, first confirm that the request comes through an official channel and that its purpose and transfer method are clear. If you cannot determine whether an item is sensitive, provide only the field name and a redacted example first, wait for support confirmation, and do not send the complete content directly.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

Technical support can distinguish the License summary status, page warning, and operation-specific error, and use the minimum safe information to identify the product version, failure stage, and environment change, then advise the required official action or information.

Verify that the designated secure channel accepted only the requested redacted material, and retain the support case reference without copying sensitive contents into ordinary notes.

## Escalation

If the ticket involves a production environment, machine migration, complete file exchange, or organizational compliance approval, ask the product administrator and security owner to handle it together. Do not submit a complete activation code, complete activation file, unrelated account information, or broad unfiltered logs.
