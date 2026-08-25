---
id: RSKB-TRANSFER-008
title: How many transfers or files can run at the same time?
product: raysync
components: [desktop-client]
domain: transfer
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - Where are parallel upload and download task counts limited?
  - How is the number of simultaneous files in one job chosen?
  - Is a long queue the same as active concurrency?
keywords: ["parallel tasks", "parallel files", "transfer concurrency", "long task queue"]
legacy_ids: ["FAQ-TRANSFER-008", "RS-FEAT-043", "RS-FEAT-045", "RS-FEAT-052"]
safety_tags: ["authorization"]
supersedes: []
superseded_by: []
related_articles: ["RSKB-TRANSFER-007", "RSKB-TRANSFER-009", "RSKB-TRANSFER-023"]
source_refs:
  - file: raysync-user-faq/04-transfer-tasks.md
    section: FAQ-TRANSFER-008 | How many transfers or files can run at the same time?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-043 | Supports specifying the maximum number of upload and download tasks
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-045 | Supports specify the number of files in parallel for a task
    evidence_type: feature-matrix
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-052 | Support for long task queues.
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How many transfers or files can run at the same time?

## Short answer

Client transfer settings allow up to 10 parallel upload tasks and up to 10 parallel download tasks. You can also set the number of files per task; the default file-parallel value is **Automatic**, calculated from the number of CPU cores.

A long queue is not proof that every item runs concurrently. These configured limits and supported capabilities are **not guaranteed throughput** and do not override server limits or available network capacity.

Maximum tasks, files in parallel, and long queues are **Supported in SMB, Enterprise, Cloud, and Multiple Spaces.**
