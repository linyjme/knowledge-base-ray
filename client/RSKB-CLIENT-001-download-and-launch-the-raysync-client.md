---
id: RSKB-CLIENT-001
title: Download and launch the Raysync client
product: raysync
components:
- user-portal
- desktop-client
- browser-plugin
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
- How do I launch the downloaded desktop client from the user portal?
- Why does Transfer List still say the browser plug-in is disconnected?
- Where can I get the approved client installer before starting a transfer?
keywords:
- start client
- Transfer List
- raysync-watch.exe
- client not connected
- How do I start the Raysync client from the user portal?
- client download
- installer
- desktop client
legacy_ids:
- FAQ-CLIENT-001
safety_tags:
- credentials
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-006 | How do I start the Raysync client from the user portal?
  evidence_type: generated-faq
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-001 | How do I download the Raysync client?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Download and launch the Raysync client

## Short answer

Sign in to the user portal. If the client is not installed or started, select **Client Download**, choose the package for your platform and preferred client type, and download it. Raysync offers a desktop client for high-speed transfers without keeping the web page open and a browser plug-in for accelerated transfers initiated from the user portal.

## Steps

1. Open the Raysync user portal.
2. Select **Client Download** when prompted or from the portal's client controls.
3. Choose the desktop client or browser plug-in and the package for your operating system.
4. Run the downloaded installer.

## Version differences

The Linux desktop client became available in version 8.1.8.2. The release history does not identify a different download procedure for later releases.

## Important notes

Use the package presented by your own Raysync server. A deployment may customize its client download URL, and an incorrect customized URL can affect normal startup from the user portal.

## Related documented boundaries

- **How do I start the Raysync client from the user portal?:** On Windows, select **Transfer List** in the user portal. If the client is not connected, choose **Start** in the prompt, approve the browser request to open `raysync-watch.exe`, and wait for startup to finish. The same **Start** action is available when the portal displays a client-not-connected message.
