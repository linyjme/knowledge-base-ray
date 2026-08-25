---
id: RSKB-P2P-009
title: Can administrators enable or disable P2P for individual users?
product: raysync
components:
- admin-portal
- desktop-client
domain: p2p
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
- Can I turn off P2P for one user without changing anyone else?
- Is per-user P2P control available in SMB, Enterprise, Cloud, and Multiple Spaces?
- Where should an administrator stop if the per-user P2P setting is not visible?
keywords:
- administrators enable
- or disable
- P2P for
- individual users
legacy_ids:
- RS-FEAT-144
safety_tags:
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-144 | Specify to enable/disable the p2p function for users
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Can administrators enable or disable P2P for individual users?

## Short answer

Yes. The supplied feature matrix explicitly documents per-user P2P enablement and disablement as supported in SMB, Enterprise, Cloud, and Multiple Spaces. It does not document the control's navigation path, so use only a reviewed per-user control that is visible in the deployed admin interface; if that control is absent, stop and verify the version and edition with Raysync support.

## Prerequisites

This article interprets the supplied feature-matrix entry for administrators. A source milestone records an appearance or change and does not establish the minimum supported version of the complete capability.

Only an authorized administrator may make this change. Use organization-approved values and confirm that the exact target is **administrators enable or disable P2P for individual users** in the intended deployment, edition, and component.

## Effect

The setting enables or disables P2P for the exact user selected by the administrator. It does not grant permission to change another user, a group, a role, a space, or stored content.

The change affects only the confirmed target and documented scope. It must not be treated as authorization to alter a different account, rule, service, license, user, or external system.

## Confirmation

Before execution, record the current state and confirm the exact target, intended effect, affected users, maintenance window where relevant, and a valid post-change check. Never copy credentials, activation codes, verification codes, or private addresses into documentation or support notes.

## Procedure

1. Confirm the exact user account, the intended enabled or disabled state, and the administrator's authority to change that account.
2. Open the reviewed per-user P2P control provided by the deployed admin interface. If the per-user control is not present, stop; do not substitute a group-wide, role-wide, space-wide, or global setting.
3. Record the user's current P2P state, select the intended state for that exact user, and confirm the target before saving.
4. Save once and wait for the interface to display the result. Do not repeat the change while its status is unknown.

## Documented evidence

- Knowledge base ID: RS-FEAT-144
- Capability domain: User Management
- Original source text: Specify to enable/disable the p2p function for users
- Edition availability: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Explicitly supported editions: SMB, Enterprise, Cloud, Multiple Spaces
- Source version note: 6.8.8.0
- Source location: Raysync Feature list.xlsx / English-New / row 144

## Recovery boundary

If the deployed edition or behavior differs, stop and verify the exact product version and edition with Raysync support. Restore the recorded prior state only through the same reviewed per-user control. Enabling or disabling P2P does not itself delete transferred or stored content; content recovery is a separate scope.

If the result differs from the confirmed effect, stop. Restore the recorded prior values only when the interface and external provider support that rollback. A sent message, deleted rule, restarted service, synchronized identity, or consumed activation operation cannot be automatically recalled; use the documented product or provider recovery path.

## Verification

Confirm that the exact user's P2P state matches the intended value and that other users remain unchanged. If the status is ambiguous or a broader scope changed, stop and restore the recorded prior value when the reviewed control supports it.

Verify the exact target after the operation and retain only a non-sensitive result, time, and visible status. Escalate with the product version, edition, component, and observed result; do not include credentials or private data.

A blank edition cell is **unspecified**. It must not be interpreted as unsupported or as proof of support. Any source version note is a feature appearance or change milestone, not the minimum version of this complete article.
