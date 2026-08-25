---
id: RSKB-IAM-012
title: 'Identity administration: how to select the default authentication method'
product: raysync
components:
- admin-portal
domain: identity-access
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
- How do I set the default user sign-in method?
- Which sign-in entry is affected by default authentication?
- Why can’t an authentication method be set as default?
keywords:
- default authentication method
- sign-in entry
- enabled status
- switch authentication
- user sign-in
- select the
- default authentication
- method
legacy_ids:
- KB-USER-006
safety_tags:
- authorization
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: knowledge-base/user-integration/KB-USER-006-how-to-select-default-authentication.md
  section: How to select the default authentication method?
  evidence_type: product-documentation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identity administration: how to select the default authentication method

## Short answer

“Default Authentication Method” determines the authentication entry used first when a user opens the sign-in page. Only an enabled, fully configured method can be selected as default. Test the new method before switching, and do not directly disable the current default method.

## Prerequisites

This applies to version 8.1.8.7 environments with two or more enabled sign-in methods that want one standard entry for most users. The operator needs User Integration management permission and should preserve administrator access that follows the organization’s emergency process.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **select the default authentication method** in the intended deployment, edition, and component.

## Effect

“Default Authentication Method” determines the authentication entry used first when a user opens the sign-in page. Only an enabled, fully configured method can be selected as default. Test the new method before switching, and do not directly disable the current default method.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Configure and test the target method under “User Integration > Sign-in Authentication.”
2. Confirm that the method is enabled, a test account can sign in, and the correct role and space access are assigned.
3. Select the target under “Default Authentication Method.”
4. Open a new user sign-in page and confirm that it displays or prioritizes the expected authentication entry.
5. Verify that other enabled methods remain visible as designed. The current sign-in page determines their exact entries.
6. To disable the original method, first confirm that it is no longer the default, assess affected users, and then proceed.

## Recovery boundary

If the target method is absent from the list, check that it is enabled, required configuration is complete, and the current edition and License support it. If users cannot sign in after switching, immediately record the failed method and visible error and ask an administrator to restore the previous setting through the approved rollback process.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

A newly opened user sign-in page prioritizes the selected authentication method, and a regular test user can authenticate. Availability and entry behavior of other enabled methods depend on current configuration.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. If a default cannot be selected, the current default cannot be disabled, or switching affects many users, ask the product administrator to schedule a change window and notify users. Provide the product version, before-and-after method names, test result, and redacted visible error.

Keep the scope explicit: a user account, group, role, space, policy, and storage allocation are distinct objects. A change or entitlement in one scope must not be assumed for another.

