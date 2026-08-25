---
id: RSKB-LICENSE-003
title: 'License administration: how to activate a License in an offline environment'
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
- How do I activate a License when the server cannot access the internet?
- How do I generate an offline activation request file?
- Where do I import the activation file returned by technical support?
keywords:
- offline activation
- activation request file
- import activation file
- isolated network
- technical support
- activate a
- License in
- an offline
legacy_ids:
- KB-LICENSE-003
safety_tags:
- license-control
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/license-activation/KB-LICENSE-003-how-to-activate-offline.md
  section: How to activate a License in an offline environment?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# License administration: how to activate a License in an offline environment

## Short answer

In an offline environment, first generate an activation request file in the admin center, deliver it to official technical support through a controlled method, and then import the activation file returned by support to complete activation. The request and response files must come from the same target environment and remain unchanged. Do not open and rewrite their contents.

## Prerequisites

This applies in version 8.1.8.7 when the target server cannot complete online activation but an administrator can exchange files with official technical support through organization-approved controlled media or a transfer environment. Before starting, obtain an activation code for the current product and reserve a possible service restart window.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **activate a License in an offline environment** in the intended deployment, edition, and component.

## Effect

In an offline environment, first generate an activation request file in the admin center, deliver it to official technical support through a controlled method, and then import the activation file returned by support to complete activation. The request and response files must come from the same target environment and remain unchanged. Do not open and rewrite their contents.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Sign in with an administrator account, go to “Device Management > Server Management,” and select “Activate” under “License Information.”
2. On the “Enter Activation Code” page, accurately enter the officially provided activation code and continue.
3. On the offline activation page, select “Generate” and download the activation request file created for the current environment.
4. Deliver the request file to official technical support using an organization-approved secure method. Do not modify the file name or contents.
5. After receiving the activation file returned by technical support, securely bring it back to the original target environment and select “Import” on the same page.
6. Select the returned file and choose “Activate.” If the page prompts for a restart, follow the page instructions during a maintenance window.
7. Review “License Information” again and confirm that the status, expiration time, and limits are updated.

## Recovery boundary

If request-file generation fails, verify the activation code and generate it again. If import fails, confirm that you are using the original file returned by technical support for this specific request. If the target machine environment changed after the request was generated, stop importing the old response file, generate a new request, and contact support for the next steps.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

After activation, the page displays “Activated” and the details show the currently effective License information. If a restart is required, the status remains normal after the restart completes.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If the organization prohibits file transfer, the returned file cannot be imported, the page reports activation failure, or you cannot confirm that the request and response files match, ask the product administrator to use the official support channel. Transfer only the files required by this process. Do not paste file contents into ordinary chat or a ticket body.

Only an authorized administrator may review or change license state. Confirm the exact deployment and license target; never publish activation material or a machine fingerprint.

