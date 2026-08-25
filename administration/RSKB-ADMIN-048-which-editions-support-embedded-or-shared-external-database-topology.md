---
id: RSKB-ADMIN-048
title: Which editions support embedded or shared external database topology?
product: raysync
components: [admin-portal]
domain: administration
access_level: internal
audience: [administrator, internal-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which packages cover several servers and MySQL?
- How are balanced servers tied to an external store?
- Why is the shared database pattern qualified by edition?
keywords: [packages several servers mysql, balanced external store, shared database, embedded topology]
legacy_ids: [RS-FEAT-183, RS-FEAT-184]
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-053]
source_refs:
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-183 | Server built-in small database (Sqlite)', evidence_type: feature-matrix}
- {file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md, section: 'RS-FEAT-184 | Connection with external database (MySQL), so that multiple Raysync servers share the database in load balancing mode', evidence_type: feature-matrix}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Which editions support embedded or shared external database topology?

## Short answer

The matrix lists an embedded database for every edition. It lists an external MySQL database shared by multiple load-balanced servers for Enterprise, Cloud, and Multiple Spaces, but not SMB.

## Terminology and boundaries

**Multi server** and **load balanced** describe server topology. **External shared MySQL** identifies the database pattern, and **store** is only a concise alias for that shared database. A **tier** is the edition evidence column; it must be qualified before any topology is treated as supported.

## Edition evidence

| Topology capability | SMB | Enterprise | Cloud | Multiple Spaces |
| --- | --- | --- | --- | --- |
| Embedded server database | Supported | Supported | Supported | Supported |
| Shared external MySQL for load balancing | Not supported | Supported | Supported | Supported |

These rows do not specify current database versions, migration paths, durability, or operational procedures. Their undated evidence cannot be promoted to a current support matrix without validation.

## Publication boundary

This internal topology summary is not a supported public contract. It does not authorize database edits, migrations, connection changes, or production topology changes.
