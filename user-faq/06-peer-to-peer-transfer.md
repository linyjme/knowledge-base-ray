### FAQ-P2P-001 | What is peer-to-peer transfer used for?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: Peer-to-peer transfer
- User intent: Understand P2P purpose
- Keywords: peer-to-peer transfer, direct transfer, server disk

#### Short answer

Peer-to-peer transfer moves files between two running Raysync clients. The data is not uploaded to the Raysync server's disk. Raysync detects the network path and, when possible, transfers directly between the sender and receiver; server infrastructure can provide connection or traffic relay services when needed.

The current page also lets trusted devices browse permitted remote files, send local files, or fetch remote files. These actions depend on permissions set by the remote device.

#### Version differences

Version 8.1.8.7 introduced a redesigned P2P page with **My Computer**, **Remote Computer**, device connection, and a **Transfer Center**. Versions before 8.1.8.6 use the documented older Send/Receive workflow. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

P2P still requires the Raysync service, open ports, an online client, and administrator configuration. “Peer-to-peer” does not mean that every network will achieve a direct path.

#### Sources

- `p2p.md` — introduction, “Page Overview,” and “Core Process”
- `client.md` — “Peer to peer tasks”
- `p2p-8186.md` — introduction
- `release.md` — “v8.1.8.7,” P2P page redesign

### FAQ-P2P-002 | What must be ready before I use peer-to-peer transfer?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: P2P prerequisites
- User intent: Prepare for P2P
- Keywords: prerequisites, online client, P2P service

#### Short answer

Both users must be logged in, both Raysync clients must be running, and both networks must be able to reach the configured service. The administrator must configure the P2P service address and required ports. For the workflow in version 8.1.8.7 and later, both devices enable P2P; the receiver shares a device ID and enables the permission needed for the intended action.

To send files, the receiver enables **Allow receive files from others**. To fetch remote files, the remote device enables **Allow others to fetch files**.

#### Version differences

The redesigned page requires client version 8.1.8.7 or higher. Versions before 8.1.8.6 use the documented Send/Receive pages. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

The end user cannot replace missing server configuration. If P2P is unavailable even with both clients online, contact the administrator to verify the service address, ports, and account permission.

#### Sources

- `p2p.md` — “Enable Peer to Peer transfer,” prerequisites
- `p2p-task.md` — “Prerequisites” and “Before You Start”
- `configuration.md` — “Peer-to-Peer transfer”
- `v8180-transfer.md` — “Peer-to-peer”

### FAQ-P2P-003 | Which ports are required for peer-to-peer transfer?

- Product: Raysync
- Audience: End user
- Applies to: Core P2P ports as documented by the deployment guides; STUN and UDP/3478 from version 6.8.8.0
- Feature: P2P networking
- User intent: Confirm firewall prerequisites
- Keywords: TCP/3443, UDP/3478, UDP/32003, firewall

#### Short answer

The documented P2P ports are exactly:

- **TCP/3443** — TCP forwarding server monitor port for peer-to-peer transfer.
- **UDP/3478** — Raysync STUN server port for network detection and hole punching.
- **UDP/32003** — peer-to-peer transfer service.

For an on-premises service behind NAT, these ports also need appropriate router NAT mapping. For a public-cloud deployment, they must be allowed in the applicable security group as well as the host firewall.

#### Version differences

The deployment guides document **TCP/3443** and **UDP/32003** as core P2P service ports. STUN support and its **UDP/3478** port were added in version 6.8.8.0. Both the later guide for versions before 8.1.8.0 and the guide for version 8.1.8.0 and later list all three ports.

#### Important notes

Opening ports is an administrator or network-team task. Do not change corporate firewall or security-group rules without authorization.

#### Sources

- `firewall.md` — “On premise deployment” and “Cloud deployment”
- `p2p-task.md` — “Prerequisites”
- `configuration.md` — “Peer-to-Peer transfer”
- `v8180-transfer.md` — “Peer-to-Peer transfer”
- `release.md` — “v6.8.8.0,” STUN service

### FAQ-P2P-004 | How do I enable peer-to-peer transfer on my device?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: P2P enablement
- User intent: Turn on P2P
- Keywords: Enable P2P, user portal, desktop client

#### Short answer

