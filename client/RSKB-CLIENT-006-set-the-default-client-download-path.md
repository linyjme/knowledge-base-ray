---
id: RSKB-CLIENT-006
title: Set the default client download path
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
- Where can I choose the folder used for client downloads?
- How do I change the save location before starting another transfer?
- Why are downloaded files going to the previous desktop path?
keywords:
- download path
- settings
- save location
- open file directory
- How do I set the default download path?
- client
- Raysync
legacy_ids:
- FAQ-CLIENT-012
safety_tags: []
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-012 | How do I set the default download path?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Set the default client download path

## Short answer

Open the client transfer settings and set **Download path** to the folder you want to use by default. Raysync also supports manually selecting a path when starting a download.

After a client download finishes, use **Open File Directory** in the browser plug-in or transfer list to locate the downloaded file.

## Version differences

The documented setting is consistent across the user client and cloud guides. No release-specific change is identified.

## Important notes

The default path applies to client downloads. A download performed with the web option appears in the browser's downloads and follows browser download behavior. Peer-to-peer transfer has a separate receive-file save path in the client settings.
