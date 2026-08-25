---
id: RSKB-START-006
title: Identify the deployed Raysync version
product: raysync
components:
- user-portal
domain: getting-started
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
- Where can I find the version number for my Raysync deployment?
- How do I compare the portal build with the desktop client version?
- What version details should I give support when a feature is missing?
keywords:
- version number
- About Raysync
- client version
- build
- How can I identify which Raysync version I am using?
- unavailable client
- About unavailable
- unknown version
legacy_ids:
- FAQ-VERSION-001
safety_tags:
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-001 | How can I identify which Raysync version I am using?
  evidence_type: generated-faq
- file: raysync-user-faq/12-version-differences.md
  section: FAQ-VERSION-012 | How do I identify the Raysync version when the client or About screen is unavailable?
  evidence_type: generated-faq
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Identify the deployed Raysync version

## Short answer

Use this standard procedure:

1. In the desktop client, right-click the client and select **About**. Record the displayed client version.
2. If support needs more detail, run **Error Detection** and record both the client version number and program version number shown there.
3. Ask the administrator for the deployed server version. The client version does not prove the server version.
4. Match the confirmed server version to the dated release history before following version-specific navigation or feature instructions.

## Version differences

The available user guide documents **About** and **Error Detection** for the desktop client. Server releases and their dates are listed separately in the release history. This distinction matters at boundaries such as 8.1.8.0 for administrator navigation, 8.1.8.6 for user two-factor authentication, and 8.1.8.7 for the redesigned peer-to-peer transfer page.

## Important notes

Record the full displayed value rather than rounding it to "8.1.8." Do not infer a version from a documentation filename, a screenshot, or one visible feature. If **About** is unavailable because the client cannot be opened, use the fallback in FAQ-VERSION-012.

## Related documented boundaries

- **How do I identify the Raysync version when the client or About screen is unavailable?:** If the client is unavailable or its **About** screen cannot be opened, do not infer the version from the interface. If **Error Detection** can still run, save its report and record the client version and program version values it displays. If it cannot run, record the exact error or detection message, operating system, browser, and visible control names for support.
