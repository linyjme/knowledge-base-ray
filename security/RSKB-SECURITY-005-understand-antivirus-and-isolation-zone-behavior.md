---
id: RSKB-SECURITY-005
title: Understand antivirus and Isolation Zone behavior
product: raysync
components:
- user-portal
- file-service
domain: security
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
- Why did an uploaded file move into the Isolation Zone?
- How can I distinguish antivirus isolation from a sensitive-word match?
- What details identify the reason a file was isolated?
keywords:
- antivirus
- ClamAV
- infected file
- upload
- isolation zone
- What happens when Raysync antivirus detects an uploaded file?
- Antivirus during file transfer
- quarantined file
legacy_ids:
- FAQ-SECURITY-011
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-011 | What happens when Raysync antivirus detects an uploaded file?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-111 | Antivirus during file transfer
  evidence_type: feature-matrix
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-012 | Why did a file disappear from my normal files and appear in the Isolation Zone?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Understand antivirus and Isolation Zone behavior

## Short answer

When antivirus is enabled, Raysync scans uploaded files with ClamAV. A file detected as infected is moved to the Isolation Zone rather than remaining in the normal file area. This behavior depends on administrator configuration and a server restart after antivirus is enabled.

## Isolation causes

The two documented causes are different:

- **Antivirus isolation:** after upload, ClamAV detects an infected file and Raysync moves it to the Isolation Zone.
- **Sensitive-word isolation:** during transfer, a configured term matches the file name or text-file content and Raysync places the file in the isolation area.

The same Isolation Zone can contain files isolated for either cause. A file's absence from normal storage does not identify the cause by itself; use the displayed isolation details rather than assuming every isolated file contains a virus.

## Version differences

The end-user outcome is the same in the legacy and 8.1.8.0 and later security guides: an infected uploaded file is moved from the normal file area to the Isolation Zone. The available documentation does not identify a different end-user response at the version 8.1.8.0 boundary.

## Important notes

Do not repeatedly upload a file identified as infected or try to distribute it another way. Use the user portal’s Isolation Zone information if it is available to your account, and contact the administrator for handling under organizational policy. Virus-definition updates and antivirus enablement are administrator responsibilities.

The Isolation Zone view can show the detected virus type and the time the file was isolated.

## Related documented boundaries

- **Antivirus during file transfer:** SMB: Not supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Supported
- **Why did a file disappear from normal files?:** Review the displayed isolation reason to distinguish an antivirus detection from a configured sensitive-word match.
