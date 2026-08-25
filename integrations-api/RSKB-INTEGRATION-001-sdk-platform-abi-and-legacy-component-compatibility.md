---
id: RSKB-INTEGRATION-001
title: SDK platform ABI and legacy-component compatibility
product: raysync
components: [sdk, cli, client-manager, file-service, typhoonv6]
domain: integrations-api
access_level: internal
audience: [developer, internal-engineer, support-engineer]
locale: en
applicable_versions: {from: null, to: null}
version_status: uncertain
status: active
question_variants:
- Which old node and manager evidence belongs in an upgrade review?
- How are obsolete binary and controller handshake results qualified?
- Which protocol, ABI, package, and platform checks establish qualification?
- Is an old-node upgrade tied to the manager boundary?
- Does the obsolete binary use a controller handshake?
- Why are old node, manager connection, and upgrade approval separate compatibility signals?
- Why do obsolete binary, controller handshake, and new release certification require separate qualification evidence?
keywords: [old node manager upgrade approval, obsolete binary controller handshake new release, protocol qualification, abi package platform]
legacy_ids: []
safety_tags: [sensitive-diagnostics]
supersedes: []
superseded_by: []
related_articles: [RSKB-INTEGRATION-002, RSKB-ADMIN-034]
source_refs:
- {file: source_file/legacy-components.md, section: Node scheduling history component compatibility prompt, evidence_type: technical-boundary-document}
- {file: source_file/boundaries.md, section: Compatibility boundaries, evidence_type: technical-boundary-document}
- {file: source_file/platform-and-version.md, section: Platform judgment, evidence_type: technical-boundary-document}
- {file: source_file/abi-version-compatibility.md, section: SDK ABI and version compatibility boundaries, evidence_type: technical-boundary-document}
- {file: source_file/gui-headless.md, section: GUI and headless manager compatibility, evidence_type: technical-boundary-document}
verification: {state: partially_verified, version: undated-source, date: '2026-08-14', verified_by: documentation-review}
---

# SDK platform ABI and legacy-component compatibility

## Short answer

Compatibility requires the release package, ABI, local manager bridge, remote protocol, optional libraries, and target platform to agree. A process that starts or a legacy node that connects proves only an early stage.

## Terminology and boundaries

An **obsolete binary** or **legacy** component may complete a protocol **handshake** with a **controller**. That observation does not certify a **new release**; **upgrade certification** additionally covers package, platform, ABI, lifecycle, and transfer results. This is an internal compatibility boundary, not a public support promise.

## Compatibility surfaces

The C ABI includes exported symbols, calling convention, enumeration values, structure and callback layout, opaque-handle lifetime, string ownership, and release responsibilities. Manager-to-worker messages and remote file-protocol semantics are separate surfaces. GUI and headless managers may share orchestration while exposing different presentation or control entrances.

Historical agent or slave components are background evidence only. They are not mandatory layers in the current master model and must not be used to infer a current protocol. Build branches for an operating system or architecture do not prove that every release package supports that combination.

Use an isolated, recoverable test to compare package versions, compilation and linking, manager connection, authentication, directory query, one small transfer, task control, callback contents, final state, and target verification. Record only redacted results and keep untested combinations unknown.

## Publication boundary

This compatibility model is not a supported public contract. It does not authorize mixing packages, replacing internal components, changing undisclosed settings, or declaring any legacy operating system currently supported.