Start and log in to the Raysync client, open **Peer to Peer** from the left menu, and turn on **Enable P2P** in the upper-right corner. The page then displays your device ID and local file list and allows connections to remote devices.

#### Version differences

This toggle and page layout apply to the redesigned interface in version 8.1.8.7 and later. In versions before 8.1.8.6, use the documented **Send** or **Receive** page; the receiver turns on **Allow to receive files** instead of using the redesigned page-level toggle. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

The administrator must already have configured the P2P service, and your account must be allowed to use it. Do not turn off P2P during a transfer because the connection may be interrupted.

#### Sources

- `p2p.md` — “Enable Peer to Peer transfer”
- `p2p-task.md` — “Quick Start - Version 8187+” and “Version Before 8186”
- `p2p-8186.md` — “Receive peer to peer files”
- `release.md` — “v8.1.8.7”

### FAQ-P2P-005 | Where do I find my P2P device ID, and can I change it?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: P2P device identity
- User intent: Share or refresh a device ID
- Keywords: device ID, copy ID, update ID

#### Short answer

In version 8.1.8.7 and later, enable P2P and locate **My Device ID** at the top of the P2P page. Select **Copy** to copy it for a trusted partner. Select **Update** to generate a new device ID.

In versions before 8.1.8.6, the documented Receive page also displays a device ID for the receiver to copy and send to the sender.

#### Version differences

The **Copy** and **Update** controls are documented for the redesigned page in version 8.1.8.7 and later. Versions before 8.1.8.6 use the device ID from the Receive page, and the older documentation also mentions an ID and key. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

After an ID update, the old ID may no longer work, so notify intended partners. Do not publish the device ID to unauthorized people; it is used to initiate connection requests.

#### Sources

- `p2p.md` — “View, Refresh, and Copy Device ID”
- `p2p-task.md` — legacy Receive steps
- `p2p-8186.md` — introduction

### FAQ-P2P-006 | How do I add and connect to a remote device?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: Remote device connection
- User intent: Connect a P2P partner
- Keywords: remote device, connect device, device ID, email

#### Short answer

Connect from the **Remote Computer** area by using the other device's ID or email.

#### Prerequisites

- Both devices are online with P2P enabled.
- You have the remote device ID or email.
- The remote device has enabled the permission required for the intended transfer.

#### Steps

1. In **Remote Computer**, select **Connect Device**.
2. Enter the remote device ID or email and, optionally, a device name.
3. Select **Connect**.
4. After connection, select the device from the device list and confirm that the remote area shows only the content its permissions allow.

#### Version differences

This persistent remote-device workflow belongs to the redesigned page in version 8.1.8.7 and later. Versions before 8.1.8.6 ask for the receiver's ID or email directly while creating a send task. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Receiving files and browsing/fetching files are different permissions. A device can accept pushed files without exposing a browsable file list. If a known device is offline, wait until it is online before connecting.

#### Sources

- `p2p.md` — “Add a Remote Device” and “Connection Management”
- `p2p-task.md` — “Quick Start - Version 8187+”
- `p2p-8186.md` — “Send Peer to Peer transfer file”

### FAQ-P2P-007 | How do I send files to another device in 8.1.8.7 or later?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: P2P sending
- User intent: Send files
- Keywords: send, My Computer, Remote Computer, Transfer Center

#### Short answer

Select local content, choose the permitted remote destination, and create the send task.

#### Prerequisites

- Connect successfully to the receiving device.
- The receiver has enabled **Allow receive files from others**.
- The remote destination has enough storage space.

#### Steps

1. In **My Computer**, select the files or folders to send.
2. In **Remote Computer**, navigate to the destination path.
3. Select **Send**, or drag the selected items to the remote-computer area.
4. Monitor the task in **Transfer Center** or the client task list.

#### Version differences

This dual-pane workflow starts with the 8.1.8.7 P2P page redesign. Versions before 8.1.8.6 use a Send page where you enter the receiver's ID or email, select files, and start the transfer. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

The receiver must enable **Allow receive files from others** and have enough free storage. Keep both clients online for large transfers, and do not move or delete local source files while the transfer is active.

#### Sources

