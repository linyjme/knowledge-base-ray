---
id: RSKB-ADMIN-057
title: Reset a forgotten Raysync administrator password
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
- How do I reset the admin password when it has been forgotten?
- Where is AdminUnlockTool used to reset the administrator account?
- Can Forget Password on the user portal reset the admin account?
keywords:
- admin password
- reset administrator password
- AdminUnlockTool
- AdminUnlockTool.exe
- forgotten admin password
- admin account
legacy_ids: []
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles:
- RSKB-ADMIN-056
- RSKB-START-003
source_refs:
- file: administration/RSKB-ADMIN-057-reset-a-forgotten-administrator-password.md
  section: Reset a forgotten Raysync administrator password
  evidence_type: product-confirmation
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-09-22'
  verified_by: product-confirmation
---

# Reset a forgotten Raysync administrator password

## Short answer

Reset a forgotten **admin** account password on the machine where the Raysync service is deployed. Find **AdminUnlockTool** in that installation and follow the operations it presents. On a Windows deployment, the program is the binary **AdminUnlockTool.exe**. This applies only when the admin password has been forgotten and the admin account password must be reset.

## Steps

1. Go to the server where the Raysync service is installed. Do this on that machine. The user portal **Forget Password** page does not reset the admin account.
2. Find **AdminUnlockTool** in the Raysync installation.
3. On Windows, run **AdminUnlockTool.exe**. On other deployments, run the **AdminUnlockTool** script shipped with that installation.
4. Follow the operations shown by the tool to reset the admin account password.
5. Sign in to the admin console at `http://[server-IP]:9090/admin` with the admin account and the new password.

## Important notes

This tool resets the **admin** account after its password has been forgotten. It is separate from end-user password recovery.

**Forget Password** on the user portal sends an email verification code for an end-user account. That flow does not reset a forgotten administrator password, and it does not replace **AdminUnlockTool**.
