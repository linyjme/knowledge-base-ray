 <h1 class="curproject-name"> Raysync Client API Documentation </h1> 

[TOC]

# Overview

The interface needs to rely on the Raysync Client. After the Raysync Client is started, it will listen to 6598/TCP and provide HTTP services. 

The document describes the meaning of all interfaces and fields that communicate with the Raysync Client.



## HTTPS Service

If you need to use the https service, additional configuration is required.

Operating Environment: Windows/Linux/Mac Client

URL address：https://xx.domain:6598



**Configuration Steps**

Rename your certificate file names to the following:

Public key: certificate.pem

![image-20230919184027925.png](http://raysync.oss-cn-shenzhen.aliyuncs.com/web3.0/doc/image-20230919184027925.png)



Private key: private.key

  ![img](https://raysync-dl.s3.eu-west-2.amazonaws.com/doc/wps5556.tmp.jpg)



**Windows：**

1. Place your certificate file in the C:/Program Files (x86)/Raysync Client/config/ssl directory in the Raysyn client installation directory (the /config/ssl directory needs to be created manually);

![image-20230919184027925.png](https://raysync-dl.s3.eu-west-2.amazonaws.com/doc/image-20240129103320594.png)

2. Restart the Client.

 

**Linux：**

1. Place your certificate files in the /usr/local/bin/config/ssl directory under the Raysyn Client installation directory (/config/ssl directory needs to be created manually).
2. Restart the Client.

 

**Mac：**

1. Place your certificate files in the /Applications/Raysync.app/Contents/RaysyncClientManager.app/Contents/MacOS/config/ssl directory under the Raysync Client installation directory (/config/ssl directory needs to be created manually).

2. Restart the Client.

   

**Synchronization Command Line Client:**

1. Place your certificate files in the config/ssl folder with raysync-man_cmd at the same directory level (/config/ssl directory needs to be created manually).
2. Restart the Client.



# Create task type



## Create normal transfer task

### Basic information

**Path：** /create-task

**Method：** POST

**Interface description:：**

<p>Create a normal transfer task.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name               | Type     | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Other information |
| ------------------ | -------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-name          | string   | Unnecessary     |         | Task Name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| server-ip          | string   | Necessary       |         | Server IP address                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-port        | integer  | Necessary       | 2442    | File service port                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-ssl-port    | integer  | Necessary       | 2443    | File service port using encryption                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| proxy-port         | integer  | Necessary       | 32001   | Accelerated service port                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| protocol-type      | string   | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold    | integer  | Unnecessary     | 0       | When "protocol-type" is "auto", the connection method is selected based on the value of this field. When protocol-type is set to auto, this field specifies the delay threshold (milliseconds), which is used to determine the connection method. Below this value TCP is preferred, above this value UDP                                                                                                                                                                                                                                                                                                                                       |                   |
| account            | string   | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| password           | string   | Necessary       |         | The password used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| source-path        | string   | Necessary       |         | Specify the source path. It is a local path when uploading and a server path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| target-path        | string   | Necessary       |         | Target path; it is a server path when uploading and a local path when Downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| space-id           | integer  | Unnecessary     |         | User space id                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| group-id           | integer  | Necessary       | 0       | User group space ID. A user can have multiple user group spaces, and the user group spaces can be switched by modifying this parameter. Group ID of 0 is the user’s default group space.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| task-type          | string   | Necessary       |         | Task type upload download                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| enable-ssl         | boolean  | Unnecessary     |         | Whether to use the encryption protocol to establish a connection with the file server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                   |
| enable-verify-hash | boolean  | Unnecessary     |         | Whether to open the Hash verification. When turning on, the source and target files will be checked hash before and after the transmission is completed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| enable-save-acl    | boolean  | Unnecessary     |         | Retain file ACL attributes (only supported on the same system)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| full-path-pair     | boolean  | Unnecessary     | false   | Keep each source path as a complete source/target pair. This value is used as the default for items in path-list. `full_path_pair` is also accepted as a compatibility alias.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| path-list          | object[] | Unnecessary     |         | List of transmission path; prefer to a single path.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| └─source-path      | string   | Unnecessary     |         | Specify the source path. When uploading is the local path, the server path is downloaded when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| └─target-path      | string   | Unnecessary     |         | Target path; the server path when uploading, the local path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| └─file-alias       | string   | Unnecessary     |         | Alias; specify the alias of the target path                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| └─full-path-pair   | boolean  | Unnecessary     |         | Override the request-level full-path-pair value for this path item. `full_path_pair` is also accepted as a compatibility alias.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| endpoint           | string   | Unnecessary     |         | Specify the endpoint of oss or aws object storage when uploading or downloading                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| access-key-id      | string   | Unnecessary     |         | Specify the accesskeyid for oss or aws object storage when uploading or downloading                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| bucket-name        | string   | Unnecessary     |         | Specify the bucketname of oss or aws object storage when uploading or downloading                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |

### Request sample 1

```json
{
    "task-name": "upload-test",
    "server-ip": "192.168.1.1",
    "server-port": 2442,
    "server-ssl-port": 2443,
    "proxy-port": 32001,
    "protocol-type": "auto",
    "delay-threshold": 10,
    "account": "test",
    "password": "123456",
    "group-id": 0,
    "task-type": "upload",
    "source-path": "/root/test",
    "target-path": "/",
    "enable-ssl":false,
    "enable-hash":false,
    "enable-save-acl":false
}
```



### Request sample 2


```json
{
    "task-name": "upload-test",
    "server-ip": "192.168.1.1",
    "server-port": 2442,
    "server-ssl-port": 2443,
    "proxy-port": 32001,
    "protocol-type": "auto",
    "delay-threshold": 10,
    "account": "test",
    "password": "123456",
    "group-id": 0,
    "task-type": "upload",
    "enable-ssl":false,
    "enable-hash":false,
    "enable-save-acl":false,
    "full-path-pair": false,
    "path-list":[
        {
        "source-path": "/root/test",
        "target-path": "/",
        "file-alias":"",
        "full-path-pair": true
    },
    {
        "source-path": "/root/test1",
        "target-path": "/1",
        "file-alias":""
    }]
}
```



### Return data

| Name    | Type    | Is it Necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| task-id | string  | Necessary       |         | If the task is created successfully,return to the task ID of the new task, otherwise, return 0.                                                         |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```



## Create synchronization task

### Basic information

**Path：** /create-sync-task

**Method：** POST

**Interface description:：**

<p>Create a synchronous data transfer task.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**


| Name                            | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Other information |
| ------------------------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-name                       | string  | Necessary       |         | Task Name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| server-ip                       | string  | Necessary       |         | Server IP address                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| server-port                     | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| server-ssl-port                 | integer | Necessary       | 2443    | File service port using encryption.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| proxy-port                      | integer | Necessary       | 32001   | Accelerated service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| protocol-type                   | string  | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field。   |                   |
| delay-threshold                 | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;                                                                                                                                                                                                                                                                                                                                   |                   |
| account                         | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| password                        | string  | Necessary       |         | The password used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| task-type                       | string  | Necessary       |         | Task Type upload ：synchronous upload; download ：synchronous download bidirectional ：two-way sync）. Real-time sync only supports upload.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| source-path                     | string  | Necessary       |         | Specify the source path. It is a local path when uploading and a server path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| target-path                     | string  | Necessary       |         | Target path; it is a server path when uploading and a local path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| full-path-pair                  | boolean | Unnecessary     | false   | Default value for full-path-pair in each path-list item. `full_path_pair` is also accepted as a compatibility alias.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| path-list                       | object[]| Unnecessary     |         | List of synchronization paths. When submitted, source-path and target-path are read from each item.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| └─source-path                   | string  | Necessary       |         | Source path for this path item.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| └─target-path                   | string  | Necessary       |         | Target path for this path item.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| └─file-alias                    | string  | Unnecessary     |         | Alias of the target path.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| └─full-path-pair                | boolean | Unnecessary     |         | Override the request-level full-path-pair value for this item. `full_path_pair` is also accepted as a compatibility alias.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| exclude                         | string  | Unnecessary     |         | Specify the names of files or folders that need to be excluded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| triggering-condition            | object  | Necessary       |         | Task trigger conditions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                   |
| └─ type                         | string  | Necessary       |         | Task trigger type. clock: Set to be executed once every day at a specified time point. If the current time has exceeded the specified time, it will be executed immediately. interval: Set to execute every specified time, execute the task immediately after it is created, and then calculate the next execution time from the completion of task execution. once: Execute only once after the task is created. user-start-once: The task is not executed immediately after creation and needs to be executed manually. weekly-time: Automatically execute once a week on the specified day and time. Used with the week and clock parameters. real-time: Enable real-time upload sync. |                   |
| └─ clock                        | string  | Unnecessary     |         | Specify that the task is executed at the specified time every day. When the specified "type" field is "clock", the field is valid. For example:"08:00": It is specified to execute the task at 8 every morning.                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| └─ interval                     | integer | Unnecessary     |         | Specify that the task is executed every specified time, unit: second. When the specified "type" field is "interval" or "real-time", the field is valid. For example:3600: The specified task is executed every 1 hour.                                                                                                                                                                                                                                                                                                                                                              |                   |
| └─ week                         | integer | Necessary       |         | Specify the date on which the task will be executed. 1, 2, 4, 8, 16, 32, and 64 correspond to Monday to Sunday, and if you want to specify multiple dates, the corresponding values are summed. For example, 15 represents Monday to Tursday                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| enable-compress-file            | boolean | Unnecessary     |         | Enable zip compression for packaging and transmission.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                   |
| compress-file-name              | string  | Unnecessary     |         | Specify the zip compression package transfer name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| enable-save-acl                 | boolean | Unnecessary     |         | Retain file ACL attributes (only supported on the same system)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| enable-ssl                      | boolean | Necessary       |         | Whether to use the encryption protocol to establish a connection with the file server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                   |
| enable-wildcard-blacklist       | bool    | Unnecessary     |         | Whether to enable the transmission blacklist and support wildcards (the whitelist is not supported to be enabled at the same time)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| wildcard-blacklist              | string  | Unnecessary     |         | Transmission blacklist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| enable-wildcard-whitelist       | bool    | Unnecessary     |         | Whether to enable the transmission whitelist (it is not supported to enable it at the same time as the blacklist)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| wildcard-whitelist              | string  | Unnecessary     |         | Transport whitelist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| file-update-mode                | integer | Unnecessary     | 0       | Processing method when the target file already exists: 0 means overwrite 1 means append writing to the target file (not applicable to object storage) 2 means rename (only supports once transfer task) 3 means overwrite if the source file is newer. Real-time sync only supports 0.                                                                                                                                                                                                                                                                                             |                   |
| enable-save-timestamp           | boolean | Unnecessary     |         | Whether to keep the time stamp information of the transferred file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| unfold-path                     | boolean | Unnecessary     |         | Whether to enable only transferring files and folders in the source directory, true means enabled, false on the contrary, when task-type is bidirectional (two-way synchronization), this parameter is yes. Real-time sync forces this value to true internally.                                                                                                                                                                                                                                                                                                                       |                   |
| enable-sync-remove              | boolean | Unnecessary     |         | Whether to enable the synchronous deletion function. When enabled, more files and folders on the target terminal than on the source terminal will be deleted when executing the synchronization operation. Real-time sync requires this value to be true.                                                                                                                                                                                                                                                                                                                              |                   |
| check-before-transfer           | object  | Unnecessary     |         | Verification is performed before starting the transmission, and the transmission is not started until the file has no changes within (3~30) seconds. Contains the following attributes: enable-check, check-time                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| └─ enable-check                 | boolean | Unnecessary     |         | Whether to enable pre-transmission verification. true means turned on, false means vice versa                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| └─ check-time                   | integer | Unnecessary     |         | How many seconds does the file remain unchanged before transmission begins? The range is 3~30.。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| enable-sync-source-file-updated | boolean | Unnecessary     |         | Whether to enable synchronization when the source file is updated, true means enabled, false otherwise. Real-time sync does not support this option and requires false.                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| enable-remove-on-completed      | boolean | Unnecessary     |         | Whether to enable the function of automatically deleting source files after file transfer is completed. Real-time sync does not support source file processing and requires false.                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| enable-remove-file-on-completed | boolean | Unnecessary     |         | Whether to enable source file processing after each file transfer is completed: automatically delete the source file and retain the source directory structure when deleting (applicable to synchronous upload and synchronous download). Real-time sync does not support source file processing and requires false.                                                                                                                                                                                                                                                                   |                   |
| move-source-file                | object  | Unnecessary     |         | Delete source files (only applicable to synchronous upload). Real-time sync does not support source file processing.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| └─enable-move-source-file       | boolean | Unnecessary     |         | Whether to enable deletion of source files                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| └─move-source-file-minutes      | integer | Unnecessary     |         | Preferred delay before moving the uploaded source file to move-source-file-target-path, in minutes. The value must be greater than 0.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| └─move-source-file-hours        | integer | Unnecessary     |         | Backward-compatible delay in hours. It is used only when move-source-file-minutes is absent and is converted to minutes internally.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| └─move-source-file-target-path  | string  | Unnecessary     |         | Move the source files to the specified path                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| └─remove-source-file-days       | integer | Unnecessary     |         | And after how many days, the transferred files will be automatically deleted.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| enable-share-file-after-upload  | boolean | Unnecessary     |         | Whether to enable sharing with others for downloading after uploading is completed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| share-emails                    | string  | Unnecessary     |         | Recipient email address, the email address used to receive the sharing link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| share-emails-content            | string  | Unnecessary     |         | Email message content                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| share-emails-password           | string  | Unnecessary     |         | Set a password for shared links                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| space_id                        | integer | Unnecessary     |         | User space id                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| group_id                        | integer | Unnecessary     |         | User group space ID. A user can have multiple user group spaces, and the user group spaces can be switched by modifying this parameter. Group ID of 0 is the user’s default group space.                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                   |
| node-url                        | string  | Unnecessary     |         | Address of the server reported by the synchronization task. The synchronization task list is displayed on this server                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |


### Request sample 1

```json
{
	"task-name": "sync-test",
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456",
	"group-id": 0,
	"enable-append": false,
	"enable-save-timestamp": true,
	"enable-sync-remove": false,
	"enable-remove-on-completed": false,
	"task-type": "upload",
	"triggering-condition": {
		"type": "clock",
		"clock": "08:00"
	},
	"source-path": "/root/sync",
	"target-path": "/",
	"exclude": "",
	"enable-exclude-large-file": false,
	"exclude-large-file-size": 0,
	"enable-save-acl":false,
	"node-url":"http://192.168.1.1:8090",
    "enable-wildcard-blacklist": true,
	"wildcard-blacklist": "*.log",
	"enable-wildcard-whitelist": false,
	"wildcard-whitelist": "",
	"share-emails": "test@rayvision.com",
    "share-emails-content": "111",
    "share-emails-password": "uzjd"
}
```

### Request sample 2

```json
{
  "task-name": "sync-test",
  "server-ip": "192.168.1.1",
  "server-port": 2442,
  "server-ssl-port": 2443,
  "proxy-port": 32001,
  "protocol-type": "auto",
  "delay-threshold": 10,
  "account": "test",
  "password": "123456",
  "task-type": "upload",
  "triggering-condition": {
    "type": "interval",
    "interval": 3600
  },
  "full-path-pair": false,
  "path-list": [
    {
      "source-path": "/root/sync",
      "target-path": "/",
      "file-alias": "",
      "full-path-pair": true
    }
  ]
}
```

### Request sample 3

```json
{
  "task-name": "sync-test",
  "server-ip": "192.168.1.1",
  "server-port": 2442,
  "server-ssl-port": 2443,
  "proxy-port": 32001,
  "protocol-type": "auto",
  "delay-threshold": 10,
  "account": "test",
  "password": "123456",
  "triggering-condition": {
    "type": "weekly-time",
    "timing": {
	  "week": 15,
	  "clock": "14:26"
    }
  },
  "source-path": "/root/sync",
  "target-path": "/"
}
```

### Request sample 4 real-time sync

```json
{
  "task-name": "real-time-sync-test",
  "server-ip": "192.168.1.1",
  "server-port": 2442,
  "server-ssl-port": 2443,
  "proxy-port": 32001,
  "protocol-type": "auto",
  "delay-threshold": 10,
  "account": "test",
  "password": "******",
  "enable-ssl": false,
  "enable-save-timestamp": true,
  "enable-sync-remove": true,
  "enable-remove-on-completed": false,
  "enable-remove-file-on-completed": false,
  "enable-sync-source-file-updated": false,
  "file-update-mode": 0,
  "task-type": "upload",
  "triggering-condition": {
    "type": "real-time",
    "interval": 60
  },
  "source-path": "D:/sync/source",
  "target-path": "/real-time-sync-test"
}
```

### Real-time sync restrictions

When `triggering-condition.type` is `real-time`, the interface applies the following validations and returns `code: 7` with the matching message when validation fails.

| Condition | Message |
| --------- | ------- |
| `task-type` is not `upload` | real-time sync only supports upload tasks. |
| `path-list` contains more than one item | real-time sync does not support multiple paths. |
| `enable-sync-remove` is not `true` | real-time sync requires [enable-sync-remove] to be true. |
| `enable-remove-on-completed`, `enable-remove-file-on-completed`, or `move-source-file.enable-move-source-file` is enabled | real-time sync does not support source file processing. |
| `enable-sync-source-file-updated` is `true` | real-time sync does not support [enable-sync-source-file-updated]. |
| `file-update-mode` is not `0` | real-time sync only supports overwrite mode: [file-update-mode] must be 0. |

### Return data

| Name    | Type    | Is it Necessary | Default | Remark                                                                                                                                                   | Other information |
| ------- | ------- | --------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.非 0。                                               |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed.。 |                   |
| task-id | string  | Necessary       |         | If the task is created successfully, return to the task ID of the new task, otherwise, return 0.                                                         |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```



## Create local copy task

### Basic information

**Path：** /create-local-copy-task

**Method：** POST

**Interface description:：**

<p>Create a local copy task on the client side.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                       | Type     | Is it necessary | Default | Remark                                                                                                                                      | Other information |
| -------------------------- | -------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-name                  | string   | Unnecessary     |         | Task name.                                                                                                                                  |                   |
| server-ip                  | string   | Necessary       |         | Server IP address used for login context.                                                                                                   |                   |
| server-port                | integer  | Necessary       | 2442    | File service port.                                                                                                                          |                   |
| server-ssl-port            | integer  | Necessary       | 2443    | File service port using encryption.                                                                                                         |                   |
| proxy-port                 | integer  | Necessary       | 32001   | Accelerated service port.                                                                                                                   |                   |
| account                    | string   | Necessary       |         | The account used to log in to the file system.                                                                                              |                   |
| password                   | string   | Necessary       |         | The password used to log in to the file system.                                                                                             |                   |
| source-path                | string   | Necessary       |         | Source local path. Required when path-list is not submitted.                                                                                |                   |
| target-path                | string   | Necessary       |         | Target local path. Required when path-list is not submitted.                                                                                |                   |
| path-list                  | object[] | Unnecessary     |         | List of local copy paths. If this field is submitted, source-path and target-path are read from each item.                                   |                   |
| └─source-path              | string   | Necessary       |         | Source local path.                                                                                                                          |                   |
| └─target-path              | string   | Necessary       |         | Target local path.                                                                                                                          |                   |
| group-id                   | integer  | Unnecessary     | 0       | User group space ID.                                                                                                                        |                   |
| enable-ssl                 | boolean  | Unnecessary     |         | Whether to use the encryption protocol when logging in.                                                                                     |                   |
| trans-mode                 | integer  | Unnecessary     | 0       | Processing method when the target file already exists: 0 overwrite, 1 overwrite, 2 resume, 3 skip.                                         |                   |
| parallel-files             | integer  | Unnecessary     | 1       | Number of local files copied in parallel. The manager clamps the effective value to 1~8. `parallel_files` is also accepted as a compatibility alias. |                   |
| bDelete-source-after-copy  | boolean  | Unnecessary     | false   | Whether to delete the source file after copying.                                                                                            |                   |
| bVerify-hash               | boolean  | Unnecessary     | false   | Whether to verify hash after copying.                                                                                                       |                   |


### Request sample

```json
{
  "task-name": "local-copy-test",
  "server-ip": "192.168.1.1",
  "server-port": 2442,
  "server-ssl-port": 2443,
  "proxy-port": 32001,
  "account": "test",
  "password": "123456",
  "source-path": "D:/source",
  "target-path": "D:/target",
  "group-id": 0,
  "enable-ssl": false,
  "trans-mode": 0,
  "parallel-files": 4,
  "bDelete-source-after-copy": false,
  "bVerify-hash": true
}
```

### Return data

| Name    | Type    | Is it Necessary | Default | Remark                                                                                                         | Other information |
| ------- | ------- | --------------- | ------- | -------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.          |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful.            |                   |
| task-id | string  | Necessary       |         | If the task is created successfully, return to the task ID of the new task, otherwise, return 0.                |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```



## Create P2P transfer task

### Basic information

**Path：** /create-p2p-task

**Method：** POST

**Interface description:：**

<p>Create a P2P transfer task.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**


| Name                      | Type    | Is it Necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Other information |
| ------------------------- | ------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-name                 | string  | Necessary       |         | Task name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| server-ip                 | string  | Necessary       |         | Server IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-port               | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-ssl-port           | integer | Necessary       | 2443    | File service port using encryption.\|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| proxy-port                | integer | Necessary       | 32001   | Accelerated service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| protocol-type             | string  | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold           | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;                                                                                                                                                                                                                                                                                                                                 |                   |
| account                   | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| password                  | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| p2p-id                    | string  | Necessary       |         | P2P transfer ID or IP address of the receiver.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| task-type                 | string  | Necessary       |         | ask type upload ：Send; download ：Receive                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| source-path               | string  | Necessary       |         | Specify the source path. It is a local path when uploading and a receiving path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| target-path               | string  | Necessary       |         | Target path: it is a receiving path when uploading and a local path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| full-path-pair            | boolean | Unnecessary     | false   | Keep the source and target as a complete path pair. `full_path_pair` is also accepted as a compatibility alias.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| exclude                   | string  | Unnecessary     |         | pecify the names of files or folders that need to be excluded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| enable-save-acl           | boolean | Unnecessary     |         | Retain file ACL attributes (only supported on the same system)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| enable-wildcard-blacklist | bool    | Unnecessary     |         | Whether to enable the transmission blacklist and support wildcards (the whitelist is not supported to be enabled at the same time)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| wildcard-blacklist        | string  | Unnecessary     |         | Transmission blacklist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| enable-wildcard-whitelist | bool    | Unnecessary     |         | Whether to enable the transmission whitelist (it is not supported to enable it at the same time as the blacklist)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| wildcard-whitelist        | string  | Unnecessary     |         | Transport whitelist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |



### Request sample


```json
{
	"task-name": "p2p-test",
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456",
	"p2p-id": "192.168.1.2",
	"task-type": "upload",
	"source-path": "/root/p2p",
	"target-path": "/",
	"full-path-pair": false,
    "exclude": "",
    "enable-save-acl":false,
    "enable-wildcard-blacklist": true,
	"wildcard-blacklist": "*.log",
	"enable-wildcard-whitelist": false,
	"wildcard-whitelist": ""
}
```



### Return data


| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| task-id | string  | Necessary       |         | If the task is created successfully, return to the task ID of the new task, otherwise, return 0.                                                        |                   |



### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```

## Create synchronous P2P transfer task

### Basic information

**Path：** /create-sync-p2p-task

**Method：** POST

**Interface description:：**

<p>Create a synchronous P2P transfer task.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                       | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Other information |
| -------------------------- | ------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-name                  | string  | Necessary       |         | Task name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| server-ip                  | string  | Necessary       |         | Server IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-port                | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-ssl-port            | integer | Necessary       | 2443    | File service port using encryption.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| proxy-port                 | integer | Necessary       | 32001   | Accelerated service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| protocol-type              | string  | Unnecessary     |         | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold            | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;                                                                                                                                                                                                                                                                                                                                 |                   |
| account                    | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| password                   | string  | Necessary       |         | The password used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| p2p-id                     | string  | Necessary       |         | P2P transfer ID or IP address of the receiver.。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| task-type                  | string  | Necessary       |         | Task type upload ：Send; download ：Receive                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| source-path                | string  | Necessary       |         | Specify the source path. It is a local path when uploading and a receiving path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| target-path                | string  | Necessary       |         | Target path; it is a receiving path when uploading and a local path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| exclude                    | string  | Unnecessary     |         | Specify the names of files or folders that need to be excluded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| triggering-condition       | object  | Necessary       |         | Task triggering condition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| └─ type                    | string  | Necessary       |         | The type of task triggered. clock: Executes once a day at a specified point in time, or once if the current time has exceeded the specified time. interval: Set the time to be executed at specified intervals, immediately after the task is created, and then calculate the time for the next execution from the time the task is completed. once: Executes the task only once after it is created. user-start-once: The task is not executed immediately after it is created and needs to be executed manually. weekly-time: automatically executes the specified day and time once a week. Use with the week and clock parameters.          |                   |
| └─ clock                   | string  | Unnecessary     |         | Specify that the task is executed at the specified time every day. When the specified "type" field is "clock", the field is valid. For example:"08:00": It is specified to execute the task at 8 every morning.。                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| └─ interval                | integer | Unnecessary     |         | Specify that the task is executed every specified time, unit: second. When the specified "type" field is "interval", the field is valid. For example:3600: The specified task is executed every 1 hour.                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| └─ week                    | integer | Unnecessary     |         | Specify the date on which the task will be executed. 1, 2, 4, 8, 16, 32, and 64 correspond to Monday to Sunday, and if you want to specify multiple dates, the corresponding values are summed. For example, 15 represents Monday to Tursday                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| enable-compress-file       | string  | Unnecessary     |         | Enable zip compression and packaging transmission.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| enables-compress-file-name | string  | Unnecessary     |         | Specify the name of the zip compression package transmission.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| enable-save-acl            | boolean | Unnecessary     |         | Retain file ACL attributes (only supported on the same system)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| enable-wildcard-blacklist  | bool    | Unnecessary     |         | Whether to enable the transmission blacklist and support wildcards (the whitelist is not supported to be enabled at the same time)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| wildcard-blacklist         | string  | Unnecessary     |         | Transmission blacklist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| enable-wildcard-whitelist  | bool    | Unnecessary     |         | Whether to enable the transmission whitelist (it is not supported to enable it at the same time as the blacklist)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| wildcard-whitelist         | string  | Unnecessary     |         | Transport whitelist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| file-update-mode           | integer | Unnecessary     |         | Processing method when the target file already exists: 0 means overwrite 1 means append writing to the target file (not applicable to object storage) 2 means rename (only supports once transfer task) 3 means overwrite if the source file is newer                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| enable-save-timestamp      | boolean | Unnecessary     |         | Whether to retain file modification time, true means to enable retaining file modification time, false otherwise                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| unfold-path                | boolean | Unnecessary     |         | Whether to enable only transferring files and folders in the source directory, true means enabled, false on the contrary, when task-type is bidirectional (two-way synchronization), this parameter is yes                                                                                                                                                                                                                                                                                                                                                                                                                                      |                   |
| enable-sync-remove         | boolean | Unnecessary     |         | Whether to enable automatic deletion of the target file when the source file is deleted, true means enabled, false otherwise.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| check-before-transfer      | object  | Unnecessary     |         | Verification is performed before starting the transmission, and the transmission is not started until the file has no changes within (3~30) seconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                   |
| └─enable-check             | boolean | Unnecessary     |         | Whether to enable pre-transmission verification. true means enabled, false means vice versa.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| └─ check-time              | integer | Unnecessary     |         | How many seconds does the file remain unchanged before transmission begins? The range is 3~30.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |


### Request sample 1

```json
{
	"task-name": "p2p-test",
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456",
	"p2p-id": "192.168.1.2",
	"task-type": "upload",
	"source-path": "/root/p2p",
	"target-path": "/",
	"triggering-condition": {
	    "type": "interval",
	    "interval": 3600
    },
    "exclude": "",
    "enable-save-acl":false,
    "enable-wildcard-blacklist": true,
	"wildcard-blacklist": "*.log",
	"enable-wildcard-whitelist": false,
	"wildcard-whitelist": ""
}
```

### Request sample 2

```json
{
	"task-name": "p2p-test",
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456",
	"p2p-id": "192.168.1.2",
	"task-type": "upload",
	"source-path": "/root/p2p",
	"target-path": "/",
	"triggering-condition": {
	  "type": "weekly-time",
	  "timing":{
		"week": 15,
		"clock":"14:26"
	    }
    },
    "exclude": "",
    "enable-save-acl":false,
    "enable-wildcard-blacklist": true,
	"wildcard-blacklist": "*.log",
	"enable-wildcard-whitelist": false,
	"wildcard-whitelist": ""
}
```



### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| task-id | string  | Necessary       |         | If the task is created successfully, return to the task ID of the new task, otherwise,return 0.                                                         |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```


## Create cluster task
### Basic information

**Path：** /create-cluster-task

**Method：** POST

**Interface description:：**

<p>Create a cluster transfer task.</p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                      | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Other information |
| ------------------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| task-name                 | string  | Necessary       |         | Task name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| server-ip                 | string  | Necessary       |         | Server IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-port               | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-ssl-port           | integer | Necessary       | 2443    | File service port using encryption.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| enable-ssl                | boolean | Necessary       | false   | Whether to use encryption protocol to establish connection with file server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| proxy-port                | integer | Necessary       | 32001   | Accelerated service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| protocol-type             | string  | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ： Automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold           | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;                                                                                                                                                                                                                                                                                                                                  |                   |
| account                   | string  | Necessary       |         | The account used to log in to the file system                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| password                  | string  | Necessary       |         | The password used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| group-id                  | integer | Unnecessary     | 0       | User group space ID. A user can have multiple user group spaces, and the user group spaces can be switched by modifying this parameter. Group ID of 0 is the user’s default group space.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| enable-append             | boolean | Unnecessary     | false   | Whether to write the file by appending. When enabled, when the target file is larger than the local file, appending writing is continued from the transmitted part of the file without comparing whether the modification time of the file is consistent with the transmitted part. When closed, the program will compare the modification time and size of the source and target files to decide whether to continue transmission or retransmit.                                                                                                                                                                                                |                   |
| enable-verify-hash        | boolean | Unnecessary     | false   | Whether to enable Hash verification. When enabled, Hash verification will be carried out on the source and target files before and after transmission.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| enable-compress           | boolean | Unnecessary     | false   | Whether to enable data compression. When enabled, it will attempt to compress file data. If the compressed data is smaller than the original data, the compressed data will be transmitted; if the compressed data is larger than the original data, the original data will be transmitted.The compression function can be effective when both the server and the client are enabled.                                                                                                                                                                                                                                                            |                   |
| enable-save-timestamp     | boolean | Unnecessary     | true    | Whether to keep the time stamp information of the transferred file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| enable-sync-remove        | boolean | Unnecessary     | false   | Whether to enable the synchronous deletion function; When enabled, more files and folders on the target terminal than on the source terminal will be deleted when executing the synchronization operation.                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| task-type                 | string  | Necessary       |         | Task type upload ：synchronous upload; download ：synchronous download                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| triggering-condition      | object  | Necessary       |         | Task triggering condition                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| └─type                    | string  | Necessary       |         | Task trigger type. clock: Set to be executed once every day at a specified time point. If the current time has exceeded the specified time, it will be executed immediately. interval: Set to execute every specified time, execute the task immediately after it is created, and then calculate the next execution time from the completion of task execution. once: Execute only once after the task is created. user-start-once: The task is not executed immediately after creation and needs to be executed manually.                                                                                                                       |                   |
| └─clock                   | string  | Unnecessary     |         | Specify that the task is executed at the specified time every day. When the specified "type" field is "clock", the field is valid. For example:"08:00": It is specified to execute the task at 8 every morning.                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| └─interval                | integer | Unnecessary     |         | Specify that the task is executed every specified time, unit: second. When the specified "type" field is "interval", the field is valid. For example:3600: The specified task is executed every 1 hour.                                                                                                                                                                                                                                                                                                                                                                                                                                          |                   |
| source-path               | string  | Necessary       |         | Specify the source path. It is a local path when uploading and a server path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| target-path               | string  | Necessary       |         | Target path. it is a server path when uploading and a local path when downloading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| exclude                   | string  | Unnecessary     |         | Specify the names of files or folders that need to be excluded.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| trans-log                 | string  | Unnecessary     |         | Specify the generation path of the transmission log during file transmission. If not specified, transmission log shall not be generated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                   |
| hash-log                  | string  | Unnecessary     |         | Specify the generation path of Hash log after file transmission is completed. If not specified, Hash log shall not be generated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| error-log                 | string  | Unnecessary     |         | Specify the log path to which error files are written when errors occur during transmission. If not specified, error log shall not be generated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| redis-address             | string  | Necessary       |         | Specify the redis server address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| redis-port                | integer | Necessary       |         | Specify the redis server port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| redis-password            | string  | Unnecessary     |         | Specify the password used to connect the redis server. If the password is not set, this field does not need to be filled in.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |
| enable-wildcard-blacklist | bool    | Unnecessary     |         | Whether to enable the transmission blacklist and support wildcards (the whitelist is not supported to be enabled at the same time)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| wildcard-blacklist        | string  | Unnecessary     |         | Transmission blacklist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| enable-wildcard-whitelist | bool    | Unnecessary     |         | Whether to enable the transmission whitelist (it is not supported to enable it at the same time as the blacklist)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| wildcard-whitelist        | string  | Unnecessary     |         | Transport whitelist, supports wildcards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                   |



### Request sample

```json
{
	"task-name": "sync-test",
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"enable-ssl": false,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456",
	"group-id": 0,
	"enable-append": false,
	"enable-verify-hash": false,
	"enable-compress": true,
	"enable-save-timestamp": true,
	"enable-sync-remove": true,
	"task-type": "upload",
	"triggering-condition": {
		"type": "interval",
		"interval": 3600,
	},
	"source-path": "/root/test",
	"target-path": "/",
	"exclude": "",
	"hash-log": "/root/hash-log",
	"error-log": "/root/error-log",
	"redis-address": "127.0.0.1",
	"redis-port": 6379,
	"redis-password": "",
    "enable-wildcard-blacklist": true,
	"wildcard-blacklist": "*.log",
	"enable-wildcard-whitelist": false,
	"wildcard-whitelist": ""
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| task-id | string  | Necessary       |         | If the task is created successfully, return to the task ID of the new task, otherwise, return 0.                                                        |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success",
	"task-id": "1"
}
```




# P2P transfer

## Enable P2P transfer monitor

### Basic information

**Path：** /enable-p2p-monitor

**Method：** POST

**Interface description:：**

<p>Enable P2P transfer of the receiver. The receiver can establish a connection with the sender only after the P2P transfer monitor is enabled. If multiple servers are available, enable the P2P transfer monitor on each server. The sender can establish a connection with the receiver without enabling the P2P transfer monitor. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**


| Name            | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Other information |
| --------------- | ------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| server-ip       | string  | Necessary       |         | Server IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-port     | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| server-ssl-port | integer | Necessary       | 2443    | File service port using encryption.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| proxy-port      | integer | Necessary       | 32001   | Accelerate service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| protocol-type   | string  | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;；                                                                                                                                                                                                                                                                                                                                |                   |
| account         | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| password        | string  | Necessary       |         | The password used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |


### Request sample

```json
{
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test",
	"password": "123456"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Disable P2P transfer monitor

### Basic information

**Path：** /disable-p2p-monitor

**Method：** POST

**Interface description:：**

<p>Disable P2P transfer of the receiver. Then the receiver cannot receive the P2P transfer tasks initiated by the sender. If multiple servers are available, disable the P2P transfer on each server.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name            | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Other information |
| --------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| server-ip       | string  | Necessary       |         | Server IP address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-port     | integer | Necessary       | 2442    | File service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                   |
| server-ssl-port | integer | Necessary       | 2443    | File service port using encryption.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| proxy-port      | integer | Necessary       | 32001   | Accelerated service port.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| protocol-type   | string  | Unnecessary     | default | Specify to use TCP or UDP protocol to establish connection with the server. Default ： The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：automatically switch according to the "delay-threshold" field. |                   |
| delay-threshold | integer | Unnecessary     | 0       | When "protocol-type" is specified as "auto", select the way to connect to the server according to the value of this field. When the delay is less than [delay-threshold], TCP protocol is preferred for connection; When the delay is greater than [delay-threshold], UDP protocol is preferred for connection;                                                                                                                                                                                                                                                                                                                                  |                   |
| account         | string  | Necessary       |         | The account used to log in to the file system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
### Request sample

```json
{
	"server-ip": "192.168.1.1",
	"server-port": 2442,
	"server-ssl-port": 2443,
	"proxy-port": 32001,
	"protocol-type": "auto",
	"delay-threshold": 10,
	"account": "test"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```


# Delete tasks

## Delete a single task 
### Basic information

**Path：** /delete-task

**Method：** POST

**Interface description:：**
<p>Delete an existing task based on the task ID. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |
**Body**

| Name     | Type     | Is it necessary | Default | Remark                                         | Other information |
| -------- | -------- | --------------- | ------- | ---------------------------------------------- | ----------------- |
| task-id  | interger | Necessary       |         | Specify the task ID of the task to be deleted. |                   |
| task-ids | string   | Necessary       |         | Specify multiple task IDs to be deleted        |                   |

### Request sample 1

```json
{
	"task-id": 1
}
```

### Request sample 2

```json
{
	"task-ids": "1,2"
}
```


### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Delete all tasks

### Basic information

**Path：** /delete-all-task

**Method：** POST

**Interface description:：**
<p>Deletes a task group or all task groups based on the specified type. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |
**Body**

| Name       | Type   | Is it necessary | Default | Remark                                                                                                                                                                   | Other information |
| ---------- | ------ | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| task-group | string | Necessary       |         | Specify the task type to be deleted; all=all tasks; normal=normal tasks; sync=synchronization tasks and cluster transmission tasks; p2p=Peer to Peer transmission tasks; |                   |

### Request sample

```json
{
	"task-group": "all"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



# Control task



## Start task
### Basic information

**Path：** /start-task

**Method：** POST

**Interface description:**

<p>Start a stopped task based on the task ID. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |
**Body**

| Name     | Type    | Is it necessary | Default | Remark                                                    | Other information |
| -------- | ------- | --------------- | ------- | --------------------------------------------------------- | ----------------- |
| task-id  | integer | Necessary       |         | Specify the task ID of the task that needs to be started. |                   |
| task-ids | string  | Necessary       |         | Specify multiple task IDs that need to be started.        |                   |

### Request sample

```json
{
	"task-id": 1
}
```
### Request sample 2

```json
{
  "task-ids": "1,2"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Start all task

### Basic information

**Path：** /start-all-task

**Method：** POST

**Interface description:**

<p>Starts one or all task types with the specified parameters.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name       | Type   | Is it necessary | Default | Remark                                                                                                                                    | Other information |
| ---------- | ------ | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-group | string | Necessary       |         | Specify the type of task you want to start; all=all task； normal=Normal transfer task; sync=Sync task,Cluster task; p2p=P2P transfer task |                   |

### Request sample

```json
{
	"task-group": "all"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |

### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```





## Stop task 

### Basic information

**Path：** /stop-task

**Method：** POST

**Interface description:**

<p>Stop a running task based on the task ID. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |
**Body**

| Name     | Type    | Is it necessary | Default | Remark                                                   | Other information |
| -------- | ------- | --------------- | ------- | -------------------------------------------------------- | ----------------- |
| task-id  | integer | Necessary       |         | Specify the task ID of the task that needs to be stoped. |                   |
| task-ids | string  | Necessary       |         | Specify multiple task IDs that need to be stoped.        |                   |

### Request sample 1

```json
{
	"task-id": 1
}
```

### Request sample 2

```json
{
	"task-ids": "2,3,4"
}
```


### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


## Stop all task 

### Basic information

**Path：** /stop-all-task

**Method：** POST

**Interface description:**

<p>Stop one or all task types with the specified parameters.</p>


### Request parameter

**Headers**

| Parameter name     | Parameter value           | Is it necessary | Sample | Remark |
| ------------ | ---------------- | -------- | ---- | ---- |
| Content-Type | application/json | Yes       |      |      |

**Body**

| Name       | Type   | Is it necessary | Default | Remark                                                                                                                                   | Other information |
| ---------- | ------ | --------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-group | string | Necessary       |         | Specify the type of task you want to stop; all=all task； normal=Normal transfer task; sync=Sync task,Cluster task; p2p=P2P transfer task |                   |


### Request sample

```json
{
	"task-group": "all"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Update task

### Basic information

**Path：** /update-task

**Method：** POST

**Interface description:：**
<p>Update an underage task based on the task ID. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name                  | Type       | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Other information |
| --------------------- | ---------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| update-tasks          | object [ ] | Necessary       |         | Specify task information that needs to be updated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| └─ task-id            | string     | Necessary       |         | Specify the task ID of the task that needs to be updated                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                   |
| └─ server-ip          | string     | Necessary       |         | Server ip                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                   |
| └─ protocol-type      | string     | Necessary       |         | Specify to use TCP or UDP protocol to establish connection with the server. Default ：The default mode, in which UDP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to TCP protocol. Tcp-first ：TCP protocol is preferred to establish connection with the server, and if the connection cannot be made, it shall be switched to UDP protocol. Tcp-only ：Only use TCP protocol to establish connection with the server. Udp-only ：Only use UDP protocol to establish connection with the server. Auto ：Automatically switch according to the "delay-threshold" field. |                   |
| └─ enable-ssl         | boolean    | Necessary       |         | Whether to use encryption protocol to establish connection with file server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| └─ enable-verify-hash | boolean    | Necessary       |         | Whether to enable Hash verification. When this function is enabled, the system performs Hash verification on source and target files before and after transmission.                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                   |
| └─ delete-database    | boolean    | Necessary       |         | Whether to delete the database of the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                   |


### Request sample

```json
{
	"update-tasks": [
        {
            "task-id":"15",
            "server-ip":"127.0.0.1",
            "protocol-type": "auto",
			"enable-ssl":false,
			"enable-verify-hash":false,
			"delete-database":false
        }
    ]
}
```

### Return data

| Name                  | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| --------------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code                  | integer | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message               | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| update-failed-task-id | string  | Necessary       |         | Returns the error task ID of the operation.                                                                                                             |                   |

### Return sample

```json
{
    "code": 0,
    "message": "success",
    "update-failed-task-id": "1,2,3"
}
```



# Check task status



## Get task list
### Basic information

**Path：** /get-task-list

**Method：** POST

**Interface description:：**
<p>Get a list of tasks in a specified type.</p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |
**Body**

| Name       | Type    | Is it necessary | Default | Remark                                                                                                                                                                  | Other information |
| ---------- | ------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-group | integer | Necessary       |         | Specify the task type to be gotten; all=all tasks; normal=normal tasks; sync=synchronization tasks and cluster transmission tasks; p2p=Peer to Peer transmission tasks; |                   |

### Request sample

```json
{
	"task-group": "all"
}
```

### Return data

| Name                 | Type      | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Other information |
| -------------------- | --------- | --------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-list            | object [] | Necessary       |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | item Type: object |
| └─task-id            | string    | Necessary       |         | task ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| └─task-name          | string    | Necessary       |         | Task name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| └─task-type          | string    | Necessary       |         | Task Type. upload ：upload task; download ：download task;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| └─task-group         | string    | Necessary       |         | Task grouping; normal ：normal task; sync ：sync task, cluster task; p2p ：P2P transfer task;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                   |
| └─task-state         | string    | Necessary       |         | Task status ; ready ：The tasks have been created and prepared to transfer; start ：Tasks are transferring; stopped ：Tasks stopped transferring; successful ：Tasks are successfully transferred; failed ：Failed to transfer tasks; auth-failed ：The authentication failed; proxy-closed ：The proxy server connection failed; idle ：The task is not triggered to transfer; stop-by-server ：Tasks transfer is stopped by server; no-permission ：Permission limitation; ip-locked ：The IP address is locked; stop-by-peer ：The P2P transfer is stopped by peer; failed-to-send ：The P2P transfer failed to send; connection-failed ：The P2P transfer connection failed; account-locked ：The account is locked. |                   |
| └─show-name          | string    | Necessary       |         | display name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| └─trans-mode         | integer   | Necessary       |         | Returns the transmission mode of the task, 0 is normal transmission, 1 is rsync verification transmission                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                   |
| triggering-condition | object    | Necessary       |         | Task trigger type. clock: Set to be executed once every day at a specified time point. If the current time has exceeded the specified time, it will be executed immediately. interval: Set to execute every specified time, execute the task immediately after it is created, and then calculate the next execution time from the completion of task execution. once: Execute only once after the task is created. user-start-once: The task is not executed immediately after creation and needs to be executed manually. weekly-time: Automatically execute once a week on the specified day and time. Used with the week and clock parameters.                                                         |                   |
| └─└─ type            | string    | Necessary       |         | pecify that the task is executed at the specified time every day. When the specified "type" field is "clock", the field is valid. For example:"08:00": It is specified to execute the task at 8 every morning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                   |
| └─└─ clock           | string    | Necessary       |         | Specify that the task is executed at the specified time every day. When the specified "type" field is "clock", the field is valid. For example:"08:00": It is specified to execute the task at 8 every morning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                   |
| └─└─ interval        | integer   | Necessary       |         | Specify that the task is executed every specified time, unit: second. When the specified "type" field is "interval", the field is valid. For example:3600: The specified task is executed every 1 hour.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                   |
| └─└─ week            | integer   | Necessary       |         | Specify the date on which the task will be executed. 1, 2, 4, 8, 16, 32, and 64 correspond to Monday to Sunday, and if you want to specify multiple dates, the corresponding values are summed. For example, 15 represents Monday to Tursday                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                   |
| └─use-ssl            | boolean   | Necessary       |         | Whether to enable encrypted transmission                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |
| code                 | integer   | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                   |
| message              | string    | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed.。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                   |

### Return sample

```json
{
	"task-list": [{
		"task-id": "1",
		"task-name": "sync-test-1",
		"task-type": "upload",
		"task-group": "sync",
		"task-state": "start"
	}, {
		"task-id": 2,
		"task-name": "sync-test-2",
		"task-type": "download",
		"task-group": "sync",
		"task-state": "start"
	}],
	"code": 0,
	"message": "success"
}
```



## Get task transfer status

### Basic information

**Path：** /get-task-status

**Method：** POST

**Interface description:：**
<p>Get all information about a task based on the specified task ID.</p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |
**Body**

| Name    | Type   | Is it necessary | Default | Remark                                                                                                                                                                                              | Other information |
| ------- | ------ | --------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-id | string | Necessary       |         | Specify the task ID of the task to be obtained. Use "," to separate multiple task IDs; if this field is not specified or the field content is empty, the task status of all tasks will be obtained. |                   |

### Request sample

```json
{
	"task-id": "1,2,3"
}
```

### Return data


| Name                              | Type      | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Other information         |
| --------------------------------- | --------- | --------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| task-list                         | object [] | Necessary       |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | item type: object         |
| └─task-id                         | string    | Necessary       |         | Task ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                           |
| └─task-name                       | string    | Necessary       |         | Task name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                           |
| └─task-type                       | string    | Necessary       |         | Task type; upload: upload task; download: download task;；                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─task-group                      | string    | Necessary       |         | Task grouping; normal: normal tasks; sync: synchronization tasks, cluster tasks; p2p: direct transfer tasks;；                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                           |
| └─task-state                      | string    | Necessary       |         | Task status; ready: ready, the task is ready to be executed after creation; start: running; stopped: stopped; successful: successful; failed: failed; auth-failed: authentication failed; proxy-closed: proxy server connection failed; idle: Idle; stop-by-server: Stopped by the server; no-permission: Insufficient permissions; ip-locked: The IP address is locked; stop-by-peer: The other party stops transmission (direct transmission) failed-to-send: Direct transmission Failed; connection-failed: the direct connection failed; account-locked: the account is locked; |                           |
| └─file-max                        | integer   | Necessary       |         | The total number of files discovered.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                           |
| └─file-pos                        | integer   | Necessary       |         | Total number of files transferred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |
| └─file-failed                     | integer   | Necessary       |         | The total number of files that have failed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                           |
| └─size-max                        | integer   | Necessary       |         | Total size of discovered files.。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─size-pos                        | integer   | Necessary       |         | Total size of files transferred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─speed                           | integer   | Necessary       |         | Transmission speed, unit: Byte/s.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                           |
| └─elapsed-time                    | integer   | Necessary       |         | Total task execution time, unit: seconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─hash-pos                        | integer   | Necessary       |         | File size verified.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                           |
| └─hash-size-max                   | integer   | Necessary       |         | Check the total size of the file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                           |
| └─file-checking                   | boolean   | Necessary       |         | The task is verifying the file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                           |
| └─local-path                      | string [] | Necessary       |         | List of local paths.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | item type: string         |
| └─remote-path                     | string [] | Necessary       |         | List of server paths.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | item type: string         |
| └─avg-speed                       | float     | Necessary       |         | Returns average speed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                           |
| └─drop-rate                       | integer   | Necessary       |         | Return packet loss rate                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                           |
| └─enable-share-file-after-upload  | boolean   | Unnecessary     |         | Returns whether to enable sharing for others to download after the upload is completed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                           |
| └─share-emails                    | string    | Necessary       |         | Returns the recipient's email address, the email address used to receive the sharing link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─share-emails-content            | string    | Necessary       |         | Returns the recipient's email address, the email address used to receive the sharing link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─share-emails-password           | string    | Necessary       |         | Return the password for the shared link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                           |
| └─enable-sync-source-file-updated | boolean   | Necessary       |         | Whether to enable synchronization when the source file is updated, true means enabled, false otherwise                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
| └─end-time                        | string    | Necessary       |         | Return task end time                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                           |
| └─is-enabled                      | boolean   | Necessary       |         | Returns whether the task is disabled, true means disabled, false means enabled                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Disabled tasks do not run |
| └─mss                             | integer   | Necessary       |         | Return UDP packet size                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
| └─rtt                             | integer   | Necessary       |         | Return rtt value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─protocol-type                   | string    | Necessary       |         | Returns the protocol type of the transmission                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                           |
| code                              | integer   | Necessary       |         | Returns the error code of the operation, 0 on success and non-0 on failure.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                           |
| message                           | string    | Necessary       |         | Returns the error text information of the execution operation, returns "success" if successful, and returns the specific failure reason if failed.                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |


### Return sample


```json
{
    "code": 0,
    "message": "success",
    "task-list": [
        {
            "avg-speed": 2476978.0,
            "drop-rate": 0,
            "elapsed-time": 2,
            "enable-share-file-after-upload": false,
            "enable-sync-source-file-updated": false,
            "end-time": "2024-06-25 20:44:44",
            "file-checking": false,
            "file-failed": 0,
            "file-max": 1,
            "file-pos": 1,
            "group-id": 0,
            "hash-pos": 0,
            "hash-size-max": 0,
            "is-enabled": true,
            "local-path": [
                "C:\\Users\\Administrator\\153787_o_IMG_5283.JPG"
            ],
            "mss": 1200,
            "protocol-type": "udp",
            "remote-path": [
                "/"
            ],
            "rtt": 1,
            "share-emails": "",
            "share-emails-content": "",
            "share-emails-password": "",
            "show-name": "153787_o_IMG_5283.JPG|1|20240625153355647",
            "size-max": 2476978,
            "size-pos": 2476978,
            "space-id": 1,
            "speed": 1238489,
            "start-time": "2024-06-25 15:33:56",
            "task-group": "p2p",
            "task-id": "98",
            "task-name": "153787_o_IMG_5283.JPG|1|20240625153356267616900",
            "task-state": "successful",
            "task-type": "download",
            "trans-mode": 0,
            "use-ssl": false
        },
        {
            "avg-speed": 0.0,
            "drop-rate": 0,
            "elapsed-time": 0,
            "enable-share-file-after-upload": false,
            "enable-sync-source-file-updated": false,
            "end-time": "2024-06-25 20:50:22",
            "file-checking": false,
            "file-failed": 0,
            "file-max": 0,
            "file-pos": 0,
            "group-id": 0,
            "hash-pos": 0,
            "hash-size-max": 0,
            "is-enabled": true,
            "local-path": [
                "C:\\Users\\Administrator\\Downloads\\0621\\floppy.txt"
            ],
            "mss": 0,
            "protocol-type": "tcp",
            "remote-path": [
                "/"
            ],
            "rtt": 0,
            "share-emails": "",
            "share-emails-content": "",
            "share-emails-password": "",
            "show-name": "floppy.txt|1|20240624202724851454400",
            "size-max": 0,
            "size-pos": 0,
            "space-id": 1,
            "speed": 0,
            "start-time": "2024-06-25 20:50:22",
            "task-group": "p2p",
            "task-id": "75",
            "task-name": "floppy.txt|1|20240624202724851454400",
            "task-state": "p2p-id-offline",
            "task-type": "upload",
            "trans-mode": 0,
            "use-ssl": false
        }
    ]
}
```


## Get all task status
### Basic information

**Path：** /get-all-task-status

**Method：** POST

**Interface description:：**
<p>Get the information on all tasks. </p>


### Request parameter
**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |
**Body**

| Name                         | Type    | Is it necessary | Default | Remark                                                                                                                                                                                                                               | Other information |
| ---------------------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| filter                       | object  | Unnecessary     |         | Filter options. If omitted, all tasks are returned.                                                                                                                                                                                  |                   |
| └─task-group                 | string  | Unnecessary     | all     | Task group; all=all tasks; normal=normal tasks; sync=synchronization tasks and cluster transmission tasks; p2p=Peer to Peer transmission tasks. Also supports subgroup values returned by this API such as normal-uploading.        |                   |
| └─task-name                  | string  | Unnecessary     |         | Fuzzy match by task name. English letters are matched case-insensitively.                                                                                                                                                            |                   |
| └─task-status                | integer | Unnecessary     | 0       | Status filter; 0=all; 1=successful; 2=failed; 3=stopped/stopping; 4=transferring; 5=waiting.                                                                                                                                         |                   |
| └─task-create-start-time     | integer | Unnecessary     | 0       | Task create start time, Unix timestamp in seconds.                                                                                                                                                                                  |                   |
| └─task-create-end-time       | integer | Unnecessary     | 0       | Task create end time, Unix timestamp in seconds.                                                                                                                                                                                    |                   |
| └─current-page               | integer | Unnecessary     | 0       | Current page number. It must be specified together with page-size. If current-page and page-size are both 0 or omitted, pagination is disabled.                                                                                      |                   |
| └─page-size                  | integer | Unnecessary     | 0       | The number of records per page. It must be specified together with current-page.                                                                                                                                                     |                   |
| └─order                      | integer | Unnecessary     | 0       | Sort order; 0=default, 1=ascending, 2=descending.                                                                                                                                                                                    |                   |
| └─orderBy                    | string  | Unnecessary     |         | Sort field; task-create-time=sort by task create time. Other values or omitted means sort by position.                                                                                                                               |                   |

### Request sample

```json
{
  "filter": {
    "task-group": "all",
    "task-name": "zip",
    "task-status": 1,
    "task-create-start-time": 1719244800,
    "task-create-end-time": 1719331199,
    "current-page": 1,
    "page-size": 20,
    "order": 2,
    "orderBy": "task-create-time"
  }
}
```

### Return data

| Name                              | Type      | Is it necessary | Default | Remark                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Other information         |
| --------------------------------- | --------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| task-list                         | object [] | Necessary       |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | item Type: object         |
| └─task-id                         | string    | Necessary       |         | task ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                           |
| └─task-name                       | string    | Necessary       |         | Task name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                           |
| └─task-type                       | string    | Necessary       |         | Task Type; upload ： upload task; download ：download task;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                           |
| └─task-group                      | string    | Necessary       |         | Task grouping; normal ：normal task; sync ：sync task, cluster task; p2p ：P2P transfer task;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
| └─task-state                      | string    | Necessary       |         | Task status ; ready ：The tasks have been created and prepared to transfer; start ：Tasks are transferring; stopped ：Tasks stopped transferring; successful ：Tasks are successfully transferred; failed ：Failed to transfer tasks; auth-failed ：The authentication failed; proxy-closed ：The proxy server connection failed idle ：The task is not triggered to transfer stop-by-server ：Tasks transfer is stopped by server; no-permission ：Permission limitation; ip-locked ：The IP address is locked; stop-by-peer ：The P2P transfer is stopped by peer; failed-to-send ：The P2P transfer failed to send; connection-failed ：The P2P transfer connection failed; account-locked ：The account is locked. |                           |
| └─file-max                        | integer   | Necessary       |         | The total number of files found.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
| └─file-pos                        | integer   | Necessary       |         | The total number of files transferred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |
| └─file-failed                     | integer   | Necessary       |         | The total number of files that have failed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
| └─size-max                        | integer   | Necessary       |         | The total size of the files found.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                           |
| └─size-pos                        | integer   | Necessary       |         | The total size of files transferred.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─speed                           | integer   | Necessary       |         | Transmission speed, unit: Byte/s.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                           |
| └─elapsed-time                    | integer   | Necessary       |         | The total time for task execution, unit: second.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
| └─hash-pos                        | integer   | Necessary       |         | The size of the file has been verified.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                           |
| └─hash-size-max                   | integer   | Necessary       |         | The total size of the Hash verification file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─file-checking                   | boolean   | Necessary       |         | The task is checking files.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                           |
| └─local-path                      | string [] | Necessary       |         | List of local paths.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | item Type: string         |
| └─remote-path                     | string [] | Necessary       |         | Server path list.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | item Type: string         |
| └─avg-speed                       | float     | Necessary       |         | Return average speed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─drop-rate                       | integer   | Necessary       |         | Return packet loss rate                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                           |
| └─enable-share-file-after-upload  | boolean   | Necessary       |         | Return whether to enable sharing for others to download after the upload is completed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |
| └─share-emails                    | string    | Unnecessary     |         | Return Recipient email address, the email address used to receive the sharing link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                           |
| └─share-emails-content            | string    | Unnecessary     |         | Return Email message content                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                           |
| └─share-emails-password           | string    | Necessary       |         | Return Password for sharing link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
| └─enable-sync-source-file-updated | boolean   | Necessary       |         | Return Whether to enable synchronization when the source file is updated, true means enabled, false otherwise                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                           |
| └─enable-remove-on-completed      | boolean   | Necessary       |         | Return whether to automatically delete source files after file transfer is completed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─move-source-file                | object    | Necessary       |         | Return the source-file move and cleanup settings for synchronization tasks.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
|   └─enable-move-source-file       | boolean   | Necessary       |         | Return whether moving the source file is enabled.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
|   └─move-source-file-minutes      | integer   | Necessary       |         | Return the move delay in minutes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
|   └─move-source-file-hours        | integer   | Necessary       |         | Return the same move delay converted to whole hours for compatibility with older callers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                           |
|   └─move-source-file-target-path  | string    | Necessary       |         | Return the destination used when moving source files.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                           |
|   └─remove-source-file-days       | integer   | Necessary       |         | Return the cleanup delay after moving source files, in days.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                           |
| └─end-time                        | string    | Necessary       |         | Return Task end time                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                           |
| └─is-enabled                      | boolean   | Necessary       |         | Return Whether the task is disabled, true means disabled, false means enabled                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Disabled tasks do not run |
| └─mss                             | integer   | Necessary       |         | Return UDP packet size                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |
| └─rtt                             | integer   | Necessary       |         | Return rtt value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                           |
| └─protocol-type                   | string    | Necessary       |         | Return the protocol type of the transmission                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                           |
| code                              | integer   | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                           |
| message                           | string    | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                           |

### Return sample

```json
{
  "task-list": [
    {
            "avg-speed": 0.0,
            "drop-rate": 0,
            "elapsed-time": 0,
            "enable-share-file-after-upload": false,
            "enable-sync-source-file-updated": false,
            "enable-remove-on-completed": false,
            "move-source-file": {
                "enable-move-source-file": true,
                "move-source-file-minutes": 30,
                "move-source-file-hours": 0,
                "move-source-file-target-path": "D:/archive",
                "remove-source-file-days": 7
            },
            "end-time": "2024-06-25 20:44:44",
            "file-checking": false,
            "file-failed": 1,
            "file-max": 1,
            "file-pos": 0,
            "group-id": 0,
            "hash-pos": 0,
            "hash-size-max": 0,
            "is-enabled": true,
            "local-path": [
                "H:\\0\\1"
            ],
            "mss": 1200,
            "protocol-type": "udp",
            "remote-path": [
                "/66"
            ],
            "rtt": 1,
            "share-emails": "",
            "share-emails-content": "",
            "share-emails-password": "",
            "show-name": "123",
            "size-max": 0,
            "size-pos": 0,
            "space-id": 2,
            "speed": 0,
            "start-time": "2024-06-25 18:28:29",
            "task-group": "sync",
            "task-id": "33",
            "task-name": "123",
            "task-state": "failed",
            "task-type": "upload",
            "trans-mode": 0,
            "triggering-condition": {
                "clock": "20:15",
                "type": "clock"
            },
            "use-ssl": false
        },
    {
            "avg-speed": 10990.0,
            "drop-rate": 0,
            "elapsed-time": 2,
            "enable-share-file-after-upload": false,
            "enable-sync-source-file-updated": false,
            "end-time": "2024-06-25 20:44:44",
            "file-checking": false,
            "file-failed": 0,
            "file-max": 1,
            "file-pos": 1,
            "group-id": 0,
            "hash-pos": 0,
            "hash-size-max": 0,
            "is-enabled": true,
            "local-path": [
                "C:\\Users\\51D95B42AFDA.txt"
            ],
            "mss": 1200,
            "protocol-type": "udp",
            "remote-path": [
                "/"
            ],
            "rtt": 1,
            "share-emails": "",
            "share-emails-content": "",
            "share-emails-password": "",
            "show-name": "689975400",
            "size-max": 10990,
            "size-pos": 10990,
            "space-id": 2,
            "speed": 5495,
            "start-time": "2024-06-24 20:12:15",
            "task-group": "p2p",
            "task-id": "25",
            "task-name": "32DFE387",
            "task-state": "successful",
            "task-type": "upload",
            "trans-mode": 0,
            "use-ssl": false
        }
  ],
  "code": 0,
  "message": "success"
}
```



## Get file list count

### Basic information

**Path：** /get-file-list-count

**Method：** POST

**Interface description:：**

<p>Get the total count of file lists under the task ID and specified Type.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

 **Body**       

| Name      | Type   | Is it necessary | Default | Remark                                                                                                                      | Other information |
| --------- | ------ | --------------- | ------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-id   | string | Necessary       |         | task ID.                                                                                                                    |                   |
| list-type | string | Necessary       |         | Specify the list of lists that need to be obtained. all=all file lists; start=is being transmitted list; error=failed list; |                   |


### Request sample

```json
{
  "task-id": "1",
  "list-type": "all"
}
```

### Return data

| Name      | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| --------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| task-list | integer | Necessary       |         | Returns the total number of lists specified Type.                                                                                                       |                   |
| code      | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message   | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
  "task-list": 100,
  "code": 0,
  "message": "success"
}
```



## Get file list 

### Basic information

**Path：** /get-file-list

**Method：** POST

**Interface description:：**

<p>Get all the file list under the task ID and specified Type.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

 **Body**       

| Name        | Type    | is it necessary | Default | Remark                                                       | Other information |
| ----------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| task-id     | string  | Necessary       |         | task ID.                                                     |                   |
| list-type   | string  | Necessary       |         | Specify the list of lists that need to be obtained. all=all file lists; start=is being transmitted list; error=failed list; wait= wait for transfer list; complete= completed list |                   |
| page-size   | integer | Necessary       |         | The number of records of each page.                          |                   |
| page-number | integer | Necessary       |         | page number.                                                 |                   |

### Request sample

```json
{
  "task-id": "1",
  "list-type": "all",
  "page-size": 10,
  "page-number": 1
}
```

### Return data

| Name           | Type      | Is it necessary | Default | Remark                                                       | Other information |
| -------------- | --------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| file-list      | object [] | Necessary       |         |                                                              | item Type: object |
| └─ local-path  | string    | Necessary       |         | Local path.                                                  |                   |
| └─ remote-path | string    | Necessary       |         | Server path.                                                 |                   |
| └─ is-folder   | boolean   | Necessary       |         | Whether the path is a directory.                             |                   |
| └─ size        | integer   | Necessary       |         | Total file size.unit: Byte.                                  |                   |
| └─ pos         | integer   | Necessary       |         | Transmission speed, unit: Byte/s.                            |                   |
| └─ write-time  | integer   | Necessary       |         | The modification timestamp of the file since 1970-01-01.     |                   |
| └─ state       | string    | Necessary       |         | File transfer status. waiting=Not started, waiting for transmission; start=Has started and is transmitting; end=finished; failed=Failed. Obtain the failure cause based on the error-code field. |                   |
| └─ error-code  | integer   | Necessary       |         | Reason for file failure. For details, see "Error Code Description" below. |                   |
| code           | integer   | Necessary       |         | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message        | string    | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| file-count     | integer   | Necessary       |         | Returns the total number of lists of this type.              |                   |

## Error code description

| Error code name                         | error code value | wrong reason                                                                                             |
| --------------------------------------- | ---------------- | -------------------------------------------------------------------------------------------------------- |
| ERROR_NOERROR                           | 0                | No error occurred                                                                                        |
| ERROR_OTHER                             | 1                | Undefined error                                                                                          |
| ERROR_CAN_NOT_OPEN_FILE                 | 2                | The file cannot be opened, the file is protected or the file does not exist                              |
| ERROR_CAN_NOT_OPEN_LOCAL_FILE           | 3                | Can't open local file                                                                                    |
| ERROR_FILE_NOT_EXISTS                   | 4                | File does not exist                                                                                      |
| ERROR_FILE_ID_IS_VALID                  | 5                | The ID used already exists                                                                               |
| ERROR_LOSE_OBJECT                       | 6                | START is not sent before sending DATA                                                                    |
| ERROR_FILE_END                          | 7                | It has been set up to still send data after the file sending is completed.                               |
| ERROR_SIZE_NOT_EQUAL                    | 8                | File size mismatch                                                                                       |
| ERROR_CAN_NOT_WRITE_FILE                | 9                | Cannot write to disk                                                                                     |
| ERROR_CAN_NOT_DELETE_FILE               | 10               | Can't delete file                                                                                        |
| ERROR_INTERNAL_ERR                      | 11               | Program internal logic error                                                                             |
| ERROR_STOP_BY_CLIENT                    | 12               | Client stops transmitting                                                                                |
| ERROR_AUTH_FAILURE                      | 13               | Authentication failed, username or password is wrong                                                     |
| ERROR_PATH_IS_NOT_FILE                  | 14               | The specified path is not a file                                                                         |
| ERROR_CAN_NOT_MK_DIR                    | 15               | Unable to create destination folder                                                                      |
| ERROR_NO_PERMISSION                     | 16               | Insufficient user rights                                                                                 |
| ERROR_AUTH_SERVICE_ERR                  | 17               | The authentication server is abnormal, timed out or returned abnormal data.                              |
| ERROR_LOSE_STORAGE                      | 18               | Storage path is lost                                                                                     |
| ERROR_LIMIT_UPLOAD                      | 19               | Restricted uploads, insufficient traffic or arrears                                                      |
| ERROR_LIMIT_DOWNLOAD                    | 20               | Restrict downloads, insufficient traffic or arrears                                                      |
| ERROR_PATH_NOFOUND                      | 21               | path does not exist                                                                                      |
| ERROR_ON_CLOSE                          | 22               | An error occurred while closing the file after uploading                                                 |
| ERROR_ACCOUNT_IS_LOCKED                 | 23               | User is locked                                                                                           |
| ERROR_NAME_NOT_SAFETY                   | 24               | The file name is not safe                                                                                |
| ERROR_PATH_EXISTS                       | 25               | Target path already exists                                                                               |
| ERROR_STOP_BY_SERVER                    | 26               | Server stops transmitting                                                                                |
| ERROR_HASH_FAULT                        | 27               | Hash verification error                                                                                  |
| ERROR_IP_IS_LOCKED                      | 28               | IP locked                                                                                                |
| ERROR_FILE_BUSY                         | 29               | File is being occupied                                                                                   |
| ERROR_DISCONNECT                        | 30               | The connection to the peer is disconnected                                                               |
| ERROR_PARAM_ERROR                       | 31               | Parameter error                                                                                          |
| ERROR_NO_RSYNC                          | 32               | Unable to perform rsync check                                                                            |
| ERROR_P2P_ID_NOT_FOUND                  | 33               | Object not found                                                                                         |
| ERROR_P2P_KEY_INCORRECT                 | 34               | The entered key is incorrect                                                                             |
| ERROR_P2P_OTHER_REGISTER                | 35               | The ID is registered by another connection, notifying that the previous registration has been cancelled. |
| ERROR_LOCAL_STOP                        | 36               | Stop task locally                                                                                        |
| ERROR_WAIT_PEER                         | 37               | Waiting for client to connect                                                                            |
| ERROR_FILE_SYSTEM_ERR                   | 38               | File system error                                                                                        |
| ERROR_UNSUPPORTED_OPERATION             | 39               | Unsupported operation                                                                                    |
| ERROR_CAN_NOT_OPEN_REMOTE_FILE          | 40               | Unable to open remote file                                                                               |
| ERROR_PATH_IS_FILE                      | 41               | The specified path is a file                                                                             |
| ERROR_CAN_NOT_READ_FILE                 | 42               | Can't read file                                                                                          |
| ERROR_RS_INVALID_DATA                   | 43               | Invalid data                                                                                             |
| ERROR_NOT_SUPPORT_FEATURE               | 44               | This feature is not supported                                                                            |
| ERROR_COMPRESS_FILE_FAILED              | 45               | Compressed file failed                                                                                   |
| ERROR_DETECTED_VIRUS                    | 46               | Virus detected                                                                                           |
| ERROR_SQL_GET_RECORD_FAILED             | 47               | Failed to get database records                                                                           |
| ERROR_SQL_DELETE_RECORD_FAILED          | 48               | Failed to delete database record                                                                         |
| ERROR_EMPTY_RECYCLE_BIN_FAILED          | 49               | Failed to empty recycle bin                                                                              |
| ERROR_FILE_SKIPPED                      | 50               | File skipped                                                                                             |
| ERROR_SENSITIVEWORD                     | 51               | Sensitive words                                                                                          |
| ERROR_LICENSE_EXPIRED                   | 52               | license invalid                                                                                          |
| ERROR_MODIFY_CACHE_FILE                 | 53               | Cache file modification failed                                                                           |
| ERROR_NO_SPACE_LEFT_ONDEVICE            | 54               | Not enough disk space                                                                                    |
| ERROR_INIT_P2P_CLIENT_FAILED            | 55               | p2p sender transmission failed                                                                           |
| ERROR_INIT_P2P_SERVER_FAILED            | 56               | p2p receiver transmission failed                                                                         |
| ERROR_FILE_INCONSISTENCY                | 57               | Files are inconsistent                                                                                   |
| ERROR_PATH_IS_FOLDER                    | 58               | The path is a folder                                                                                     |
| ERROR_INSUFFICIENT_STORAGE_BALANCE      | 59               | Insufficient storage balance                                                                             |
| ERROR_DISABLED_BY_SERVER                | 60               | Server disables transfer                                                                                 |
| ERROR_EXTRACT_FILE_FAILED               | 61               | Failed to decompress file                                                                                |
| ERROR_UPLOADING_FILE_UNSUPPORT_DOWNLOAD | 62               | Unfinished files cannot be downloaded                                                                    |
| ERROR_FILE_RESOTRE_FAILED               | 63               | File restore failed                                                                                      |
| ERROR_P2P_ID_OFFLINE                    | 64               | Peer to Peer ID Offline                                                                                  |
| ERROR_LOCAL_TOO_MANY_OPEN_FILES         | 65               | Too many local files open                                                                                |
| ERROR_REMOTE_TOO_MANY_OPEN_FILES        | 66               | Too many remote files are opened                                                                         |
| ERROR_LOCAL_FILE_NO_PERMISSION          | 67               | Local files have no permissions                                                                          |
| ERROR_REMOTE_FILE_NO_PERMISSION         | 68               | The remote file has no permissions                                                                       |
| ERROR_REMOTE_PATH_NOT_FOLDER            | 69               | The remote path is not a folder                                                                          |
| ERROR_REMOTE_PATH_IS_FOLDER             | 70               | The remote path is a folder                                                                              |
| ERROR_LOCAL_FILE_NOT_EXISTS             | 71               | The local file does not exist                                                                            |
| ERROR_REMOTE_FILE_NOT_EXISTS            | 72               | The remote file does not exist                                                                           |
| ERROR_P2P_SERVICE_STATUS_STOP           | 73               | P2P service exception                                                                                    |


### Return sample

```json
{
  "file-list": [
    {
      "local-path": "/root/1.txt",
      "remote-path": "/1.txt",
      "is-folder": false,
      "size": 100,
      "pos": 50,
      "write-time": 1632415039,
      "state": "start",
      "error-code": 0
    }
  ],
  "code": 0,
  "message": "success",
  "file-count": 1
}
```


## Set the maximum number of simultaneous transfer tasks

### Basic information

**Path：** /set-task-limit

**Method：** POST

**Interface description:：**

<p>Set the limit on the number of common tasks/point-to-point tasks that are allowed to be uploaded and downloaded at the same time. Tasks that exceed the number will be queued to wait.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                           | Type    | Is it necessary | Default | Remark                                                                                                                                                                                | Other information |
| ------------------------------ | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| upload                         | integer | Necessary       | 0       | Specify the maximum number of upload tasks that can be started at the same time. Value range: [1, 20].                                                                                |                   |
| download                       | integer | Necessary       | 0       | Specify the maximum number of download tasks that can be started at the same time. Value range: [1, 20].                                                                              |                   |
| num-of-parallel-trans-per-task | integer | Unnecessary     | 0       | Specify the number of files transferred by a single task. 0 is automatic, the number of CPU cores is automatically selected. The values ​​that can be set are "0 1 2 4 6 8 10 16 32". |                   |


### Request sample

```json
{
	"upload": 20,
	"download": 20
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
}
```



## Get the maximum number of simultaneous transfer tasks 

### Basic information

**Path：** /get-task-limit

**Method：** POST

**Interface description:：**

<p>Get the limit on the number of common tasks/peer-to-peer tasks allowed to be uploaded and downloaded at the same time. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name                           | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------------------------------ | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code                           | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message                        | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| upload                         | integer | Necessary       | 0       | Returns the maximum number of upload tasks started at the same time.                                                                                    |                   |
| download                       | integer | Necessary       | 0       | Returns the maximum number of download tasks started at the same time.                                                                                  |                   |
| num-of-parallel-trans-per-task | integer | Unnecessary     | 0       | Returns the number of files transferred by a single task                                                                                                |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"upload": 2,
	"download": 2,
	"num-of-parallel-trans-per-task": 0
}
```



## Set transfer parameters

### Basic information

**Path：** /set-transmission-parameters

**Method：** POST

**Interface description:：**

<p>Modifying the transfer parameters. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name               | Type    | Is it necessary | Default | Remark                                                                                    | Other information                              |
| ------------------ | ------- | --------------- | ------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------- |
| mss                | integer | Unnecessary     | 0       | Set the maximum size of UDP packets for transmission using UDP. Value range: [600, 1442]. |                                                |
| max-upload-speed   | integer | Unnecessary     | 0       | Set the maximum upload speed, unit: Mbps; 0 means no limit;                               |                                                |
| max-download-speed | integer | Unnecessary     | 0       | Set the maximum download speed, unit: Mbps; 0 means no limit;                             |                                                |
| min-upload-speed   | integer | Unnecessary     | 0       | Set the minimum upload speed, unit: Mbps; 0 means no limit；                               |                                                |
| min-download-speed | integer | Unnecessary     |         | Set the minimum receiving speed, unit: Mbps; 0 means no limit                             |                                                |
| set-rate           | boolean | Necessary       |         | Whether to set the maximum speed                                                          | Used with max-upload-speed, max-download-speed |
| set-min-speed      | boolean | Necessary       |         | Whether to set minimum speed                                                              | Used with min-upload-speed, min-download-speed |
| enable-p2p-server-smart-speed | boolean | Unnecessary | false | Whether to enable smart-speed control for P2P receiver tasks.                         |                                                |
| p2p-server-fast-task-count | integer | Unnecessary | 0 | Number of P2P receiver tasks assigned to the fast tier; values below 0 are treated as 0.       |                                                |
| p2p-server-fast-upload-speed | integer | Unnecessary | 0 | Fast-tier upload speed, unit: Mbps; 0 means no limit.                                          |                                                |
| p2p-server-fast-download-speed | integer | Unnecessary | 0 | Fast-tier download speed, unit: Mbps; 0 means no limit.                                      |                                                |
| p2p-server-slow-upload-speed | integer | Unnecessary | 0 | Slow-tier upload speed, unit: Mbps; 0 means no limit.                                          |                                                |
| p2p-server-slow-download-speed | integer | Unnecessary | 0 | Slow-tier download speed, unit: Mbps; 0 means no limit.                                      |                                                |


### Request sample

```json
{
	"mss": 1200,
	"max-upload-speed": 0,
	"max-download-speed": 0,
	"min-upload-speed": 0,
	"min-download-speed": 0,
	"set-rate": false,
	"set-min-speed": false,
	"enable-p2p-server-smart-speed": true,
	"p2p-server-fast-task-count": 1,
	"p2p-server-fast-upload-speed": 100,
	"p2p-server-fast-download-speed": 100,
	"p2p-server-slow-upload-speed": 10,
	"p2p-server-slow-download-speed": 10
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.           |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get transfer parameters

### Basic information

**Path：** /get-transmission-parameters

**Method：** POST

**Interface description:：**

<p>Get the transfer parameters. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name               | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------------------ | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code               | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message            | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| mss                | integer | Necessary       | 0       | Returns the maximum size of a UDP packet for transmission using UDP.                                                                                    |                   |
| max-upload-speed   | integer | Necessary       | 0       | Returns the maximum upload speed, unit: Mbps; 0 means no limit;                                                                                         |                   |
| max-download-speed | integer | Necessary       | 0       | Returns the maximum download speed, unit: Mbps; 0 means no limit；                                                                                       |                   |
| min-upload-speed   | integer | Necessary       | 0       | Return the minimum upload speed, unit: Mbps; 0 means no limit;                                                                                          |                   |
| min-download-speed | integer | Necessary       |         | Returns the minimum sending speed, unit: Mbps; 0 is unlimited                                                                                           |                   |
| set-rate<br>       | boolean | Necessary       |         | Returns whether to set the maximum speed                                                                                                                |                   |
| set-min-speed      | boolean | Necessary       |         | Returns whether to set the maximum speed                                                                                                                |                   |
| enable-p2p-server-smart-speed | boolean | Necessary | false | Returns whether smart-speed control for P2P receiver tasks is enabled.                                                                               |                   |
| p2p-server-fast-task-count | integer | Necessary | 0 | Returns the number of P2P receiver tasks assigned to the fast tier.                                                                                         |                   |
| p2p-server-fast-upload-speed | integer | Necessary | 0 | Returns the fast-tier upload speed, unit: Mbps.                                                                                                           |                   |
| p2p-server-fast-download-speed | integer | Necessary | 0 | Returns the fast-tier download speed, unit: Mbps.                                                                                                       |                   |
| p2p-server-slow-upload-speed | integer | Necessary | 0 | Returns the slow-tier upload speed, unit: Mbps.                                                                                                           |                   |
| p2p-server-slow-download-speed | integer | Necessary | 0 | Returns the slow-tier download speed, unit: Mbps.                                                                                                       |                   |



### Return sample

```json
{
    "code":0,
     "message":"success",
	 "max-download-speed":0,
	 "max-upload-speed":0,
	 "min-download-speed":0,
	 "min-upload-speed":0,
	 "mss":1200,
	 "set-min-speed":false,
	 "set-rate":false,
	 "enable-p2p-server-smart-speed":true,
	 "p2p-server-fast-task-count":1,
	 "p2p-server-fast-upload-speed":100,
	 "p2p-server-fast-download-speed":100,
	 "p2p-server-slow-upload-speed":10,
	 "p2p-server-slow-download-speed":10
 }
```



## Set advanced parameters

### Basic information

**Path：** /set-advanced-parameters

**Method：** POST

**Interface description:：**

<p>Modifying the advanced setting.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name                           | Type    | Is it necessary | Default | Remark                                                       | Other information                                            |
| ------------------------------ | ------- | --------------- | ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| enable-compress                | boolean | Unnecessary     | true    | Whether to enable data compression. <br/>When it is turned on, it will try to compress the file data. If the compressed data is smaller than the original data, the compressed data is transmitted; if the compressed data is larger than the original data, the original data is transmitted. Both the server and the client must enable the compression function to take effect. |                                                              |
| enable-save-timestamp          | boolean | Unnecessary     | true    | Whether to keep the time stamp information of the transferred file. |                                                              |
| enable-tcp-first               | boolean | Unnecessary     | false   | The TCP protocol is preferred to establish a connection with the server, and if it fails to connect, it will switch to the UDP protocol. |                                                              |
| enable-ssl                     | boolean | Unnecessary     | false   | Whether to use encryption protocol to establish connection with file server. |                                                              |
| enable-verify-hash             | boolean | Unnecessary     | false   | Whether to enable Hash verification.<br/>When it is turned on, the source and target files will be Hash checked before the transfer starts and after the transfer is completed. |                                                              |
| enable-rsync                   | boolean | Unnecessary     | false   | Whether to enable rsync to verify transmission.              |                                                              |
| enable-download-new-files-only | boolean | Unnecessary     | false   | Whether to enable downloading only new files.                |                                                              |
| timeout                        | integer | Unnecessary     | 10      | The timeout period for connecting to the server and logging in, in seconds. The minimum value is 20 seconds. |                                                              |
| check-before-transfer          | object  | Unnecessary     |         | Verification is performed before starting the transmission, and the transmission is not started until the file has no changes within (3~30) seconds. |                                                              |
| └─enable-check                 | boolean | Unnecessary     |         | Whether to enable pre-transmission verification. true means enabled, false means vice versa. |                                                              |
| └─ check-time                  | integer | Unnecessary     |         | Whether to enable pre-transmission verification. true means enabled, false means vice versa. |                                                              |
| download-link-only             | boolean | Unnecessary     |         | Whether to enable download link files                        | This parameter is only supported on Linux and Mac OS systems. |
| enable-full-path               | boolean | Unnecessary     |         | Whether to enable uploading to the target to retain the complete structure of the source directory |                                                              |
| enable-save-acl                | boolean | Unnecessary     |         | Whether to enable retaining file ACL attributes              | Only supports retention on the same system                   |
| reconnection-setting           | object  | Unnecessary     |         | Task retry setting                                           |                                                              |
| └─ enable-reconnection         | boolean | Unnecessary     |         | Whether to enable task retry. true: Enabled; false: disabled. |                                                              |
| └─ maximum-retry               | integer | Unnecessary     |         | Retry times                                                  |                                                              |
| └─ retry-delay                 | integer | Unnecessary     |         | Retry delay time                                             |                                                              |


### Request sample

```json
{
  "enable-compress": true,
  "enable-save-timestamp": true,
  "enable-tcp-first": false,
  "enable-ssl": false,
  "enable-verify-hash": false,
  "enable-rsync": false,
  "enable-download-new-files-only": false,
  "timeout": 20,
  "reconnection-setting":{
    "enable-reconnection":true,
    "maximum-retry":3,
    "retry-delay":5
  }
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get advanced parameters

### Basic information

**Path：** /get-advanced-parameters

**Method：** POST

**Interface description:：**

<p>Get the advanced setting. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name                           | Type    | Is it necessary | Default | Remark                                                       | Other information                                            |
| ------------------------------ | ------- | --------------- | ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| code                           | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                                                              |
| message                        | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                                                              |
| enable-compress                | boolean | Necessary       | true    | Returns whether data compression is enabled.                 |                                                              |
| enable-save-timestamp          | boolean | Necessary       | true    | Returns Whether to keep the time stamp information of the transferred file. |                                                              |
| enable-tcp-first               | boolean | Necessary       | false   | Returns whether to enable the TCP protocol first to establish a connection with the server. |                                                              |
| enable-ssl                     | boolean | Necessary       | false   | Returns whether to use encryption protocol to establish connection with file server. |                                                              |
| enable-verify-hash             | boolean | Necessary       | false   | Returns whether to enable Hash verification.                 |                                                              |
| enable-rsync                   | boolean | Necessary       | false   | Returns whether to enable rsync verification.                |                                                              |
| enable-download-new-files-only | boolean | Necessary       | false   | Returns whether to enable download of new files only.        |                                                              |
| timeout                        | integer | Necessary       | 0       | Returns the timeout duration for connecting to the server and logging in, in seconds. |                                                              |
| check-before-transfer          | object  | Unnecessary     |         | Returns whether to enable verification before starting transmission. The transmission will not start until the file does not change within (3~30) seconds. |                                                              |
| └─enable-check                 | boolean | Unnecessary     |         | Returns whether to enable pre-transmission verification. true means enabled, false means vice versa. |                                                              |
| └─ check-time                  | integer | Unnecessary     |         | Returns whether there is no change in the number of seconds after opening the file before starting the transfer. The range is 3~30. |                                                              |
| download-link-only             | boolean | Unnecessary     |         | Returns whether to enable download link file                 | This parameter is only supported on Linux and Mac OS systems. |
| enable-full-path               | boolean | Unnecessary     |         | Returns whether to enable uploading to the target and retain the complete structure of the source directory. |                                                              |
| enable-save-acl                | boolean | Unnecessary     |         | Returns whether to enable retaining file ACL attributes.     | Only supports retention on the same system                   |
| reconnection-setting           | object  | Unnecessary     |         | Returns whether to enable the number of retry times.         |                                                              |
| └─ enable-reconnection         | boolean | Unnecessary     |         | Returns whether to enable Enable retry times. true: Enable; false: Disable. |                                                              |
| └─ maximum-retry               | integer | Unnecessary     |         | Returns the maximum number of retries.                       |                                                              |
| └─ retry-delay                 | integer | Unnecessary     |         | Return the maximum retry delay.                              |                                                              |



### Return sample

```json
{
    "check-before-transfer": {
        "check-time": 0,
        "enable-check": false
    },
    "code": 0,
    "download-link-only": false,
    "enable-compress": true,
    "enable-download-new-files-only": false,
    "enable-full-path": false,
    "enable-rsync": false,
    "enable-save-acl": false,
    "enable-save-timestamp": true,
    "enable-ssl": false,
    "enable-tcp-first": false,
    "enable-verify-hash": false,
    "message": "success",
    "timeout": 10,
    "reconnection-setting":{
        "enable-reconnection":true,
        "maximum-retry":3,
        "retry-delay":5
    }
    
}
```



## Set proxy server parameters 

### Basic information

**Path：** /set-proxy-parameters

**Method：** POST

**Interface description:：**

<p>Set whether to connect to the server through a proxy. Support the Socks5 proxy.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name           | Type    | Is it necessary | Default | Remark                                                                                  | Other information                                                                     |
| -------------- | ------- | --------------- | ------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| proxy-type     | string  | Necessary       |         | The proxy server type.<br>none ：Not use the proxy server;<br>socks5：Socks5 proxy server | When the proxy-type is socks5, the proxy-host and proxy-port parameters are required. |
| proxy-host     | string  | Unnecessary     |         | The address or domain name of the proxy server.                                         |                                                                                       |
| proxy-port     | integer | Unnecessary     | 0       | The port of the proxy server.                                                           |                                                                                       |
| proxy-account  | string  | Unnecessary     |         | The account for logging in to the proxy server.                                         |                                                                                       |
| proxy-password | string  | Unnecessary     |         | The password for logging in to the proxy server.                                        |                                                                                       |


### Request sample

```json
{
	"proxy-type": "socks5",
	"proxy-host": "192.168.1.1",
	"proxy-port": 1080,
	"proxy-account": "test",
	"proxy-password": "123"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get the proxy server parameters

### Basic information

**Path：** /get-proxy-parameters

**Method：** POST

**Interface description:：**

<p>Get the proxy configuration. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name           | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| -------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code           | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message        | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| proxy-type     | string  | Necessary       |         | The proxy server type.<br/>none ：Not use the proxy server;<br/>socks5：Socks5 proxy server;                                                              |                   |
| proxy-host     | string  | Necessary       |         | Return to the address or domain name of the proxy server                                                                                                |                   |
| proxy-port     | integer | Necessary       |         | Return to the port of the proxy server.                                                                                                                 |                   |
| proxy-account  | string  | Necessary       |         | Return to the account for logging in to the proxy server.                                                                                               |                   |



### Return sample

```json
{
	"code": 0,
	"message": "success",
	"proxy-type": "socks5",
	"proxy-host": "192.168.1.1",
	"proxy-port": 1080,
	"proxy-account": "test"
}
```



## Set external proxy parameters

### Basic information

**Path：** /set-external-proxy-parameters

**Method：** POST

**Interface description:：**

<p>Set whether to connect to the server through an external proxy server. After enabling it, the acceleration service will no longer be started locally and implemented through the external proxy server. Supports Socks5 type proxy. You must use the proxy tool provided by Raysync.</p>

### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name           | Type    | Is it necessary | Default | Remark                                                                                   | Other information |
| -------------- | ------- | --------------- | ------- | ---------------------------------------------------------------------------------------- | ----------------- |
| proxy-type     | string  | Necessary       |         | The proxy server type.<br>none ：Not use the proxy server;<br>socks5：Socks5 proxy server; |                   |
| proxy-host     | string  | Unnecessary     |         | Return to the address or domain name of the proxy server                                 |                   |
| proxy-port     | integer | Unnecessary     | 0       | Return to the port of the proxy server.                                                  |                   |
| proxy-account  | string  | Unnecessary     |         | Return to the account for logging in to the proxy server.                                |                   |
| proxy-password | string  | Unnecessary     |         | Return to the password for logging in to the proxy server.                               |                   |


### Request sample

```json
{
	"proxy-type": "socks5",
	"proxy-host": "192.168.1.1",
	"proxy-port": 1080,
	"proxy-account": "test",
	"proxy-password": "123"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get external proxy paramete

### Basic information

**Path：** /get-external-proxy-parameters

**Method：** POST

**Interface description:：**

<p>Get external proxy paramete</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name           | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| -------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code           | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message        | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| proxy-type     | string  | Necessary       |         | The proxy server type.<br/>none ：Not use the proxy server;<br/>socks5：Socks5 proxy server;                                                              |                   |
| proxy-host     | string  | Necessary       |         | Return to the address or domain name of the proxy serve                                                                                                 |                   |
| proxy-port     | integer | Necessary       |         | Return to the port of the proxy server.                                                                                                                 |                   |
| proxy-account  | string  | Necessary       |         | Return to the account for logging in to the proxy server.                                                                                               |                   |



### Return sample

```json
{
	"code": 0,
	"message": "success",
	"proxy-type": "socks5",
	"proxy-host": "192.168.1.1",
	"proxy-port": 1080,
	"proxy-account": "test"
}
```



## Set P2P transfer parameters

### Basic information

**Path：** /set-p2p-parameters

**Method：** POST

**Interface description:：**

<p>Set P2P transfer parameters.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name      | Type    | Is it necessary | Default | Remark                               | Other information |
| --------- | ------- | --------------- | ------- | ------------------------------------ | ----------------- |
| renew-id  | boolean | Unnecessary     | false   | Whether to reinitialize a new receiver ID for P2P transfer. |                   |
| root-path | string  | Unnecessary     |         | Set the default paths for P2P transfer sending and receiving.   |                   |


### Request sample

```json
{
	"renew-id": false,
	"root-path": "/root/p2p"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.          |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed.  |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get the P2P transfer parameters 

### Basic information

**Path：** /get-p2p-parameters

**Method：** POST

**Interface description:：**

<p>Get the P2P transfer parameters. </p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | -------- | ------ | ---- | -------- |


### Request sample

```json
{}
```

### Return data

| Name      | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| --------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code      | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message   | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| p2p-id    | string  | Necessary       |         | Return to the P2P transfer ID of the receiver.                                                                                                          |                   |
| root-path | string  | Necessary       |         | Return to the default paths for P2P transfer sending and receiving.                                                                                     |                   |
| status    | boolean | Necessary       |         | Returns whether permission to receive files is enabled                                                                                                  |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"p2p-id": "1234567890",
	"root-path": "/root/p2p",
	"status":true
}
```



## Set P2P browse config

### Basic information

**Path：** /set-p2p-browse-config

**Method：** POST

**Interface description:：**

<p>Set the configured idle release timeout for P2P browse sessions.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                    | Type    | Is it necessary | Default | Remark                                                                                                        | Other information |
| ----------------------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------- | ----------------- |
| session_timeout_minutes | integer | Necessary       | 0       | P2P browse session timeout in minutes. Valid range: 0~1440. 0 means no configured timeout release.            |                   |


### Request sample

```json
{
	"session_timeout_minutes": 30
}
```

### Return data

| Name                    | Type    | Is it necessary | Default | Remark                                                                                                                 | Other information |
| ----------------------- | ------- | --------------- | ------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code                    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                  |                   |
| message                 | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful.                    |                   |
| session_timeout_minutes | integer | Necessary       | 0       | The P2P browse session timeout value saved after setting, in minutes.                                                 |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"session_timeout_minutes": 30
}
```



## Get P2P browse config

### Basic information

**Path：** /get-p2p-browse-config

**Method：** POST

**Interface description:：**

<p>Get the configured idle release timeout for P2P browse sessions.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | --------------- | ------- | ------ | ----------------- |


### Request sample

```json
{}
```

### Return data

| Name                    | Type    | Is it necessary | Default | Remark                                                                                                                 | Other information |
| ----------------------- | ------- | --------------- | ------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code                    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                  |                   |
| message                 | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful.                    |                   |
| session_timeout_minutes | integer | Necessary       | 0       | Current configured P2P browse session timeout in minutes. 0 means no configured timeout release.                       |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success",
	"session_timeout_minutes": 30
}
```



## Set Raysync server parameters

### Basic information

**Path：** /set-node-machine

**Method：** POST

**Interface description:：**

<p>Set Raysync server parameters</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name     | Type    | Is it necessary | Default | Remark                                                       | Other information                                            |
| -------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| enable   | boolean | Necessary       | false   | Set whether to enable the node machine.                      | When the enable parameter is true, url, account, password are required |
| url      | string  | Unnecessary     |         | Set the IP address of node machine including the protocol, address, and port. Such as: http://192.168.1.1:8090. |                                                              |
| auth_way | integer | Necessary       |         | Authentication Type <br/>Raysync authentication: 1 <br/>LDAP authentication: 2 <br/>Email authentication: 4 <br/>System authentication: 8 <br/>External HTTP authentication: 128 |                                                              |
| account  | string  | Unnecessary     |         | Set the account for logging in to the node machine.          |                                                              |
| password | string  | Unnecessary     |         | Set the password for logging in to the node machine.         |                                                              |


### Request sample

```json
{
  "enable": true,
  "url": "http://192.168.1.1:8090",
  "account": "test",
  "password": "123",
  "auth_way": 2
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Get Raysync server parameters

### Basic information

**Path：** /get-node-machine

**Method：** POST

**Interface description:：**

<p>Get Raysync server parameters</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | --------------- | ------- | ------ | ----------------- |


### Request sample

```json
{}
```

### Return data

| Name     | Type    | Is it necessary | Default | Remark                                                       | Other information |
| -------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code     | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message  | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| enable   | boolean | Necessary       |         | Returns whether to enable the node machine.                  |                   |
| url      | string  | Necessary       |         | Returns the IP address of the node machine.                  |                   |
| auth_way | integer | Necessary       |         | Authentication Type <br/>Raysync authentication: 1 <br/>LDAP authentication: 2 <br/>Email authentication: 4 <br/>System authentication: 8 <br/>External HTTP authentication: 128 |                   |
| account  | string  | Necessary       |         | Returns the account for logging in to the node machine.      |                   |



### Return sample

```json
{
   "account": "test",
    "auth_way": 1,
    "code": 0,
    "enable": true,
    "message": "success",
    "url": "http://192.168.1.1:8090"
}
```



## Set visible ui

### Basic information

**Path：** /set-visible-ui

**Method：** POST

**Interface description:：**

<p>Set the status parameters of the GUI display.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name    | Type    | Is it necessary | Default | Remark                                         | Other information |
| ------- | ------- | --------------- | ------- | ---------------------------------------------- | ----------------- |
| visible | boolean | Necessary       |         | Set the graphical interface whether to display |                   |


### Request sample

```json
{
	"visible": true
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.           |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed.  |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```



## Set GUI language parameters

### Basic information

**Path：** /set-language

**Method：** POST

**Interface description:：**

<p>Set GUI language parameters.</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name     | Type   | Is it necessary | Default | Remark                                                     | Other information |
| -------- | ------ | --------------- | ------- | ---------------------------------------------------------- | ----------------- |
| language | string | Necessary       |         | Set the GUI language type. Accepted values: zh-CN, en-US, tr-TR, ja-JP, fr-FR, es-ES, pt-PT, it-IT. | The running client returns failed when the language is not supported by manager resources. |


### Request sample

```json
{
	"language": "en-US"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```

## Set proxy manager

### Basic information

**Path：** /set-proxy-manager

**Method：** POST

**Interface description:：**

<p>Set the parameters of the Internet machine agent function. Version 6.2.8.20 is supported</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name                 | Type    | Is it necessary | Default | Remark                                         | Other information |
| -------------------- | ------- | --------------- | ------- | ---------------------------------------------- | ----------------- |
| enable-proxy-manager | boolean | Necessary       |         | The Internet machine agent function is enabled |                   |
| proxy-manager-ip     | string  | Unnecessary     |         | Address of the proxy machine                   |                   |
| proxy-manager-port   | integer | Unnecessary     |         | Proxy network port                             |                   |


### Request sample

```json
{
	"enable-proxy-manager": true,
    "proxy-manager-ip": "172.16.4.36",
    "proxy-manager-port": 6061
}
```

### Return data

| Name  | Type  | Is it necessary | Default | Remark                                                                    | Other information |
| ------- | ------- | -------- | ------ | --------------------------------------------------------------------------- | -------- |
| code    | integer | Necessary | 0      | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                          |          |
| message | boolean  | Necessary |        | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |          |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```

## Filter task display

### Basic information

**Path：** /show-task

**Method：** POST

**Interface description:：**

<p>Filter task display</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name     | Type   | Is it necessary | Default | Remark  | Other information |
| -------- | ------ | --------------- | ------- | ------- | ----------------- |
| task-ids | string | Necessary       |         | Task id |                   |



### Request sample

```json
{
	"task-ids": "1,2,3"
}
```

### Return data

| Name  | Type  | Is it necessary | Default | Remark                                                                    | Other information |
| ------- | ------- | -------- | ------ | --------------------------------------------------------------------------- | -------- |
| code    | integer | Necessary | 0      |Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                          |          |
| message | boolean  | Necessary |        | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. 。 |          |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```

## Log retention period

### Basic information

**Path：**/set-clean-log-time

**Method：** POST

**Interface description:：**

<p>Clear expired log files</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name         | Type    | Is it necessary | Default | Remark              | Other information |
| ------------ | ------- | --------------- | ------- | ------------------- | ----------------- |
| time_seconds | integer | Necessary       |         | Log expiration time |                   |



### Request sample

```json
{
	"time-seconds": 7200
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message | boolean | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
	"code": 0,
	"message": "success"
}
```


## Get log cleaning time

### Basic Information

**Path：** /get-clean-log-time

**Interface description：**
<p>Get log cleaning time</p>

### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes              |        |        |

**Body**

| Name   | Type | Is it necessary | Default | Remark                                                  | Other information |
| -------- | ------ | -------- | ------ | --------------------------------------------------------- | -------- |

### Request sample

```json
{}
```

### Return data

| Name         | Type    | Is it necessary | Default | Remark                                                                                                                                                  | Other information |
| ------------ | ------- | --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| code         | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed.                                                  |                   |
| message      | boolean | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| time-seconds | integer | Necessary       |         | Returns the log cleaning time. The unit is seconds.                                                                                                     |                   |

### Return sample

```json
{
  "code": 0,
  "message": "success",
  "time-seconds":7200
}
```



## Prioritize transfer tasks

### Basic Information

**Path：** /set-top-task

**Method：** POST

**Interface description:：**

<p>Adjust the task to the first position in the task queue so that it can be transferred first</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name    | Type   | Is it necessary | Default | Remark  | Other information |
| ------- | ------ | --------------- | ------- | ------- | ----------------- |
| task-id | string | Necessary       |         | task-id |                   |

### Request sample

```json
{
  "task-id": "1"
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
  "code": 0,
  "message": "success"
}
```

## Set task speed

### Basic Information

**Path：**  /set-task-speed

**Method：** POST

**Interface description:：**

<p>Set task speed</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name               | Type    | Is it necessary | Default | Remark                                         | Other information |
| ------------------ | ------- | --------------- | ------- | ---------------------------------------------- | ----------------- |
| task-id            | string  | Necessary       |         | task-id                                        |                   |
| max-upload-speed   | integer | Necessary       |         | Maximum upload speed (b/s), 0 means no limit   |                   |
| max-download-speed | integer | Necessary       |         | Maximum download speed (b/s), 0 means no limit |                   |

### Request sample

```json
{
    "task-id": "1",
    "max-upload-speed":2,
    "max-download-speed":3
}
```

### Return data

| Name    | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code    | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |


### Return sample

```json
{
  "code": 0,
  "message": "success"
}
```

## Get the total number of task types

### Basic Information

**Path：**   /get-task-type-count

**Method：** POST

**Interface description:：**

<p>Get the total number of task types</p>


### Request parameter

**Headers**

| Parameter name | Parameter value  | Is it necessary | Sample | Remark |
| -------------- | ---------------- | --------------- | ------ | ------ |
| Content-Type   | application/json | Yes             |        |        |

**Body**

| Name | Type | Is it necessary | Default | Remark | Other information |
| ---- | ---- | --------------- | ------- | ------ | ----------------- |
|      |      |                 |         |        |                   |

### Request sample

```json
{

}
```

### Return data

| Name                   | Type    | Is it necessary | Default | Remark                                                       | Other information |
| ---------------------- | ------- | --------------- | ------- | ------------------------------------------------------------ | ----------------- |
| code                   | integer | Necessary       | 0       | Return the error code of the execution operation that returns 0 when successful and non-0 when failed. |                   |
| message                | string  | Necessary       |         | Return the error text information of the execution operation that returns "success" when successful and return the specific failure reason when failed. |                   |
| normal                 | integer | Necessary       |         | General task                                                 |                   |
| └─ complete-count      | integer | Necessary       |         | Number of tasks completed                                    |                   |
| └─ download-count      | integer | Necessary       |         | Number of download tasks                                     |                   |
| └─ upload-count        | integer | Necessary       |         | Number of upload tasks                                       |                   |
| sync                   | integer | Necessary       | 0       | Sync task                                                    |                   |
| └─ bidirectional-count | integer | Necessary       |         | Number of bidirectional sync tasks                           |                   |
| └─ download-count      | integer | Necessary       |         | Number of download sync tasks                                |                   |
| └─ upload-count        | integer | Necessary       |         | Number of upload sync tasks                                  |                   |
| p2p                    | integer | Necessary       | 0       | P2P task                                                     |                   |
| └─ complete-count      | integer | Necessary       |         | Number of tasks completed                                    |                   |
| └─ download-count      | integer | Necessary       |         | Number of p2p receiving tasks                                |                   |
| └─ upload-count        | integer | Necessary       |         | Number of p2p sending tasks                                  |                   |
| sync-p2p               | integer | Necessary       | 0       | P2P sync task                                                |                   |
| └─ count               | integer | Necessary       |         | Number of P2P sync tasks                                     |                   |


### Return sample

```json
{
    "code": 0,
    "message": "success",
    "normal": {
        "complete-count": 1,
        "download-count": 0,
        "upload-count": 0
    },
    "p2p": {
        "complete-count": 0,
        "download-count": 0,
        "upload-count": 0
    },
    "sync": {
        "bidirectional-count": 0,
        "download-count": 0,
        "upload-count": 1
    },
    "sync-p2p": {
        "count": 0
    }
}
```