- `p2p.md` — “Send Files to remote device” and “View Task List”
- `p2p-task.md` — “Send Files to a Remote Device”
- `release.md` — “v8.1.8.7”

### FAQ-P2P-008 | How do I fetch files from a remote device?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: P2P fetching
- User intent: Fetch remote files
- Keywords: fetch files, remote file, local path

#### Short answer

Select permitted remote content and choose the local destination before creating the fetch task.

#### Prerequisites

- Connect successfully to the remote device.
- The remote device has enabled **Allow others to fetch files**.
- Your local destination has enough storage space.

#### Steps

1. In **Remote Computer**, select the files or folders to fetch.
2. In **My Computer**, navigate to the local destination.
3. Select **Receive** to create the fetch task, or drag the remote items into the local area.
4. Monitor the task in **Transfer Center**.

This is a pull operation: the remote device must enable **Allow others to fetch files**. It is different from passively accepting files that another device sends to you.

#### Version differences

Remote browsing and explicit fetching are documented for version 8.1.8.7 and later. Versions before 8.1.8.6 use a Receive page that prepares the device to accept sender-created tasks. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Choose a local destination with sufficient space. Access to view a remote file list does not by itself grant permission to fetch those files.

#### Sources

- `p2p.md` — “Receive Files from remote device” and P2P permission descriptions
- `p2p-task.md` — “Receive Files from a Remote Device”
- `p2p-8186.md` — “Receive peer to peer files”

### FAQ-P2P-009 | How do I allow other devices to send files to me?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: P2P receive permission
- User intent: Accept incoming files
- Keywords: allow receive files, incoming files, receive permission

#### Short answer

In version 8.1.8.7 and later, enable P2P and turn on **Allow receive files from others** in P2P settings. This permission is on by default when P2P is enabled. Set a safe receive path and share your device ID only with the intended sender.

In versions before 8.1.8.6, open **Receive** and enable **Allow to receive files**, then copy the displayed device ID to the sender.

#### Version differences

The current permission label belongs to version 8.1.8.7 and later. Versions before 8.1.8.6 use **Allow to receive files** on the Receive page or client. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Allowing incoming sends does not require you to expose a browsable file list. Store received files in a dedicated folder rather than a system or important-data directory.

#### Sources

- `p2p.md` — “P2P Permission Configuration”
- `p2p-task.md` — current and legacy quick starts
- `p2p-8186.md` — “Receive peer to peer files”

### FAQ-P2P-010 | How do I allow another device to browse and fetch my files?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.7 and later
- Feature: P2P file permissions
- User intent: Permit remote fetching
- Keywords: view file list, fetch files, remote browsing

#### Short answer

Enable **Allow others to view file list** so connected devices can browse files under your configured open path. Then enable **Allow others to fetch files** if they should be able to download those files. Viewing and fetching are separate permissions: browsing alone does not authorize download.

#### Version differences

These granular permissions are documented for the redesigned page in version 8.1.8.7 and later. The older Send/Receive documentation does not describe remote file browsing and fetch controls.

#### Important notes

**Security:** File-list browsing exposes file and folder names and the directory structure under the configured open path. Use a dedicated least-privilege path, inspect it for sensitive content before enabling access, and permit only trusted devices. Delete and rename are separate high-risk permissions and are not required for fetching. Connected devices must reconnect after a permission change.

#### Sources

- `p2p.md` — “P2P Permission Configuration” and “Receive Files from remote device”
- `release.md` — “v8.1.8.7,” P2P page redesign

### FAQ-P2P-011 | How do I stop receiving P2P files?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: P2P reception control
- User intent: Close incoming reception
- Keywords: stop receiving, disable P2P, allow receive files

#### Short answer

In version 8.1.8.7 and later, turn off **Allow receive files from others** when you no longer want pushed files. You can also turn off **Enable P2P** to close P2P on the device entirely. In versions before 8.1.8.6, clear **Allow to receive files** on the user portal's **Receive** page or turn off receiving in the Raysync client.

#### Version differences

The redesigned permission names apply to version 8.1.8.7 and later. Versions before 8.1.8.6 use the documented older receive control. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Do not disable P2P while an active transfer is running because it may interrupt the connection. Disabling incoming sends does not automatically disable remote browsing or fetching; turn off those permissions separately if they were enabled.

#### Sources

