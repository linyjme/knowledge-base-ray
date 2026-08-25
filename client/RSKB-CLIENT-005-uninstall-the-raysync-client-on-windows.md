---
id: RSKB-CLIENT-005
title: Uninstall the Raysync client on Windows
product: raysync
components:
- desktop-client
domain: client
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- How do I remove the Raysync client from a Windows computer?
- Where is the uninstall entry if the client is still listed in Control Panel?
- Why does Raysync remain installed after I close the desktop application?
keywords:
- uninstall
- Windows Control Panel
- uninstall.exe
- remove client
- How do I uninstall the Raysync client on Windows?
- client
- Raysync
legacy_ids:
- FAQ-CLIENT-011
safety_tags:
- authorization
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-011 | How do I uninstall the Raysync client on Windows?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Uninstall the Raysync client on Windows

## Short answer

Use Windows **Control Panel > Programs > Programs and Features**, select the Raysync client, and uninstall it. Alternatively, open the client installation directory and run `uninstall.exe` as administrator.

## Steps

Before starting, use a Windows account authorized to uninstall software. Let active client transfers finish, or pause or stop them under your organization's approved transfer procedure. The exact target is the selected Raysync client installation on the current Windows computer.

Before confirming removal, confirm that the selected program entry or installation directory belongs to the Raysync client. The documentation defines removal of that client installation, but it does not specify whether downloaded files, settings, or cache are removed. Do not infer a broader cleanup effect.

Method 1:

1. Open **Control Panel > Programs > Programs and Features**.
2. Select the Raysync client.
3. Right-click and choose uninstall.

Method 2:

1. Right-click the desktop Raysync icon and select **Open file location**.
2. Right-click `uninstall.exe` and select **Run as administrator**.
3. Confirm removal.

## Recovery boundary

There is no documented undo or rollback for uninstalling the client. Restoring the application requires reinstalling it with an approved installer. The source does not promise that reinstalling restores prior settings or files, so preserve anything required by your organization's policy before removal.

## Verify the result

Refresh **Programs and Features** and verify that the selected Raysync client entry is no longer listed. If the entry remains or the removal reports an error, stop and ask an authorized administrator to review the installation rather than deleting files manually.

## Version differences

No version-specific uninstall change is documented.

## Important notes

These are Windows procedures. The available source does not provide macOS- or Linux-specific uninstall instructions. Exiting the client only closes it; it does not uninstall the software.
