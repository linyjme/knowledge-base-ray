---
id: RSKB-CLIENT-007
title: Use the client transfer list
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
- Where can I see progress and speed for active client transfers?
- How do I pause and resume a task from the desktop transfer list?
- Which task filter helps me find a completed client transfer?
keywords:
- client transfer list
- task progress
- transfer speed
- pause and resume
- task filters
- task priority
legacy_ids:
- FAQ-CLIENT-013
safety_tags:
- destructive-operation
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/02-client-installation-and-settings.md
  section: FAQ-CLIENT-013 | How do I open and use the client transfer list?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-025 | Support for task sorting and filtering by creation time.
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-021 | Sorting client task priority
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Use the client transfer list

## Short answer

Select **Transfer List** in the upper-right corner of the user portal, select the client icon, or right-click the client and choose **Transfer List**. The list includes general transfer tasks, sync tasks, and peer-to-peer tasks.

Use the list to operate on client tasks: pause or start selected tasks, batch-select with `Ctrl` or `Ctrl+A`, retry when available, pin a task, open its local directory, or open its details.

## Undefined delete-action boundary

The source lists a task-delete control but does not define whether deleting an active client task stops the transfer, removes its record, or affects source files or destination files. Because the exact target, effect, and recovery boundary are unknown, this article does not recommend the delete action.

Do not use task deletion for an active or important transfer based on this article. Confirm the exact effect for the deployed version with an administrator or Raysync support before deciding whether that action is appropriate.

## Version differences

Version 8.1.8.6 adds client task sorting and creation-time filtering. Version 8.1.8.7 adds filtering by task name and task status.

## Important notes

Use the client list only for client-task operations; web progress is shown elsewhere.

## Related documented boundaries

- **Support for task sorting and filtering by creation time.:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported The source records 8.1.8.6 as an appearance or change milestone, not as proof of the onset of support.
- **Sorting client task priority:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