- `p2p.md` — “Enable Peer to Peer transfer” and “P2P Permission Configuration”
- `p2p-8186.md` — “Receive peer to peer files”

### FAQ-P2P-012 | Where are received P2P files saved?

- Product: Raysync
- Audience: End user
- Applies to: Documented for version 8.1.8.7 and later, and for versions before 8.1.8.6
- Feature: P2P receive path
- User intent: Find received files
- Keywords: receive path, save path, local destination

#### Short answer

In version 8.1.8.7 and later, use **Save path when receiving files** in P2P settings to choose the default destination for pushed files. For files you fetch yourself, navigate to the desired directory in **My Computer** before selecting **Receive** or dragging the remote items there. Versions before 8.1.8.6 document preparing the Receive page but do not specify a user-selectable save path.

#### Version differences

The dedicated receive-path setting and dual-pane destination selection are documented for version 8.1.8.7 and later. Versions before 8.1.8.6 do not specify a user-selectable path in the cited text. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Choose a directory with enough space and easy access. Do not use a system directory or an important working-data folder, because incoming names or remotely granted file operations could affect local content.

#### Sources

- `p2p.md` — “P2P Permission Configuration” and “Receive Files from remote device”
- `p2p-task.md` — “Receive Files from a Remote Device”
- `p2p-task.md` — “Version Before 8186,” Receive peer-to-peer files
- `p2p-8186.md` — “Receive peer to peer files”

### FAQ-P2P-013 | Can I create a P2P send task while the receiver is offline?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.8.8.1 through versions before 8.1.8.6; legacy workflow only
- Feature: Offline P2P tasks
- User intent: Queue a transfer for an offline receiver
- Keywords: receiver offline, ready for transfer, queued task

#### Short answer

In the documented pre-8.1.8.6 legacy workflow, yes. The sender can create a task while the receiver is offline. Its status is **Receiver offline, ready for transfer**, and the receiver automatically receives the file after coming online.

#### Version differences

Offline P2P tasks were added in version 6.8.8.1 and are explicitly described in `p2p-8186.md`, whose title limits that workflow to versions before 8.1.8.6. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support. The workflow in version 8.1.8.7 and later requires both devices to be online before connecting and does not document creating an offline task.

#### Important notes

An offline-ready task still depends on the receiver later starting the client and allowing reception. The cited sources do not provide extra recovery steps for an offline task that never starts.

#### Sources

- `p2p-8186.md` — “Receive peer to peer files,” transfer status description
- `p2p.md` — “Add a Remote Device,” prerequisites
- `p2p-task.md` — “Before You Start”
- `release.md` — “v6.8.8.1,” offline P2P tasks

### FAQ-P2P-014 | Can I schedule a P2P send task?

- Product: Raysync
- Audience: End user
- Applies to: Scheduled P2P from version 6.7.8.0; steps shown for version 8.1.8.7 and later
- Feature: Scheduled P2P sending
- User intent: Send later or repeatedly
- Keywords: scheduled sending, once, every, daily, weekly

#### Short answer

Configure a send task to run once or on a repeating schedule from the current P2P task settings.

#### Prerequisites

- Use the documented **My Computer** interface from version 8.1.8.7 and later for these steps.
- Connect the remote device and confirm that it can receive files.
- Both clients must be online and reachable at the scheduled time.

#### Steps

1. In **My Computer**, open the task transfer settings.
2. Enable scheduled sending and choose **Once**, **Every**, **Daily**, or **Weekly**.
3. Set the required date, time, interval, or weekday and save the settings.
4. Select the directory and choose **Send** to create the task.
5. Review scheduled task information in the client; the user portal does not show it.

#### Version differences

Scheduled P2P tasks were introduced in version 6.7.8.0. The **My Computer** settings and the **Once**, **Every**, **Daily**, and **Weekly** controls described here are from the interface in version 8.1.8.7 and later. For exact version 8.1.8.6, the supplied documentation does not specify this workflow; follow the visible interface or contact your administrator or Raysync support.

#### Important notes

Both clients must be online and the remote device reachable at the scheduled time. Avoid an excessively short **Every** interval because frequent tasks can affect computer and network performance. The adjacent **Move from source to target** option removes files from the source after transfer and must be evaluated separately.

