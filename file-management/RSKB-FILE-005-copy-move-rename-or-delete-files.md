---
id: RSKB-FILE-005
title: How do I copy, move, rename, or delete files?
product: raysync
components: [user-portal]
domain: file-management
access_level: public
audience: [end-user]
locale: en
applicable_versions: {from: "8.1.8.7", to: null}
version_status: current
status: active
question_variants:
  - How can I move or copy content in Raysync?
  - Where do I rename a file in the portal?
  - What happens when I delete a Raysync file?
keywords: [copy file, move file, rename file, delete file, file operations]
legacy_ids: [FAQ-FILE-005]
safety_tags: [authorization, destructive-operation]
supersedes: []
superseded_by: []
related_articles: [RSKB-FILE-004, RSKB-FILE-011, RSKB-FILE-012, RSKB-FILE-015]
source_refs:
  - file: raysync-user-faq/03-file-upload-download-and-management.md
    section: FAQ-FILE-005 | How do I copy, move, rename, or delete files?
    evidence_type: generated-faq
  - file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
    section: RS-FEAT-012 | Support new folder, copy, move, rename, delete, Unzip
    evidence_type: feature-matrix
verification: {state: verified, version: "8.1.8.7", date: "2026-08-13", verified_by: documentation-review}
---

# How do I copy, move, rename, or delete files?

## Short answer

Select the file or folder and choose the required toolbar or operation-menu action. **Move** asks for a destination and uses **Move here**; **Copy** asks for a destination and uses **Copy to this**; **Rename** makes the name editable; **Delete** follows the server's deletion policy.

## Authorization and preconditions

Use only an account permitted to change the selected personal or group content. Confirm the exact item, its current location, any destination, and the server deletion policy before choosing an operation.

## Exact target and effect

Copy retains the source and creates another item; move changes its location; rename changes its name; delete removes the selected item under the server policy. Confirm one exact action and destination rather than treating these effects as interchangeable.

## Confirmation

Recheck the selected item, destination or new name, same-name behavior, and affected group library before submitting. For delete, confirm whether the policy retains the item in a recycle bin or removes it directly.

## Recovery boundary

Preserve a backup or other approved recovery path before move, overwrite, or direct delete. A direct deletion or content removed from an emptied recycle bin cannot be recovered through the documented recycle-bin workflow.

## Post-action verification

Refresh the original and destination locations. Verify that copy left the source, move changed only the intended location, rename produced the intended name, or delete affected only the selected item and produced the expected retention result.

## Understand the result

- **Copy** keeps the source and creates another item.
- **Move** changes the item's location.
- **Rename** changes its name. A virtual directory cannot be renamed from the client side.
- **Delete** may send the item to a recycle bin or remove it directly, depending on administrator policy.

Confirm the selection before deleting. A direct delete or an emptied recycle bin permanently removes content. Overwrite is different: it replaces target-file content during transfer. The feature matrix lists these core file-management operations for SMB, Enterprise, Cloud, and Multiple Spaces editions.
