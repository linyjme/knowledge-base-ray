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
- Where is AdminUnlockTool used to reset the administrator account on Linux?
- Where is AdminUnlockTool.exe used to reset the administrator account on Windows?
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

Reset a forgotten **admin** account password on the machine where the Raysync service is deployed, using the **AdminUnlockTool** binary shipped with that installation. On Linux the binary is **AdminUnlockTool**. On Windows the binary is **AdminUnlockTool.exe**. Follow the operations the program presents. This applies only when the admin password has been forgotten and the admin account password must be reset.

## Steps

1. Go to the server where the Raysync service is installed. Do this on that machine. The user portal **Forget Password** page does not reset the admin account.
2. Find the unlock binary in the Raysync installation on that server.
3. On Linux, run the binary **AdminUnlockTool**. On Windows, run the binary **AdminUnlockTool.exe**.
4. Follow the operations shown by the tool to reset the admin account password.
5. Sign in to the admin console at `http://[server-IP]:9090/admin` with the admin account and the new password.

## Important notes

This tool resets the **admin** account after its password has been forgotten. It is separate from end-user password recovery.

**Forget Password** on the user portal sends an email verification code for an end-user account. That flow does not reset a forgotten administrator password, and it does not replace **AdminUnlockTool**.
