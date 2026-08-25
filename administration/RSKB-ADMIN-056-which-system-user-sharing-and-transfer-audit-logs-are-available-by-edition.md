---
id: RSKB-ADMIN-056
title: Which system-user sharing and transfer audit logs are available by edition?
product: raysync
components:
- admin-portal
- file-service
domain: administration
access_level: support
audience:
- administrator
- support-engineer
locale: en
applicable_versions:
  from: null
  to: null
version_status: uncertain
status: active
question_variants:
- Which audit trails cover system changes, logins, sharing, group transfers, and transmission
  activity?
- Can Cloud or Multiple Spaces forward transfer and operation records through Syslog?
- Which editions can collect server logs as well as display real-time transfer records?
keywords:
- system audit log
- user login history
- sharing audit
- transfer record
- Syslog forwarding
- server log collection
legacy_ids:
- RS-FEAT-259
- RS-FEAT-258
- RS-FEAT-255
- RS-FEAT-257
- RS-FEAT-261
- RS-FEAT-262
- RS-FEAT-260
- RS-FEAT-256
safety_tags:
- sensitive-diagnostics
- authorization
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-259 | Administrator operation behavior log
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-258 | File sharing data log
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-255 | System management log
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-257 | User login log
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-261 | Transmission logs and operation logs support Syslog integration
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-262 | Collect server logs
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-260 | Real-time transmission monitoring and transmission log
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-256 | Group file transfer log
  evidence_type: feature-matrix
verification:
  state: partially_verified
  version: undated-source
  date: '2026-08-14'
  verified_by: documentation-review
---

# Which system-user sharing and transfer audit logs are available by edition?

## Short answer

The supplied feature matrix documents the following exact availability:

- Administrator operation behavior log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- File sharing data log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- System management log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- User login log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Transmission logs and operation logs support Syslog integration: SMB: Supported; Enterprise: Supported; Cloud: Not supported; Multiple Spaces: Not supported
- Collect server logs: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported
- Real-time transmission monitoring and transmission log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- Group file transfer log: SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported

## Symptoms

An administrator needs to determine whether the deployed product tier includes the named capability, or observed availability differs from the supplied matrix.

## Checks

Confirm the exact product edition and deployed version without changing production state. Read each edition cell literally: **Supported** is explicit support, **Not supported** is explicit exclusion, and a blank cell is unspecified rather than unsupported.

## Interpretation

| Capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Administrator operation log | Supported | Supported | Supported | Supported |
| File-sharing data log | Supported | Supported | Supported | Supported |
| System-management log | Supported | Supported | Supported | Supported |
| User-login log | Supported | Supported | Supported | Supported |
| Syslog integration for transmission and operation logs | Supported | Supported | Not supported | Not supported |
| Server log collection | Supported | Supported | Supported | Not supported |
| Real-time transmission monitoring and log | Supported | Supported | Supported | Supported |
| Group file-transfer log | Supported | Supported | Supported | Supported |

The source references preserve each canonical feature identifier and matrix anchor. Row-level milestones record appearance or change only; rows without one retain uncertain version applicability.

## Backup or recovery boundary

No backup or recovery operation is authorized. Preserve the observed edition, version, and current configuration, and do not alter production to make it match the matrix.

## Corrective action

This article is explanatory and does not authorize a UI, command, or state change. The responsible product owner may compare entitlement evidence and open a version-and-edition verification request.

## Verification

Verify the exact edition cell for every required capability and record any mismatch as an unresolved version or entitlement question; feature presence alone does not establish support for a different edition.

## Evidence to collect

Collect only the product version, edition, capability name, and observed availability. Do not include credentials, private addresses, customer data, or full logs.

## Escalation

Escalate to Raysync support when the deployed version and edition are known but behavior differs from the exact matrix entry. Keep any source milestone separate from the requested current-support decision.
