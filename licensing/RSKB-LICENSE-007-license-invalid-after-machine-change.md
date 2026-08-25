---
id: RSKB-LICENSE-007
title: 'License administration: what to do when the License becomes invalid after a machine environment change'
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
- Why did the License become invalid after replacing the server?
- What should I do if the License is invalid after virtual machine migration?
- What should I do if activation status is abnormal after a system environment change?
keywords:
- machine environment change
- server migration
- virtual machine change
- invalid License
- system environment change
- what to
- do when
- the License
legacy_ids:
- KB-LICENSE-007
safety_tags:
- authorization
- license-control
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-007-license-invalid-after-machine-change.md
  section: What to do when the License becomes invalid after a machine environment change?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: what to do when the License becomes invalid after a machine environment change

## Short answer

If the page shows not activated, invalid, or activation failed after a server, virtual machine, or system environment change, record the customer-visible status, change type, and time, then contact official technical support for the next steps. Do not infer the exact relationship between the change and License status, and do not repeatedly try old files.

## Prerequisites

This applies when License status becomes abnormal after a server, virtual machine, or system environment change in version 8.1.8.7. The customer-visible page cannot determine the exact cause or whether reactivation is required. Official technical support must confirm the current scenario.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

## Effect

Support-confirmed reactivation binds valid activation information to the current target environment and changes its License state. Generating a new offline request is specific to that environment and must not be reused for another server.

## Confirmation

Confirm the exact changed environment, current License status, applicable version and edition, recoverable business state, support authorization, and online or offline reactivation path before proceeding.

## Procedure

1. Pause further migration or repeated changes to the current environment and preserve the current recoverable business state.
2. Go to “Device Management > Server Management” and record the product version, edition, License status, and complete visible error.
3. Organize the type and time of recent environment changes. Describe only what changed in the server, virtual machine, or system environment; do not list or speculate about specific causes.
4. Contact official technical support and describe the change scenario. Ask support to confirm whether the existing activation information still applies or must be reissued.
5. Reactivate only through the online or offline process confirmed by support. For an offline scenario, generate a new request file for the current target environment.
6. After completion, verify the status, validity period, edition, and usage limits, and test the affected customer-visible features.

## Recovery boundary

If reactivation still reports invalid, confirm that the operation occurred on the target server confirmed by support and provide the new visible error. Do not continue changing the machine environment or attempt a recovery operation that official support has not confirmed.

Only an authorized owner may perform the described change for the confirmed target. If authority, scope, or the expected result is unclear, stop. Restore the recorded prior value only through the documented interface or owning system when that recovery is supported; otherwise escalate without expanding the change.

## Verification

Official support confirms the procedure for the current machine environment, and new or confirmed-valid activation information takes effect on the target server. The page returns to “Activated” and displays the correct limits.

## Escalation

If activation becomes invalid immediately after a production environment change, the admin center is inaccessible, or it is unclear which visible information should be recorded, ask the product administrator to contact official technical support. Provide the product version, visible License status, complete error, environment-change type, and time. Do not submit the complete activation code, complete activation file, or unrelated environment information.
