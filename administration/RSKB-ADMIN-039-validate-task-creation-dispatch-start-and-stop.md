---
id: RSKB-ADMIN-039
title: Validate task creation dispatch start and stop
product: raysync
components: [client-manager, file-service, node-scheduler]
domain: administration
access_level: internal
audience: [administrator, internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which controller observation follows accepted start?
- How is execution correlated with final result?
- What shows the job actually ran and produced a destination?
keywords: [controller accepted start, execution, job ran produced, request, worker result]
legacy_ids: []
safety_tags: [authorization, sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-ADMIN-033, RSKB-TROUBLE-010]
source_refs:
- {file: source_file/task-creation-acceptance.md, section: Minimum acceptance after task creation, evidence_type: technical-boundary-document}
- {file: source_file/task-dispatch-start-stop.md, section: 'Task distribution, start and stop', evidence_type: technical-boundary-document}
- {file: source_file/task-not-dispatched.md, section: 'What to do if the task is not sent?', evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# Validate task creation dispatch start and stop

## Short answer

Acceptance is complete only after the same test crosses control, execution, and result surfaces: request accepted, task created, worker registered, dispatched, running or stopped as intended, terminal state recorded, and target independently verified.

## Terminology and boundaries

**Accepted start** is control acknowledgement; **execution** is worker activity; **terminal** is the final task state. **Output** inspection supplies **target proof**. The sequence defines an evidence chain for controlled validation and does not authorize an operation by itself.

## Preconditions

An authorized operator must confirm the exact target node and task, direction, source and destination summaries, expected action, current state, permissions, and a minimum reversible test scope. Save the pre-action task and target inventory.

## Recovery boundary

Keep the original task evidence and same-name policy. Do not delete a task record, overwrite target data, or issue repeated start or stop requests until the previous request's result is known.

## Controlled action

Confirm the exact target and effect. Submit one start, stop, or dispatch action; record its acceptance time; then wait for a node return and subsequent state transition before deciding on another action.

## Verification

Correlate request, task, worker, progress, terminal, failed-object, and target evidence. A task ID or interface success message is not completion proof. This internal procedure is not a supported public contract and does not authorize undocumented task control.