#### Sources

- `p2p.md` — “Task Transfer Settings” and “View Task List”
- `release.md` — “v6.7.8.0,” P2P scheduled tasks
- `release.md` — “v8.1.8.7,” P2P page redesign

### FAQ-P2P-015 | How can I tell whether a P2P transfer is direct or relayed?

- Product: Raysync
- Audience: End user
- Applies to: Version 8.1.8.3 and later for logged connection type
- Feature: P2P connection type
- User intent: Understand the network path
- Keywords: direct connection, relay, transfer log, server traffic

#### Short answer

Raysync performs network detection and attempts a direct client-to-client path. If the network cannot establish that path, the configured P2P infrastructure can forward traffic. In either case, the documentation says the file data is not uploaded to server disk.

Connection type became available in P2P transfer logs in 8.1.8.3. Ordinary users can see task progress and details in the client; access to server transfer logs may require an administrator.

#### Version differences

P2P connection-type logging was added in 8.1.8.3. The 8.1.8.7 page redesign changes task presentation, not the underlying direct-path goal.

#### Important notes

Do not infer “direct” merely from a successful task. Network topology and NAT can require relay. The source does not provide an end-user control that forces a direct path.

#### Sources

- `client.md` — “Peer to peer tasks”
- `p2p.md` — introduction
- `firewall.md` — TCP forwarding and STUN port descriptions
- `release.md` — “v8.1.8.3,” P2P connection type in logs

### FAQ-P2P-016 | What does STUN do for P2P transfers?

- Product: Raysync
- Audience: End user
- Applies to: Version 6.8.8.0 and later
- Feature: STUN service
- User intent: Understand direct-connection assistance
- Keywords: STUN, UDP/3478, network detection, hole punching

#### Short answer

STUN is optional server-side configuration that detects the network between two devices and helps establish a direct connection. It improves the success rate of direct P2P connections. An administrator can configure a private STUN service or an open public one.

The configured STUN address can be one public IP address or domain name, and the documented default STUN port is **UDP/3478**.

#### Version differences

STUN service support was added in version 6.8.8.0. The later guide for versions before 8.1.8.0 and the guide for version 8.1.8.0 and later use the same STUN description and default **UDP/3478** port.

#### Important notes

STUN is not an end-user setting in the cited workflow. It assists connection establishment but does not guarantee a direct path through every NAT or firewall.

#### Sources

- `p2p-task.md` — “Stun Service”
- `configuration.md` — “Stun Service”
- `v8180-transfer.md` — “Stun Service”
- `firewall.md` — UDP/3478 description
- `release.md` — “v6.8.8.0,” STUN service

### FAQ-P2P-017 | Which P2P workflow should I use for my Raysync version?

- Product: Raysync
- Audience: End user
- Applies to: All documented versions
- Feature: Version-specific P2P workflow
- User intent: Choose the correct operational workflow
- Keywords: 8.1.8.7, 8.1.8.6, legacy P2P, workflow

#### Short answer

Check your deployed Raysync version, then choose the matching workflow:

1. For **version 8.1.8.7 and later**, open **Peer to Peer**, enable P2P, connect the remote device by ID or email, and send or fetch files between **My Computer** and **Remote Computer**. Monitor the result in **Transfer Center** and the client task list.
2. For **exact version 8.1.8.6**, match the controls visible in your deployed interface, or contact your administrator or Raysync support. The supplied sources do not unambiguously specify an operational workflow for this exact version.
3. For **versions before 8.1.8.6**, use the documented legacy **Send** and **Receive** pages. Some older documentation also refers to a transfer ID and key.

#### Version differences

The release list explicitly dates the page redesign to 8.1.8.7 and P2P system notifications to 8.1.8.6.

#### Important notes

The quick-start heading says “Before 8186,” while the page redesign begins at 8187, leaving 8.1.8.6 without an explicit workflow in the supplied documentation. No behavior from either adjacent range should be assumed for that exact version.

#### Sources

- `p2p-task.md` — “Quick Start - Version 8187+” and legacy quick start
- `p2p-8186.md` — legacy Send/Receive workflow
- `p2p.md` — current workflow
- `release.md` — “v8.1.8.7” and “v8.1.8.6”
