<a name="top"></a>

# Raysync Web admin API Documentation v8.1.8.4

[TOC]

Raysync Web Admin API interface for integrating web admin portal functions

# API interface authentication mode description

**1.API authentication mode**

The Raysync admin portal authenticates each access request, that is, each request needs to include the Authorization parameter in the public request parameter to verify the user identity. The information is generated after the user logs in successfully. Otherwise, the API interface cannot be invoked.



**2. Instructions for using authentication mode**

The password is encrypted using Hashids (Hashids is a small open source library that generates short, unique, non-sequential ids from numbers). The salt value can be configured by yourself. The configuration file is **config.ini** and the field is **hashid_salt**, for example: 'hashid_salt = eRuYuw'; The default length is **64** characters.

**Note ** : Modifying the hashid_salt field of the config.ini file will affect the normal background login. To log in to the background normally, delete the hashid_salt configuration.

Encoding step: Convert the string to byte - convert the byte string to the corresponding hexadecimal - encode the string with hashids.

After obtaining the corresponding encryption string, test the login in postman. If the login succeeds, the token value will be returned. When requesting other interfaces, add **Authorization: Bearer JWT_TOKEN** in **headers** to request interfaces normally. As follows:

| Authorization | Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2NzE2MjE5MzIsInVzZXJfaWQiOjEsInJvbGVfaWQiOjEsImFjY291bnQiOiJhZG1pbiIsImFjY291bnRfdHlwZSI6MX0.cRwaH440E6rmqy-KSyMbhLFF-8LkDuu_RX7O0veaIrU |
| ------------- | ------------------------------------------------------------ |



**3. Authentication Example code**

**Python example**

```python
# -*- coding: utf-8 -*-
from hashids import Hashids
import binascii

hashids = Hashids(salt='xEYuYu=', min_length=64)

# encoding
b_str = bytes("qwer.1234", encoding="utf8")
en_str = binascii.hexlify(b_str)
val = str(en_str, encoding="utf-8")
decode_val = hashids.encode_hex(val)
print('decode', decode_val)

# decode
s = "QlXmVpPWyb8JYLKABdzQ42kgLBYemGAoYjHaE6DbqjwZeoMD90GRr163xNav5EOo"

val = Hashids(salt='xEYuYu=', min_length=64).decode_hex(s)
_str = bytes(val, encoding="utf8")
output = binascii.unhexlify(_str)
val = str(output, encoding="utf-8")
print("encode", val)
```

**Js example**

```javascript
import Hashids from 'hashids'

const ALPHABET = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890'
const SALT = 'xEYuYu='
const HASH_MIN_LENGTH = 64
export const toHex = (str: string) => {
  var result = ''
  for (var i = 0; i < str.length; i++) {
    result += str.charCodeAt(i).toString(16)
  }
  return result
}
class Hash {
  static hashids = new Hashids(SALT, HASH_MIN_LENGTH, ALPHABET)

  public static encode(key: string) {
    const vaule = toHex(key)
    return this.hashids.encodeHex(vaule)
  }
  public static decode(key: string) {
    if (!key) return ''
    return Buffer.from(this.hashids.decodeHex(key), 'hex').toString('utf8')
  }
}

export default Hash
```


___


# <a name='AdminResource'></a> AdminResource

## <a name='Administrator login'></a> Administrator login
[Back to top](#top)

```
POST /api/users/admin/login
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>(Necessary)  Admin account</p> |
| password | `String` | <p>(Necessary)   Password , using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| isAuth | `Boolean` | <p>(Optional)   Whether to enable custom salt encryption. This parameter is disabled by default.</p> <p>If enabled, the hashid_salt value of the config.ini file is used.</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "account":"admin",
    "password":"64695oONQpxkwZMJvE0GblRDKBqPokrPJAzZmhGeB7yaVX4r2jY1dvE0GblRDKBq",
    "isAuth":false
}
```
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>Admin account </p> |
| softVersion | `String` | <p>Soft version</p> |
| protocol_version | `String` | <p>Protocol version</p> |
| client_version | `String` | <p>Client version</p> |
| disk_capacity | `Int` | <p>Free disk space (MB)</p> |
| userId | `Int` | <p>User ID</p> |
| loginFailTimes | `Int` | <p>Login failures times</p> |
| lockPeriod | `Int` | <p>Lockout period when a user fails to log in (unit: second)</p> |
| maxLockTimes | `Int` | <p>The maximum number of failed login attempts</p> |
| token | `String` | <p>Login token</p> |
| refresh_token | `String` | <p>Renew tokens, which are used in exchange for new tokens</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "data": {
            "account": "admin",
            "softVersion": "raysync_enterprise",
            "protocol_version": "6.7.8.3",
            "client_version": "6.7.8.3",
            "disk_capacity": 112724.01171875,
            "userId": 991,
            "loginFailTimes": 0,
            "lockPeriod": 180,
            "maxLockTimes": 5,
            "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MDEyNTE2ODcsInVzZXJfaWQiOjEsInJvbGVfaWQiOjEsImFjY291bnQiOiJhZG1pbiIsImFjY291bnRfdHlwZSI6MX0._ZB4gcwf_gxd5fD0sRSBtgACZQY3jyTh70xUQ7Bsfm4",
            "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MDI0NTc2ODcsInVzZXJfaWQiOjEsImFjY291bnQiOiJhZG1pbiIsInJvbGVfaWQiOjEsImlzX3JlZnJlc2giOnRydWUsImFjY291bnRfdHlwZSI6MX0.3CRYskR6ZGpj6Kl_cf9CJCIXp_XLF1cXp4uqsizyOzY"
        },
    "message": "OK",
    "result": true,
    "value": "OK",
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1001,
    "value": "Database exception",
    "message": "Database exception",
    "data": {},
    "result": false
}
{
    "code": 1005,
    "value": "Password invalid",
    "message": "Password invalid",
    "data": {},
    "result": false
}
{
    "code": 1098,
    "value": "WS_NeedUpdatePwd",
    "message": "WS_NeedUpdatePwd",
    "data": {},
    "result": false
}
{
    "code": 1050,
    "value": "account was locked",
    "message": "account was locked",
    "data": {},
    "result": false
}   
{
    "code": 4001,
    "value": "account does not exist",
    "data": {},
    "result": false,
    "message": "account does not exist"
}
{
    "code": 4068,
    "value": "The disk capacity is insufficient. Clear the disk capacity in time",
    "data": {},
    "result": false,
    "message": "The disk capacity is insufficient. Clear the disk capacity in time"
}
{
    "code": 4078,
    "value": "Account is not activated",
    "message": "Account is not activated",
    "data": {},
    "result": false
}
```

## <a name='Renewal token'></a> Renewal token
[Back to top](#top)

```
PUT /api/users/admin/auth
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>refresh_token</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| token | `str` | <p>New token</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
    {
        "code": 200,
        "value": "OK",
        "data": {
            "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTkxNzA0MDIsInVzZXJfaWQiOjEsImFjY291bnRfdHlwZSI6MX0.xsweyz380wIybU_-CecrVbNooMQwLQ55GQ3ivQN4TpY"
        },
        "result": true
    }
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1009,
    "value": "Invalid token",
    "data": null,
    "result": false
}
```

# <a name='LicenseResource'></a> LicenseResource

## <a name='Get lincense information'></a> Get lincense information
[Back to top](#top)

```
GET /api/license
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| actived | `Int` | <p>Activated: 1: active, 0: inactive</p> |
| max_bandwidth | `String` | <p>Maximum bandwidth</p> |
| activate_date | `String` | <p>Activation date</p> |
| expire_date | `String` | <p>Expiration date</p> |
| maintenance_expiry | `String` | <p>Maintenance date</p> |
| total_traffic | `Int` | <p>Total authorized traffic. -1: no limit. The unit is Byte</p> |
| remain_traffic | `Int` | <p>Remaining traffic, -1: no limit, expressed in Byte</p> |
| user_num_limit | `Int` | <p>User limit</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "actived": 1,
        "max_bandwidth": "2048M",
        "activate_date": "2023-11-23",
        "expire_date": "2033-11-23",
        "maintenance_expiry": "2025-05-29",
        "total_traffic": -1,
        "remain_traffic": -1,
        "user_num_limit": 1000
    },
    "result": true,
    "message": "OK"
}
```

# <a name='ServiceResource'></a> ServiceResource

## <a name='Get the status of the service'></a> Get the status of the service
[Back to top](#top)

```
GET /api/service/status
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| p2p | `Boolean` | <p>Status of the peer-to-peer transfer service</p> |
| rayfile | `Boolean` | <p>Status of the Rayfiile service</p> |
| ftp | `Boolean` | <p>Status of the FTP transfer service</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "p2p": true,
        "rayfile": true
        "ftp": true,
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Restart service)'></a> Restart service
[Back to top](#top)

```
POST /api/service/transfer/restart
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| serviceName | `String` | <p>(Necessary)  p2p rayfile ftp</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "serviceName":"p2p"
}
{
    "serviceName":"rayfile"
}
{
    "serviceName":"ftp"
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4190,
    "value": "Point-to-point service is not configured",
    "data": null,
    "result": false
}
{
    "code": 1035,
    "value": "Command execution failed",
    "data": null,
    "result": false
}
```

# <a name='StorageResource'></a> StorageResource

## <a name='Create Storage'></a> Create Storage

[Back to top](#top)

```
POST /api/storage/create
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name                   | Type      | Description                                                  |
| ---------------------- | --------- | ------------------------------------------------------------ |
| OssType                | `Int`     | <p>(Necessary)  OSS type 0: local storage; 1: Alibaba Cloud, OSS; 2: Amazon S3; 3: Other S3 storage; 5: Azure Blob;  7: Google Cloud Storage</p> |
| storageName            | `String`  | <p>(Necessary)  Storage name</p>                             |
| OssHome                | `String`  | <p>(Optional) Home directory when stored locally</p>         |
| Endpoint               | `String`  | <p>(Optional) Endpoint cloud storage field</p>               |
| AccessKeyId            | `String`  | <p>(Optional) AccessKeyId cloud storage field</p>            |
| AccessKeySecret        | `String`  | <p>(Optional) Cloud storage field, using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| BucketName             | `String`  | <p>(Optional) The name of the storage space created in the cloud storage service</p> |
| OssBuff                | `Int`     | <p>(Optional) OssBuff Byte cloud storage field<p>            |
| Region                 | `String`  | <p>(Optional) Region cloud storage field</p>                 |
| UseVirtualAddressing   | `Int`     | <p>(Optional) Cloud storage field. 0: virtual addressing is not used 1: virtual addressing is used</p> |
| cleanSwitch            | `Boolean` | <p>(Optional)  Automatic file cleaning switch; 0: off, 1: on (Local storage only)</p> |
| cToFolder              | `String`  | <p>(Optional) Recovery path  (Local storage only)</p>        |
| cProperty              | `Int`     | <p>(Optional) The time type of the file reclamation judgment. 0: the last access time. 1: the last modification time (Local storage only)</p> |
| cTimeDelta             | `Int`     | <p>(Optional)  Number of days (Local storage only)</p>       |
| cFileType              | `Int`     | <p>(Optional)  Type of the reclaimed file. 0 : All files; 1: Transfer temporary files, you can set 1 only if cProperty is equal to 0 (Local storage only)</p> |
| cDelete                | `Boolean` | <p>(Optional) Whether to delete files directly. 0: not deleted 1: deleted (Local storage only) </p> |
| cReserveAfterCleanTime | `Int`     | <p>(Optional) Keep the file for xx days and delete it. The value ranges from 0 to 9999. 0 indicates permanent retention (Local storage only)</p> |

### Parameters examples

`json` - Request-Example(Local storage):

```json
{
    "storageName": "storage",
    "OssHome": "/data/user",
    "cleanSwitch": true,
    "cProperty": 0,
    "cTimeDelta": 7,
    "cFileType": 1,
    "cToFolder": "",
    "cReserveAfterCleanTime": 0,
    "cDelete": false,
}
```

`json` - Request-Example(OSS Cloud):

```json
{
  "OssType": 1,
  "storageName": "test_alyun",
  "Endpoint": "oss-cn-shenzhen.aliyuncs.com",
  "AccessKeyId": "LTAI5tJQuzUHDFpoByoseEzr",
  "AccessKeySecret": "dK0b9ogjBLBLVKD0pTwbY0xP3mMUe1541QQ2zuk5DmGB2ELfa0ozjGKJXg6yWjOV",
  "BucketName": "hello-ok-oss",
  "OssHome": "",
  "OssBuff": 104857600,
  "cDelete": false
}
```

`json` - Request-Example(AWS S3):

```json
{
  "OssType": 2,
  "storageName": "test_ams3",
  "Region": "ap-east-1",
  "AccessKeyId": "AKIA6DFCDPOU3CM5RDMJ",
  "AccessKeySecret": "rEBwoJMGweIlMRkvXl95SbkAPDMdVWT4zoY4ZrlAtjJ1GklE8ZfYD0o3E8zZCAwEJ8K",
  "BucketName": "zbuckhk",
  "OssBuff": 104857600,
  "cDelete": false
}
```

`json` - Request-Example(Other S3):

```json
{
  "id": 6,
  "isDefault": false,
  "storageName": "test_others3",
  "create_time": "2024-09-09 15:47:44",
  "OssType": 3
}
```

`json` - Request-Example(Azure Blob):

```json
#Server Expired and Cannot Be Used
```

`json` - Request-Example(Google Cloud):

```json
{
  "id": 7,
  "isDefault": false,
  "storageName": "test_google",
  "create_time": "2024-09-09 16:00:31",
  "OssType": 7
}
```

### Success response

#### Success response

| Name        | Type       | Description                                                  |
| ----------- | ---------- | ------------------------------------------------------------ |
| id          | `int`      | <p>Storage id</p>                                            |
| storageName | `String`   | <p>Storage name</p>                                          |
| create_time | `datatime` | <p>Create time</p>                                           |
| isDefault   | `Boolean`  | <p>Whether it is the default space. 0: The space is not the default space. 1: The space is the default space</p> |
| OssType     | `Int`      | <p>oss type 0: local storage; 1: OSS Cloud; 2: Amazon S3 CLoud; 3: Other S3 storage; 5: Azure Blob;  7:Google Cloud Storage</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "id": 4,
        "isDefault": false,
        "storageName": "22",
        "create_time": "2024-04-28 16:42:54",
        "OssType": 0
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4009,
    "value": "storage name is exist, please modify",
    "message": "storage name is exist, please modify",
    "data": null,
    "result": false
}
{
    "code": 1066,
    "value": "invalid path",
    "message": "invalid path",
    "data": null,
    "result": false
}
```

## <a name='Gets a list of all storage'></a> Gets a list of all storage

[Back to top](#top)

```
GET /api/storage/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type     | Description                      |
| -------- | -------- | -------------------------------- |
| pageNum  | `String` | <p>(Optional)    Page number</p> |
| pageSize | `String` | <p>(Optional)   Page size</p>    |

### Success response

#### Success response - `回参`

| Name                   | Type      | Description                                                  |
| ---------------------- | --------- | ------------------------------------------------------------ |
| storage_data           | `list`    | <p>Storage information</p>                                   |
| total                  | `int`     | <p>Total query results</p>                                   |
| size                   | `int`     | <p>Quantity per page</p>                                     |
| current                | `int`     | <p>Current page count</p>                                    |
| pages                  | `int`     | <p>Total pages</p>                                           |
| OssType                | `Int`     | <p>oss type 0: local storage; 1: OSS Cloud; 2: Amazon S3 CLoud; 3: Other S3 storage; 5: Azure Blob;  7:Google Cloud Storage</p> |
| storageName            | `String`  | <p>Storage name</p>                                          |
| OssHome                | `String`  | <p>Home directory when stored locally</p>                    |
| Endpoint               | `String`  | <p>Cloud storage field</p>                                   |
| AccessKeyId            | `String`  | <p>Cloud storage field</p>                                   |
| AccessKeySecret        | `String`  | <p>Cloud storage field. Using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| OssBuff                | `Int`     | <p>Byte. Cloud storage field</p>                             |
| Region                 | `String`  | <p>Cloud storage field</p>                                   |
| UseVirtualAddressing   | `Int`     | <p>Cloud storage field</p>                                   |
| cleanSwitch            | `Boolean` | <p>Whether to enable automatic file clearing for local storage</p> |
| cToFolder              | `String`  | <p>Recovery path</p>                                         |
| cProperty              | `Int`     | <p>The time type of the file reclamation judgment. 0: the last access time. 1: the last modification time</p> |
| cTimeDelta             | `Int`     | <p>Number of days</p>                                        |
| cFileType              | `Int`     | <p>Type of the reclaimed file. 0 : All files; 1: Transfer temporary files</p> |
| cDelete                | `Boolean` | <p>Whether to delete files directly. 0: not deleted 1: deleted</p> |
| cReserveAfterCleanTime | `Int`     | <p>Keep the file for xx days and delete it. The value ranges from 0 to 9999. 0 indicates permanent retention</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "storage_data": [
            {
                "id": 5,
                "Endpoint": "7777",
                "create_time": 1619667296.0,
                "OssBuff": "",
                "Region": "",
                "UseVirtualAddressing": 1,
                "isDefault": true,
                "cleanSwitch": false,
                "cTimeDelta": 7,
                "OssType": 0,
                "update_time": 1619669601.0,
                "AccessKeyId": "",
                "BucketName": "",
                "OssHome": "222",
                "storageName": "11",
                "cProperty": 0,
                "cToFolder": "",
                "cFileType": 0,
                "cDelete": false,
                "cReserveAfterCleanTime": 0
            },
            {
                "id": 1,
                "Endpoint": "",
                "create_time": 1619325734.0,
                "OssBuff": 0,
                "Region": "",
                "UseVirtualAddressing": 1,
                "isDefault": false,
                "cleanSwitch": false,
                "cTimeDelta": 7,
                "OssType": 0,
                "update_time": 1619601301.0,
                "AccessKeyId": "",
                "BucketName": "",
                "OssHome": "D:\\dev\\gitlab\\raysync_operationplatform\\user",
                "storageName": "Default",
                "cProperty": 0,
                "cToFolder": "",
                "cFileType": 0,
                "cDelete": false,
                "cReserveAfterCleanTime": 0
            }
        ],
        "total": 2,
        "current": 1,
        "size": 10,
        "pages": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Delete storage'></a> Delete storage

[Back to top](#top)

```
DELETE /api/storage/delete
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name            | Type   | Description                        |
| --------------- | ------ | ---------------------------------- |
| storage_id_list | `list` | <p>(Necessary) Storage id list</p> |

### Parameters examples

`json` - Request-Example(Local storage):

```json
{storage_id_list: [3]}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{"code": 200, "value": "OK", "data": null, "result": true, "message": "OK"}
```

# <a name='TaskDistributionResource'></a> TaskDistributionResource

## <a name='Create a server delivery task'></a> Create a server delivery task

[Back to top](#top)

```
POST /api/task_distribution/create
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name                                  | Type      | Description                                                  |
| ------------------------------------- | --------- | ------------------------------------------------------------ |
| taskName                              | `String`  | <p>(Necessary) Task name</p>                                 |
| sourcePath                            | `String`  | <p>(Necessary) Source path. The source path is an absolute path. When the server is the source path (i.e. download), the source path is relative to the path pointed to by the storage Id (storageId)</p> |
| storageId                             | `Int`     | <p>(Necessary) The storage ID where the server path is located</p> |
| spaceId                               | `Int`     | <p>(Necessary) The space ID to which the storage ID belongs</p> |
| targetPath                            | `String`  | <p>(Necessary)  Target path. The target path is an absolute path. When the server is the target path (i.e. upload), it is relative to the path pointed to by the storage ID (storageId)</p> |
| taskType                              | `String`  | <p>(Necessary) Synchronization type. Upload: synchronous upload; Download: synchronous download; Bidirectional: Bidirectional synchronization</p> |
| triggeringCondition                   | `Object`  | <p>(Necessary) Trigger condition. Task trigger type</p>      |
| triggeringCondition.taskFrequencyType | `Object`  | <p>(Necessary)  once: Execute only once after task creation. This field is valid when the 'taskFrequencyType' field is specified as' once '. For example：<br/> { &quot;taskFrequencyType&quot;: &quot;once&quot;, &quot;once&quot;: 1720668917.108,  # Only executed once, timestamp }<br/> integer: The task is executed at specified intervals. This field is valid when the 'taskFrequenceType' field is specified as' integer ', with the unit of interger being seconds, for example: executed once every hour. <br/> { taskFrequencyType: &quot;integer&quot;, &quot;integer&quot;: 3600, #Execute once every 3600 seconds, which is once an hour}<br/> clock: Tasks are executed at designated times every day. This field is valid when the 'taskFrequencyType' field is specified as' clock '. For example: Execute once a day at 8 o'clock<br/> { &quot;taskFrequencyType&quot;: &quot;clock&quot;, &quot;clock&quot;: &quot;08:00&quot;, }<br/> timing: Automatically executed once per week on a specified date and time. When the 'taskFrequencyType' field is specified as' timing ', this field is valid. Use 1, 2, 4, 8, 16, 32, 64 to correspond to Monday to Sunday. When multiple dates need to be specified, add the corresponding values together, for example: 15 represents Monday to Thursday. Execute at 15:15 every Monday to Thursday<br/> { &quot;taskFrequencyType&quot;: &quot;timing&quot;, &quot;timing&quot;: { &quot;week&quot;: 15, &quot;clock&quot;: &quot;15:15&quot; } }<br/></p> |
| enableSSL                             | `Boolean` | <p>(Optional) Enable encrypted transmission</p>              |
| fullSync                              | `Boolean` | <p>(Optional) Preserving file attributes (including preserving file modification time, preserving file ACL attributes) FullSync, saveTimestamp, and enable_stave_coml must select one of them</p> |
| saveTimestamp                         | `Boolean` | <p>(Optional)  Preserve the file modification time, which can be enabled simultaneously with enable_save_acl</p> |
| enable_save_acl                       | `Boolean` | <p>(Optional)  Preserve the file ACL attribute, which can be enabled simultaneously with saveTimestamp</p> |
| underThePath                          | `Boolean` | <p>(Optional) Only transfer files and folders from the source path</p> |
| removeSurplusFile                     | `Boolean` | <p>(Optional) Automatically delete the target file when the source file is deleted</p> |
| syncRemoveSourceFile                  | `Boolean` | <p>(Optional) Whether to automatically delete the source file switch after a single file transfer is completed</p> |
| syncRemoveSourceFileDetail            | `Object`  | <p>(Optional) 1. Delete option<br/> Delete all source directories and files: { type: 1, deleteAllDir: true, saveSourceDir: false } <br/> Keep the source directory structure: { type: 1, deleteAllDir: false, saveSourceDir: true } <br/> 2. Delete after moving (only applicable for synchronous upload)<br/> Unit: 'h/d' (hour/day)<br/>For example: Move to path E:/a after 10 hours and automatically delete after 1 day {&quot;type&quot;: 2, &quot;n&quot;: 10, &quot;unit&quot;: &quot;h&quot;, &quot;path&quot;: &quot;E:/a&quot;, &quot;days&quot;: 1}</p> |
| fileUpdatedMode                       | `Int`     | <p>(Optional) File update method. 0: Overwrite file; 1: Add write (not applicable to object storage); 2: Rename (only supports synchronizing tasks once); 3: If the source file is newer, overwrite it</p> |
| sourceIsClient                        | `Boolean` | <p>(Optional)   Is the source from the client</p>            |
| transIgnoreRegSwitch                  | `Boolean` | <p>(Optional) Switch for skipping files during transfer</p>  |
| transIgnoreReg                        | `String`  | <p>(Optional) Skip file</p>                                  |
| transIncludeRegSwitch                 | `Boolean` | <p>(Optional) Switch of the transfer file whitelist</p>      |
| transIncludeReg                       | `String`  | <p> (Optional) Transfer file whitelist</p>                   |
| transIgnoreSizeSwitch                 | `Boolean` | <p>(Optional) Switch for skipping files larger than xx during transfer</p> |
| transIgnoreSize                       | `String`  | <p>(Optional) Transfer skips file size</p>                   |
| transIgnoreSizeUnit                   | `String`  | <p>(Optional) Transfer file unit</p>                         |
| MachineNodeList                       | `list`    | <p>(Optional) Specify the MAC address list/api/machine/node for the transmitted node machine to obtain node machine information/p></p> |

### Parameters examples

`json` - Request-Example(Download):

```json
{
  "taskName": "Distribute synchronous download tasks",
  "MachineNodeList": [],
  "spaceId": 1,
  "storageId": 1,
  "enableSSL": false,
  "fullSync": true,
  "saveTimestamp": true,
  "enable_save_acl": true,
  "underThePath": false,
  "removeSurplusFile": false,
  "syncRemoveSourceFile": false,
  "syncRemoveSourceFileDetail": {
    "type": 1,
    "deleteAllDir": true,
    "saveSourceDir": false
  },
  "fileUpdatedMode": 0,
  "forbidClientFilterSwitch": false,
  "transIgnoreRegSwitch": false,
  "transIncludeRegSwitch": false,
  "transIgnoreSizeSwitch": false,
  "transIgnoreSize": 1,
  "transIgnoreSizeUnit": "MB",
  "sourcePath": "/taskDistribution",
  "targetPath": "/taskDistribution",
  "triggeringCondition": {
    "taskFrequencyType": "once",
    "once": 1725420535.319
  },
  "sourceIsClient": false,
  "taskType": "download"
}
```

`json` - Request-Example(Upload):

```json
{
  "taskName": "Distribute synchronous upload tasks",
  "MachineNodeList": [],
  "sourcePath": "/taskDistribution",
  "spaceId": 1,
  "storageId": 1,
  "targetPath": "/taskDistribution",
  "enableSSL": false,
  "fullSync": true,
  "saveTimestamp": true,
  "enable_save_acl": true,
  "underThePath": false,
  "removeSurplusFile": false,
  "syncRemoveSourceFile": false,
  "syncRemoveSourceFileDetail": {
    "type": 1,
    "deleteAllDir": true,
    "saveSourceDir": false
  },
  "fileUpdatedMode": 0,
  "forbidClientFilterSwitch": false,
  "transIgnoreRegSwitch": false,
  "transIncludeRegSwitch": false,
  "transIgnoreSizeSwitch": false,
  "transIgnoreSize": 1,
  "transIgnoreSizeUnit": "MB",
  "triggeringCondition": {
    "taskFrequencyType": "once",
    "once": 1725420761.366
  },
  "sourceIsClient": true,
  "taskType": "upload"
}
```

`json` - Request-Example(two-way sync):

```json
{
  "taskName": "two-way sync task",
  "MachineNodeList": [],
  "sourcePath": "/taskDistribution",
  "spaceId": 1,
  "storageId": 1,
  "targetPath": "/taskDistribution",
  "enableSSL": false,
  "fullSync": true,
  "saveTimestamp": true,
  "enable_save_acl": true,
  "underThePath": true,
  "removeSurplusFile": false,
  "syncRemoveSourceFile": false,
  "syncRemoveSourceFileDetail": {
    "type": 1,
    "deleteAllDir": true,
    "saveSourceDir": false
  },
  "fileUpdatedMode": 0,
  "forbidClientFilterSwitch": false,
  "transIgnoreRegSwitch": false,
  "transIncludeRegSwitch": false,
  "transIgnoreSizeSwitch": false,
  "transIgnoreSize": 1,
  "transIgnoreSizeUnit": "MB",
  "triggeringCondition": {
    "taskFrequencyType": "once",
    "once": 1725420857.76
  },
  "sourceIsClient": true,
  "taskType": "bidirectional"
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

## <a name='Get the list of server delivery task'></a> Get the list of server delivery task

[Back to top](#top)

```
GET /api/task_distribution/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type     | Description                          |
| -------- | -------- | ------------------------------------ |
| pageNum  | `String` | <p>(Optional)  Page number</p>       |
| pageSize | `String` | <p>(Optional)  Quantity per page</p> |
| taskName | `String` | <p>(Optional) Task name</p>          |

### Parameters examples

`String` - Request-Example:

```String
/api/task_distribution/list?taskName=test
```

### Success response

#### Success response

| Name                                  | Type      | Description                                                  |
| ------------------------------------- | --------- | ------------------------------------------------------------ |
| taskName                              | `String`  | <p>Task name</p>                                             |
| status                                | `String`  | <p>Task status. 0: idle. 1: The task has been delivered but has not been started. 2: Delivery is being executed. 3: indicates completion; 4: Pause; 5: Disable</p> |
| taskType                              | `String`  | <p>Synchronization type. Upload: synchronous upload; Download: synchronous download; Bidirectional: Bidirectional synchronization</p> |
| taskUid                               | `String`  | <p>Task uid</p>                                              |
| id                                    | `Int`     | <p>Task id</p>                                               |
| progressRate                          | `Int`     | <p>Task progress (percent)</p>                               |
| transFileCount                        | `Int`     | <p>Number of files during transmission</p>                   |
| transFileSize                         | `Int`     | <p>File size during transmission</p>                         |
| sourcePath                            | `String`  | <p>Source path</p>                                           |
| storageId                             | `Int`     | <p>Server storage ID</p>                                     |
| spaceId                               | `Int`     | <p>Server space ID</p>                                       |
| targetPath                            | `String`  | <p>Target path</p>                                           |
| triggeringCondition                   | `Object`  | <p>Trigger condition. Task trigger type</p>                  |
| triggeringCondition.taskFrequencyType | `Object`  | <p>once :Execute only once after task creation <br/> integer :Set to execute once every specified duration, immediately after task creation, and then calculate the next execution time from the completion of task execution <br/> clock :Set to execute once at a specified time every day, and if the current time has exceeded the specified time, execute immediately <br/> timing : Weekly scheduled {&quot;weekday&quot;:0, &quot;clock&quot;:&quot;xx:xx&quot;} 0 represents Monday, in descending order <br/> once: Execute only once after task creation. This field is valid when the 'taskFrequency Type' field is specified as' clock '.<br/> { &quot;taskFrequencyType&quot;: &quot;once&quot;, &quot;once&quot;: 1649668078,  # Only executed once, timestamp }<br/> integer: The specified task is executed every specified time. This field is valid when the 'taskFrequency Type' field is specified as' interval '.<br/> { &quot;taskFrequencyType&quot;: &quot;integer&quot;, &quot;integer&quot;: 3600,  # Unit: seconds }<br/> clock: Assign tasks to be executed at designated times each day. This field is valid when the 'taskFrequency Type' field is specified as' clock '.<br/> { &quot;taskFrequencyType&quot;: &quot;clock&quot;, &quot;clock&quot;: &quot;08:00&quot;, }<br/> timing: Scheduled every week. This field is valid when the 'taskFrequency Type' field is specified as' timing '.<br/> { &quot;taskFrequencyType&quot;: &quot;timing&quot;, &quot;timing&quot;: {&quot;week&quot;: 0, &quot;clock&quot;: &quot;xx:xx&quot;}  # Week 0 is Monday, in descending order }<br/></p> |
| enableSSL                             | `Boolean` | <p>Enable encrypted transmission</p>                         |
| fullSync                              | `Boolean` | <p>Preserving file attributes (including preserving file modification time, preserving file ACL attributes) FullSync, saveTimestamp, and enable_save_acl must select one of them</p> |
| saveTimestamp                         | `Boolean` | <p>Preserve the file modification time, which can be enabled simultaneously with enable_save_acl</p> |
| enable_save_acl                       | `Boolean` | <p>Preserve the file ACL attribute, which can be enabled simultaneously with saveTimestamp</p> |
| underThePath                          | `Boolean` | <p>Only transfer files and folders from the source path</p>  |
| removeSurplusFile                     | `Boolean` | <p>Automatically delete the target file when the source file is deleted</p> |
| syncRemoveSourceFile                  | `Boolean` | <p>Whether to automatically delete the source file switch after a single file transfer is completed</p> |
| syncRemoveSourceFileDetail            | `Object`  | 1. Delete option<br/> Delete all source directories and files: { type: 1, deleteAllDir: true, saveSourceDir: false } <br/> Keep the source directory structure: { type: 1, deleteAllDir: false, saveSourceDir: true } <br/> 2. Delete after moving (only applicable for synchronous upload)<br/> Unit: 'h/d' (hour/day)<br/>For example: Move to path E:/a after 10 hours and automatically delete after 1 day {&quot;type&quot;: 2, &quot;n&quot;: 10, &quot;unit&quot;: &quot;h&quot;, &quot;path&quot;: &quot;E:/a&quot;, &quot;days&quot;: 1}</p> |
| fileUpdatedMode                       | `Int`     | <p>File update method. 0: Overwrite file; 1: Add write (not applicable to object storage); 2: Rename (only supports synchronizing tasks once); 3: If the source file is newer, overwrite it/p</p> |
| sourceIsClient                        | `Boolean` | <p>Is the source from the client</p>                         |
| transIgnoreRegSwitch                  | `Boolean` | <p>Switch for skipping files during transfer</p>             |
| transIgnoreReg                        | `String`  | <p>Skip file</p>                                             |
| transIncludeRegSwitch                 | `Boolean` | <p>Switch of the transfer file whitelist</p>                 |
| transIncludeReg                       | `String`  | <p>Transfer file whitelist</p>                               |
| transIgnoreSizeSwitch                 | `Boolean` | <p>Switch for skipping files larger than xx during transfer</p> |
| transIgnoreSize                       | `String`  | <p>Transfer skips file size</p>                              |
| transIgnoreSizeUnit                   | `String`  | <p>Transfer file unit</p>                                    |
| MachineNodeList                       | `list`    | <p>Specify the MAC address list/api/machine/node for the transmitted node machine to obtain node machine information</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "id": 1,
                "taskName": "test",
                "taskUid": "ef68fa3d-43a1-4db8-8fa0-1ed20a13715a",
                "sourcePath": "/",
                "targetPath": "/taskDistribution",
                "spaceId": 1,
                "storageId": 1,
                "triggeringCondition": {
                    "taskFrequencyType": "once",
                    "once": 1720668574.181
                },
                "taskType": "download",
                "enableSSL": false,
                "saveTimestamp": true,
                "underThePath": false,
                "removeSurplusFile": false,
                "syncRemoveSourceFile": false,
                "syncRemoveSourceFileDetail": {
                    "type": 1,
                    "deleteAllDir": true,
                    "saveSourceDir": false
                },
                "fileUpdatedMode": 0,
                "transIgnoreRegSwitch": false,
                "transIgnoreReg": "",
                "transIncludeRegSwitch": false,
                "transIncludeReg": "",
                "transIgnoreSizeSwitch": false,
                "transIgnoreSize": 1,
                "transIgnoreSizeUnit": "MB",
                "create_time": "2024-07-11 11:30:38",
                "fullSync": true,
                "enable_save_acl": true,
                "sourceIsClient": false,
                "MachineNodeList": [],
                "status": 3,
                "progressRate": 100,
                "fileCount": 0,
                "fileSize": 0,
                "transFileCount": 0,
                "transFileSize": 0
            }
        ],
        "uploadSpeed": 0,
        "downloadSpeed": 0,
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Delete a server delivery task'></a> Delete a server delivery task

[Back to top](#top)

```
DELETE /api/task_distribution/delete
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name   | Type  | Description                |
| ------ | ----- | -------------------------- |
| taskId | `Int` | <p>(Necessary) Task id</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

# <a name='NodeResource'></a> NodeResource

## <a name='Get node information'></a> Get node information

[Back to top](#top)

```
POST /api/machine/node
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name    | Type     | Description                     |
| ------- | -------- | ------------------------------- |
| url     | `String` | <p>(Necessary) Node url</p>     |
| headers | `string` | <p>(Necessary) Node headers</p> |

### Parameters examples

`json` - Request-Example:

```json
{
  "url": "/api/node_list?page_index=0&page_size=10",
  "headers": {
    "Content-Type": "application/json;charset=UTF-8"
  }
}
```

### Success response

#### Success response

| Name                            | Type       | Description                                                 |
| ------------------------------- | ---------- | ----------------------------------------------------------- |
| body                            | `String`   | <p>json format</p>                                          |
| node                            | `Object[]` | <p>Node list</p>                                            |
| node.node_id                    | `Int`      | <p>Node ID</p>                                              |
| node.node_ip                    | `String`   | <p>Node IP</p>                                              |
| node.node_port                  | `Int`      | <p>Node port</p>                                            |
| node.node_name                  | `String`   | <p>Node name</p>                                            |
| node.node_mac                   | `String`   | <p>Node MAC address</p>                                     |
| node.node_remark                | `String`   | <p>Remark</p>                                               |
| node.node_cpu_percent_total     | `Int`      | <p>Total CPU usage rate</p>                                 |
| node.node_cpu_percent_using     | `Int`      | <p>Current CPU usage rate</p>                               |
| node.node_memory_size_total     | `Int`      | <p>Total memory size, unit: MB</p>                          |
| node.node_memory_size_using     | `Int`      | <p>Current usage size of memory, unit: MB</p>               |
| node.node_cpu_core_count        | `Int`      | <p>Number of CPU cores</p>                                  |
| node.node_pause_times           | `String`   | <p>Node pause times</p>                                     |
| node.node_status                | `String`   | <p>Node status, " offline&quot; or &quot; running&quot;</p> |
| node.node_task_running          | `Boolean`  | <p>Whether a node task is running</p>                       |
| node.node_operating_system      | `String`   | <p>Operating system</p>                                     |
| node.node_computer_name         | `String`   | <p>Computer name</p>                                        |
| node.node_user_name             | `String`   | <p>User name</p>                                            |
| node.node_system_start_datetime | `String`   | <p>Node startup time</p>                                    |
| node.node_connect_datetime      | `String`   | <p>Node connection time</p>                                 |
| node.node_disconnect_datetime   | `String`   | <p>Node disconnection time</p>                              |
| node.node_disk_count            | `Int`      | <p>Number of disks</p>                                      |
| node.node_disks                 | `Object[]` | <p>Disk information list</p>                                |
| node.node_disks.name            | `String`   | <p>Disks name</p>                                           |
| node.node_disks.size_total      | `Int`      | <p>Total disk capacity (unit: MB)</p>                       |
| node.node_disks.size_using      | `Int`      | <p>The used capacity of the disk (unit: MB)</p>             |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "code": 202,
        "body": "{\"version\":\"1.0.0\",\"result\":true,\"code\":1000,\"message\":\"ok\",\"node_size\":1,\"node\":[{\"node_id\":1048576,\"node_ip\":\"127.0.0.1\",\"node_port\":62270,\"node_name\":\"\",\"node_remark\":\"\",\"node_cpu_percent_total\":800,\"node_cpu_percent_using\":520,\"node_memory_size_total\":16271,\"node_memory_size_using\":11550,\"node_cpu_core_count\":8,\"node_pause_times\":0,\"node_status\":\"running\",\"node_task_running\":false,\"node_operating_system\":\"Windows 10  LTSC\",\"node_computer_name\":\"LINYONGJIE\",\"node_user_name\":\"linyj\",\"node_mac\":\"94:de:80:62:8d:ac\",\"node_system_start_datetime\":\"2021-05-17 09:33:20\",\"node_connect_datetime\":\"2021-06-05 14:19:37\",\"node_disconnect_datetime\":\"\",\"node_disk_count\":4,\"node_disks\":[{\"name\":\"C:\",\"size_total\":114471,\"size_using\":53050},{\"name\":\"D:\",\"size_total\":307200,\"size_using\":52693},{\"name\":\"E:\",\"size_total\":323584,\"size_using\":5791},{\"name\":\"F:\",\"size_total\":323081,\"size_using\":6884}]}]}",
        "error": null
    },
    "result": true,
    "message": "OK"
}
```

# <a name='UserResource'></a> UserResource

## <a name='Create user'></a> Create user
[Back to top](#top)

```
POST /api/users/create
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>(Necessary)  Account</p> |
| password | `String` | <p>(Necessary)  Password , using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| status | `Boolean` | <p>(Optional)  Account status switch</p> |
| email | `String` | <p>(Necessary)  Email</p> |
| name | `String` | <p>(Optional)  Name</p> |
| roleId | `Int` | <p>(Necessary) Role ID</p> |
| deptIdList                    | `list`     | <p>(Optional)  Department id list, which records the department ids of all departments to which the user belongs</p> |
| needUpdatePwd                 | `Boolean`  | <p>(Optional)  Whether to force users to change their passwords upon the first login</p> |
| createEmailNotificationSwitch | `Boolean`  | <p>(Optional) Switch of sending email after the user is successfully created</p> |
| emailNotificationType         | `Int`      | <p>(Optional) User email notification sending mode. 0: Account number and password sent in one email; 1: The account and password are sent in different emails</p> |
| loginLinkType                 | `Int`      | <p>(Optional) Login mode. 0: log in to the web page and desktop client. 1: Log in to the website. 2 Log in to the desktop client</p> |
| storageId | `Int` | <p>(Necessary)  Storage id</p> |
| home | `String` | <p>(Optional)  Set the storage path of the account. If the path is not set, the account will be stored in the corresponding storage of storageId</p> |
| vfs                           | `Object[]` | <p>(Optional)  Virtual directory</p>                         |
| vfs.alias                     | `String`   | <p>Alias of the virtual directory, the name displayed in the file list</p> |
| vfs.storageId                 | `Int`      | <p>Storage ID</p>                                            |
| vfs.path                      | `String`   | <p>The actual path of the virtual directory can be written to the relative or absolute path of the corresponding storage</p> |
| cleanSwitch                   | `Boolean`  | <p>(Optional) Whether to enable automatic file clearing for local storage</p> |
| cToFolder                     | `String`   | <p>(Optional)  Recovery path</p>                             |
| cProperty                     | `Int`      | <p>(Optional)  The time type of the file reclamation judgment. 0: the last access time. 1: the last modification time</p> |
| cTimeDelta                    | `Int`      | <p>(Optional) Number of days</p>                             |
| cFileType                     | `Boolean`  | <p>(Optional) Type of the reclaimed file. 0 : All files; 1: Transfer temporary files, you can set 1 only if cProperty is equal to 0</p> |
| cDelete                       | `Boolean`  | <p>(Optional)  Whether to delete files directly. 0: not deleted 1: deleted</p> |
| cReserveAfterCleanTime        | `Int`      | <p>(Optional) Keep the file for xx days and delete it. The value ranges from 0 to 9999. 0 indicates permanent retention</p> |
| passwordExpirationSwitch      | `Boolean`  | <p>(Optional)  Password validity switch</p>                  |
| passwordExpiration            | `Int`      | <p>(Optional)  Password validity period (days)</p>           |
| accountExpiration             | `Int`      | </p>(Optional) Account expiration period, timestamp (seconds), 0 means no restriction</p> |
| emailSenderType               | `Int`      | <p>(Optional) Email sending method (0: send using system-configured email, 1: send using user-configured email)</p> |
| shareEmailNotificationType    | `Int`      | <p>(Optional) Share link and password email sending type (0: link and password sent in one email; 1: link and password sent in separate emails)</p> |
| whitelistIPSwitch             | `Boolean`  | <p>(Optional)  IP login whitelist switch</p>                 |
| whitelistIP                   | `String`   | <p>(Optional)  Whitelist ip</p>                              |
| freeEmailVerification         | `list`     | <p>(Optional)  No email authentication for login. 0: off 1: on, After enabled, you can log in without the email verification code</p> |
| cTransEncryptSwitch           | `Int`      | <p>(Optional)    Client transmission encryption switch. 0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cHashVerifySwitch             | `Int`      | <p>(Optional)    Client Hash verification switch .   0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cRsyncVerifySwitch            | `Int`      | <p>(Optional)    Client Rsync verification switch.    0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| loginNotice                   | `String`   | <p>(Optional)   The content of the pop-up prompt during login</p> |
| loginNoticeSwitch             | `Boolean`  | <p>(Optional)   Switch for pop-up prompt during login</p>    |

### Parameters examples

`json` - Request-Example:

```json
{
    "email": "test5@test.com",
    "account": "test5",
    "name": "test5",
    "password": "646WaVX4r2jY1dvE0GblRDKBqPokrPJAzZmhGeB7yLm8z95oONQpxkwZMJ3PAevN",
    "roleId": 1,
    "deptIdList": [
        1
    ],
    "status": true,
    "createEmailNotificationSwitch": true,
    "emailNotificationType": 0,
    "needUpdatePwd": true,
    "storageId": 1,
    "home": "test",
    "vfs": [],
    "passwordExpirationSwitch": false,
    "passwordExpiration": 90,
    "emailSenderType": 0,
    "shareEmailNotificationType": 0,
    "whitelistIPSwitch": true,
    "whitelistIP": "127.0.0.1",
    "freeEmailVerification": 0,
    "cHashVerifySwitch": 0,
    "cTransEncryptSwitch": 0,
    "cRsyncVerifySwitch": 0,
    "loginNoticeSwitch": false,
    "cleanSwitch": false,
    "cProperty": 0,
    "cTimeDelta": 7,
    "cFileType": 0,
    "cReserveAfterCleanTime": 30,
    "cDelete": false,
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "user_num": 1000,
        "userId": 2
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1001,
    "value": "Database exception",
    "message": "Database exception",
    "data": null,
    "result": false
}
{
    "code": 1004,
    "value": "Account already existed",
    "message": "Account already existed",
    "data": null,
    "result": false
}
{
    "code": 1005,
    "value": "Password invalid",
    "message": "Password invalid",
    "data": null,
    "result": false
}
{
    "code": 1014,
    "value": "Email already existed",
    "message": "Email already existed",
    "data": null,
    "result": false
}
{
    "code": 1018,
    "value": "Account not allowed",
    "message": "Account not allowed",
    "data": null,
    "result": false
}
{
    "code": 1046,
    "value": "illegal request",
    "message": "illegal request",
    "data": null,
    "result": false
}
{
    "code": 1066,
    "value": "invalid path",
    "message": "invalid path",
    "data": null,
    "result": false
}
{
    "code": 1068,
    "value": "email auth error",
    "message": "email auth error",
    "data": null,
    "result": false
}
{
    "code": 1080,
    "value": "version not support",
    "message": "version not support",
    "data": null,
    "result": false
}
{
    "code": 1097,
    "value": "virtual path format invalid",
    "message": "virtual path format invalid",
    "data": null,
    "result": false
}
{
    "code": 4004,
    "value": "storage id does not exist",
    "message": "storage id does not exist",
    "data": null,
    "result": false
}
{
    "code": 4016,
    "value": "User relevance group does not exist",
    "message": "User relevance group does not exist",
    "data": null,
    "result": false
}
{
    "code": 4018,
    "value": "transIgnoreSizeUnit value error",
    "message": "transIgnoreSizeUnit value error",
    "data": null,
    "result": false
}
{
    "code": 4019,
    "value": "IP format is error",
    "message": "IP format is error",
    "data": null,
    "result": false
}
{
    "code": 4066,
    "value": "The user account cannot start with _dl_ or _up_ or @ or _gr_ or _sp_",
    "message": "The user account cannot start with _dl_ or _up_ or @ or _gr_ or _sp_",
    "data": null,
    "result": false
}
{
    "code": 4067,
    "value": "In Windows, the folder path cannot be completely empty",
    "message": "In Windows, the folder path cannot be completely empty",
    "data": null,
    "result": false
}
{
    "code": 4110,
    "value": "Aliases are not case sensitive in windows system",
    "message": "Aliases are not case sensitive in windows system",
    "data": null,
    "result": false
}
{
    "code": 4121,
    "value": "Windows system unable to set root directory",
    "message": "Windows system unable to set root directory",
    "data": null,
    "result": false
}
{
    "code": 4126,
    "value": "Missing email",
    "message": "Missing email",
    "data": null,
    "result": false
}
{
    "code": 4137,
    "value": "Trigger condition does not match rule",
    "message": "Trigger condition does not match rule",
    "data": null,
    "result": false
}
{
    "code": 4146,
    "value": "Department name is not exist",
    "message": "Department name is not exist",
    "data": null,
    "result": false
}
```

## <a name='Update user'></a> Update user
[Back to top](#top)

```
PUT /api/users/update
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `Int` | <p>(Necessary)  User id</p> |
| password | `String` | <p>(Necessary)  Password , using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| status | `Boolean` | <p>(Optional)  Account status switch</p> |
| email | `String` | <p>(Optional)  Email</p> |
| name | `String` | <p>(Optional)  Name</p> |
| roleId                     | `Int`      | <p>(Necessary)  Role id</p>                                  |
| deptIdList                 | `list`     | <p>(Optional)  Department id list, which records the department ids of all departments to which the user belongs</p> |
| needUpdatePwd              | `Boolean`  | <p>(Optional)  Whether to force users to change their passwords upon the first login</p> |
| storageId                  | `Int`      | <p>(Necessary)  Storage id</p>                               |
| home                       | `String`   | <p>(Optional)  Set the storage path of the account. If the path is not set, the account will be stored in the corresponding storage of storageId</p> |
| vfs                        | `Object[]` | <p>(Optional)  Virtual directory</p>                         |
| vfs.alias                  | `String`   | <p>Alias of the virtual directory, the name displayed in the file list</p> |
| vfs.storageId              | `Int`      | <p>Storage ID</p>                                            |
| vfs.path                   | `String`   | <p>The actual path of the virtual directory can be written to the relative or absolute path of the corresponding storage</p> |
| cleanSwitch                | `Boolean`  | <p>(Optional) Whether to enable automatic file clearing for local storage</p> |
| cToFolder                  | `String`   | <p>(Optional)  Recovery path</p>                             |
| cProperty                  | `Int`      | <p>(Optional)  The time type of the file reclamation judgment. 0: the last access time. 1: the last modification time</p> |
| cTimeDelta                 | `Int`      | <p>(Optional) Number of days</p>                             |
| cFileType                  | `Boolean`  | <p>(Optional) Type of the reclaimed file. 0 : All files; 1: Transfer temporary files, you can set 1 only if cProperty is equal to 0</p> |
| cDelete                    | `Boolean`  | <p>(Optional)  Whether to delete files directly. 0: not deleted 1: deleted</p> |
| cReserveAfterCleanTime     | `Int`      | <p>(Optional) Keep the file for xx days and delete it. The value ranges from 0 to 9999. 0 indicates permanent retention</p> |
| passwordExpirationSwitch   | `Boolean`  | <p>(Optional)  Password validity switch</p>                  |
| passwordExpiration         | `Int`      | <p>(Optional)  Password validity period (days)</p>           |
| accountExpiration          | `Int`      | <p>(Optional)  Account validity period, timestamp (seconds), 0 indicates no limit</p> |
| emailSenderType            | `Int`      | <p>(Optional) Sending mailbox mode: 0: sends the email from the system configured mailbox 1: sends the email from the user configured mailbox</p> |
| shareEmailNotificationType | `Int`      | <p>(Optional) Share link and password email sending type. 0: The link and password are sent in one email; 1: The link and password are sent in separate emails</p> |
| whitelistIPSwitch          | `Boolean`  | <p>(Optional)  IP login whitelist switch</p>                 |
| whitelistIP                | `String`   | <p>IP addresses that allow users to log in, with semicolons when multiple IP addresses are used; partition</p> |
| freeEmailVerification      | `list`     | <p>No email authentication for login. 0: off 1: on, After enabled, you can log in without the email verification code</p> |
| cTransEncryptSwitch        | `Int`      | <p>Client transmission encryption switch. 0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cHashVerifySwitch          | `Int`      | <p>Client Hash verification switch .   0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cRsyncVerifySwitch         | `Int`      | <p>Client Rsync verification switch.    0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| loginNotice                | `String`   | <p>(Optional)   The content of the pop-up prompt during login</p> |
| loginNoticeSwitch          | `Boolean`  | <p>(Optional)   Switch for pop-up prompt during login</p>    |

### Parameters examples

`json` - Request-Example:

```json
{
    "email": "test5@test.com",
    "account": "test5",
    "name": "test5",
    "roleId": 1,
    "deptIdList": [
        1
    ],
    "status": true,
    "needUpdatePwd": true,
    "storageId": 1,
    "home": "test",
    "vfs": [],
    "passwordExpirationSwitch": false,
    "passwordExpiration": 90,
    "accountExpiration": 0,
    "emailSenderType": 0,
    "shareEmailNotificationType": 0,
    "whitelistIPSwitch": true,
    "whitelistIP": "127.0.0.1",
    "freeEmailVerification": 0,
    "cHashVerifySwitch": 0,
    "cTransEncryptSwitch": 0,
    "cRsyncVerifySwitch": 0,
    "loginNoticeSwitch": false,
    "loginNotice": "",
    "cleanSwitch": false,
    "cProperty": 0,
    "cTimeDelta": 7,
    "cFileType": 0,
    "cToFolder": "",
    "cReserveAfterCleanTime": 30,
    "cDelete": false,
    "userId": 6
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1001,
    "value": "Database exception",
    "message": "Database exception",
    "data": null,
    "result": false
}
{
    "code": 1014,
    "value": "Email already existed",
    "message": "Email already existed",
    "data": null,
    "result": false
}
{
    "code": 1046,
    "value": "illegal request",
    "message": "illegal request",
    "data": null,
    "result": false
}
{
    "code": 1068,
    "value": "email auth error",
    "message": "email auth error",
    "data": null,
    "result": false
}
{
    "code": 1080,
    "value": "version not support",
    "message": "version not support",
    "data": null,
    "result": false
}
{
    "code": 1081,
    "value": "user id not found",
    "message": "user id not found",
    "data": null,
    "result": false
}      
{
    "code": 1097,
    "value": "virtual path format invalid",
    "message": "virtual path format invalid",
    "data": null,
    "result": false
}
{
    "code": 4004,
    "value": "storage id does not exist",
    "message": "storage id does not exist",
    "data": null,
    "result": false
}
{
    "code": 4016,
    "value": "User relevance group does not exist",
    "message": "User relevance group does not exist",
    "data": null,
    "result": false
}
{
    "code": 4019,
    "value": "IP format is error",
    "message": "IP format is error",
    "data": null,
    "result": false
}
{
    "code": 4110,
    "value": "Aliases are not case sensitive in windows system",
    "message": "Aliases are not case sensitive in windows system",
    "data": null,
    "result": false
}
{
    "code": 4121,
    "value": "Windows system unable to set root directory",
    "message": "Windows system unable to set root directory",
    "data": null,
    "result": false
}
{
    "code": 4137,
    "value": "Trigger condition does not match rule",
    "message": "Trigger condition does not match rule",
    "data": null,
    "result": false
}
{
    "code": 4146,
    "value": "Department name is not exist",
    "message": "Department name is not exist",
    "data": null,
    "result": false
}
```

## <a name='Get all user information'></a> Get all user information
[Back to top](#top)

```
GET /api/users/list
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>(Optional)   Query field - Account</p> |
| email | `String` | <p>(Optional)   Query field - Email</p> |
| is_locked | `Boolean` | <p>(Optional)   Query field - Lock or not</p> |
| is_online | `Boolean` | <p>(Optional)    Query field - Whether it is online</p> |
| name | `String` | <p>(Optional)   Query field - Name</p> |
| order | `Int` | <p>(Optional)    Sorting mode, descending by default, 1: ascending</p> |
| pageNum | `Int` | <p>(Optional)   Number of pages</p> |
| pageSize | `Int` | <p>(Optional) The number of pages per page, depending on the actual situation, if there is a limit on the number of pages, it needs to be increased, you can choose 10 / page, 20 / page, 30 / page, 40 / page, 50 / page</p> |

### Parameters examples

`String` - Request-Example:

```String
/api/users/list?pageNum=1&account=test
```
### Success response

#### Success response 

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| users | `list` | <p>User list</p> |
| total | `int` | <p>Total query results</p> |
| size | `int` | <p>Quantity per page</p> |
| current | `int` | <p>Current page count</p> |
| pages | `int` | <p>Total pages</p> |
| account | `String` | <p>Account</p> |
| accountExpiration | `int` | <p>Account expiration period</p> |
| name | `String` | <p>Name</p> |
| email | `String` | <p>Email</p> |
| status                     | `Boolean` | <p>Status (ture: enabled, False: disabled)</p>               |
| accountType                | `int`     | <p>Account type (2: General user 4: LDAP/AD user 5: Email user 6: Linux system user 8: OpenID Connect user 9: External authentication user controlled by Raysync)</p> |
| userLockedFlag             | `Boolean` | <p>User lock flag (whether locked)</p>                       |
| loginFailTimes             | `int`     | <p>Login failures times</p>                                  |
| userLockedStartTime        | `int`     | <p>Start time for locking a user after xx incorrect passwords are entered (timestamp).  0 Indicates that the user does not enter incorrect passwords or the user is locked due to too many incorrect passwords (timestamp cleared).</p> |
| needUpdatePwd              | `Boolean` | <p>Whether to change the password</p>                        |
| userLockedFinishTime       | `int`     | <p>End time of locking after xx incorrect passwords (timestamp). 0 Indicates that the user does not enter incorrect passwords or the user is locked due to too many incorrect passwords (timestamp cleared).</p> |
| userHomeSize               | `int`     | <p>User home directory size: MB,GB,TB</p>                    |
| userHomeTotal              | `int`     | <p>Total user home directory size: MB,GB,TB</p>              |
| file_count                 | `int`     | <p>Number of files</p>                                       |
| folder_count               | `int`     | <p>Number of folder</p>                                      |
| userHomeFlag               | `Boolean` | <p>User home directory flag</p>                              |
| emailSenderType            | `int`     | <p>Sending mailbox mode (0: sends the message using the system configured mailbox 1: sends the message using the user configured mailbox)</p> |
| emailAccount               | `String`  | <p>Email account</p>                                         |
| emailPassword              | `String`  | <p>Email password</p>                                        |
| emailSmtpHost              | `String`  | <p>SMTP host</p>                                             |
| emailFromName              | `String`  | <p>Sender's name</p>                                         |
| emailSmtpPort              | `String`  | <p>SMTP port (for example: 465)</p>                          |
| emailEncryptType           | `String`  | <p>Email encryption type '1': SSL encryption '2': TLS encryption</p> |
| emailType                  | `int`     | <p>Email type  0:gmail 1:AOL 2:iCloud 3:MSN 4:Microsoft 365 5:outlook.com 6:Hotmail.com 7:Live.com 8:Yahoo! 9:Others</p> |
| shareEmailNotificationType | `int`     | <p>Share download email notification types. 0: The link and password are sent in one email. 1: The link and password are sent in different emails</p> |
| whitelistIPSwitch          | `Boolean` | <p>Whether to enable whitelist IP addresses</p>              |
| whitelistIP                | `String`  | <p>IP addresses that allow users to log in, with semicolons when multiple IP addresses are used; partition</p> |
| create_time                | `String`  | <p>Create time</p>                                           |
| freeEmailVerification      | `int`     | <p>No email authentication for login. 0: off 1: on, After enabled, you can log in without the email verification code</p> |
| cHashVerifySwitch          | `int`     | <p>Client Hash verification switch .   0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cTransEncryptSwitch        | `int`     | <p>Client transmission encryption switch. 0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| cRsyncVerifySwitch         | `int`     | <p>Client Rsync verification switch.    0: not configured 1: forcibly enabled 2: forcibly disabled 3: no limit is set. Priority: The user's configuration  &gt; Server configuration &gt; Client configuration, server configuration &gt; Client configuration</p> |
| loginNotice                | `String`  | <p>The content of the pop-up prompt during login</p>         |
| loginNoticeSwitch          | `Boolean` | <p>Switch for pop-up prompt during login</p>                 |
| userId                     | `int`     | <p>User ID</p>                                               |
| departments                | `list`    | <p>Department information list, including the department ID(an integer), department name (user-defined name), and department path (including the relationship between departments)</p> |
| online_info                | `dict`    | <p>User online information (If the user is not online: empty {}, if the user is online: {IP address: online platform (1: the web page is online, 2: the client is online)}</p> |
| groupList                  | `list`    | <p>Group file library information (User does not join the group: empty []; User joins the group: returns the information of the joined group, see the group interface for details)</p> |
| roleId                     | `int`     | <p>Roled id</p>                                              |
| roleName                   | `String`  | <p>Role name</p>                                             |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "users": [
            {
                "id": 1,
                "account": "test",
                "accountExpiration": 0,
                "name": "test",
                "email": "test@gmail.com",
                "status": true,
                "accountType": 2,
                "userLockedFlag": false,
                "loginFailTimes": 0,
                "userLockedStartTime": 0,
                "needUpdatePwd": false,
                "userLockedFinishTime": 0,
                "userHomeSize": 0,
                "userHomeTotal": 0,
                "file_count": 0,
                "folder_count": 0,
                "userHomeFlag": false,
                "emailSenderType": 0,
                "emailAccount": "",
                "emailPassword": "",
                "emailSmtpHost": "smtp.gmail.com",
                "emailFromName": "",
                "emailSmtpPort": "465",
                "emailEncryptType": "1",
                "emailType": 0,
                "shareEmailNotificationType": 0,
                "whitelistIPSwitch": false,
                "whitelistIP": "",
                "create_time": "2023-11-30 11:44:19",
                "freeEmailVerification": 0,
                "cHashVerifySwitch": 0,
                "cTransEncryptSwitch": 0,
                "cRsyncVerifySwitch": 0,
                "loginNotice": "",
                "loginNoticeSwitch": false,
                "userId": 1,
                "departments": [
                    {
                        "deptId": 1,
                        "deptName": "local",
                        "deptPath": "/0/1"
                    }
                ],
                "online_info": {},
                "groupList": [],
                "roleId": 3,
                "roleName": "roleName",
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1,
        "total_users": 1
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1001,
    "value": "Database exception",
    "message": "Database exception",
    "data": null,
    "result": false
}
```

## <a name='Get user information'></a> Get user information
[Back to top](#top)

```
GET /api/users/:user_id
```

Returns a single ordinary user's full profile for the **default space (spaceId = 1)**. The `user` object merges:

- `User.to_basic_dict()` — account, lock state, quotas, personal SMTP, whitelist, etc.
- `SpaceUserConfig.to_user_dict()` — `spaceId`, `home`, `storageId`, `roleId`, recycle / member settings
- `PermissionRoleModel.to_user_dict()` — menus (`clientMenuDict`, `pcMenuDict`), `permission`, path allow/deny lists, transfer speed and suffix rules, etc.

Additional fields computed on the server:

| Field | Description |
|-------|-------------|
| `homeRootDir` | Root path of the user's bound storage from `get_storage_home_path(storageId)`: local disk → absolute `OssHome`; object storage → normalized path prefix. Empty string if storage is missing. |
| `home` | If the configured home in space member config is empty **and** storage exists, it is filled with `getUserPath(home, account, userId)` (default folder name rule). If storage is missing, `home` is set to `""`. If home was already set in DB, it is returned as stored. |

Nested collections:

| Field | Description |
|-------|-------------|
| `user.vfs` | Virtual folders for this user in the default space. Each item is `VirtualFolder.to_basic_dict()` merged with `Storage.to_storage_dict()` (`storageId`, `storageName`, `isDeleted`). Entries whose storage no longer exists are omitted. |
| `user.departments` | `{ deptId, deptPath, deptName }` for each department the user belongs to. |

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Bearer token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user_id | `Int` | <p>(Required in URL path) User id, minimum 1</p> |
| userId | `Int` | <p>(Optional query) If provided, overrides the path `user_id`</p> |

### Parameters examples

`String` - Request-Example:

```String
GET /api/users/1
GET /api/users/1?userId=2
```

### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `Object` | <p>Merged user + space member + role fields; see introduction above</p> |
| user.homeRootDir | `String` | <p>Storage root path for the user's `storageId`</p> |
| user.home | `String` | <p>Home folder relative segment (or computed default when empty in DB)</p> |
| user.vfs | `Array` | <p>Virtual folders with storage summary</p> |
| user.departments | `Array` | <p>Department list</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "user": {
            "id": 1,
            "userId": 1,
            "account": "test",
            "name": "test",
            "email": "test@example.com",
            "accountType": 2,
            "status": true,
            "spaceId": 1,
            "home": "test",
            "homeRootDir": "D:/raysync/storage",
            "storageId": 1,
            "roleId": 1,
            "permission": 131071,
            "clientMenuDict": {},
            "pcMenuDict": {},
            "vfs": [],
            "departments": []
        }
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4007,
    "value": "user id does not exist",
    "message": "user id does not exist",
    "data": null,
    "result": false
}
```

```json
{
    "code": 4084,
    "value": "Space relative user id is not exist",
    "message": "Space relative user id is not exist",
    "data": null,
    "result": false
}
```

## <a name='Delete user'></a> Delete user
[Back to top](#top)

```
DELETE /api/users/delete
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| users | `list` | <p>(Necessary)  User id list </p> |
| removeFolder | `Boolean` | <p>(Optional)  The default is False. Whether to delete the empty user folder</p> |

### Parameters examples

`json` - Request-Example:

```json
{"users": [1]}
```
`json` - Request-Example:

```json
{
"users":[84],
"removeFolder":true
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4007,
    "value": "user id does not exist",
    "message": "user id does not exist"
    "data": null,
    "result": false,
}
```

## <a name='Lock user'></a> Lock user
[Back to top](#top)

```
PATCH /api/users/lock
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| status | `Boolean` | <p>(Necessary)   Locked status (true: locked, false: unlocked)</p> |
| userId | `Int` | <p>(Optional)   User id</p> |
| account | `String` | <p>(Optional)  User account (choose between userId and account)</p> |

### Parameters examples

`json` - Request-Example:

```json
{"status":true,"userId":1}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4007,
    "value": "user id does not exist",
    "message": "user id does not exist",
    "data": null,
    "result": false
}
```

## <a name='Copy user'></a> Copy user
[Back to top](#top)

```
POST /api/users/copy
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>(Necessary)   Account</p> |
| password | `String` | <p>(Necessary)   Password , using hashid encrypted ciphertext password (See API interface authentication Mode description)</p> |
| email | `String` | <p>(Necessary)   Email</p> |
| copyId | `Int` | <p>(Necessary)   id of the replication user</p> |
| name | `String` | <p>(Optional)  Name</p> |
| deptIdList | `list` | <p>(Optional)  Department id list, which records the department ids of all departments to which the user belongs</p> |
| createEmailNotificationSwitch | `Boolean` | <p>(Optional) Switch of sending email after the user is successfully created</p> |
| emailNotificationType | `Int` | <p>(Optional) User email notification sending mode. 0: Account number and password sent in one email; 1: The account and password are sent in different emails</p> |
| loginLinkType | `Int` | <p>(Optional) Login mode. 0: log in to the web page and desktop client. 1: Log in to the website. 2 Log in to the desktop client</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "email": "test6@test.com",
    "account": "test6",
    "password": "646WaVX4r2jY1dvE0GblRDKBqPokrPJAzZmhGeB7y11Lm8z95oONQpxkwZMJ3PAevN",
    "deptIdList": [],
    "createEmailNotificationSwitch": false,
    "emailNotificationType": 0,
    "copyId": 6
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4126,
    "value": "Missing email",
    "message": "Missing email",
    "data": null,
    "result": false
}
```

# <a name='PermissionRoleResource'></a> PermissionRoleResource

## <a name='Get user role list'></a> Get user role list

[Back to top](#top)

```
GET /api/permission/role/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type     | Description                 |
| -------- | -------- | --------------------------- |
| roleName | `String` | <p>(Optional) Role name</p> |

### Parameters examples

`String` - Request-Example:  

```String
/api/permission/role/list?roleName=User
```

### Success response

#### Success response

| Name              | Type      | Description                  |
| ----------------- | --------- | ---------------------------- |
| roleName          | `String`  | <p>Role name</p>             |
| roleId            | `Int`     | <p>Role id</p>               |
| isDefault         | `Boolean` | <p>Is default role</p>       |
| creatorName       | `String`  | <p>Creator name</p>          |
| lastUpdatedName   | `String`  | <p>Last updated by</p>       |
| createTime        | `String`  | <p>Creation time</p>         |
| updateTime        | `String`  | <p>Update time</p>           |
| relativeUserCount | `Int`     | <p>Associated user count</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "roleInfo": [
            {
                "roleId": 1,
                "roleName": "Default User",
                "roleType": 1,
                "isDefault": true,
                "creatorName": "Admin",
                "lastUpdatedName": "Admin",
                "createTime": "2025-01-13 11:55:05",
                "updateTime": "2025-02-25 12:20:20",
                "relativeUserCount": 6
            },
            {
                "roleId": 3,
                "roleName": "userrole3",
                "roleType": 1,
                "isDefault": false,
                "creatorName": "Admin",
                "lastUpdatedName": "Admin",
                "createTime": "2025-01-22 14:58:33",
                "updateTime": "2025-02-25 12:20:20",
                "relativeUserCount": 1
            }
        ]
    },
    "result": true,
    "message": "OK"
}
```

# <a name='UserGroupResource'></a> UserGroupResource

## <a name='Get Group File Library List'></a> Get Group File Library List

[Back to top](#top)

```
GET /api/user/group/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name      | Type     | Description                                |
| --------- | -------- | ------------------------------------------ |
| groupName | `String` | <p>(Optional) Group name</p>               |
| roleId    | `Int`    | <p>(Optional) Permission id</p>            |
| pageSize  | `Int`    | <p>(Optional) Number of items per page</p> |
| pageNum   | `Int`    | <p>(Optional) Page number</p>              |

### Success response

#### Success response 

| Name              | Type       | Description                               |
| ----------------- | ---------- | ----------------------------------------- |
| groupId           | `Int`      | <p>Group id</p>                           |
| groupName         | `String`   | <p>Group name</p>                         |
| groupHome         | `String`   | <p>Group home directory</p>               |
| userHomeSize      | `Int`      | <p>Group storage used size</p>            |
| userHomeTotal     | `Int`      | <p>Group storage total size</p>           |
| roleId            | `Int`      | <p>Permission id</p>                      |
| file_count        | `Int`      | <p>Number of files in group storage</p>   |
| folder_count      | `Int`      | <p>Number of folders in group storage</p> |
| group_creator_id  | `Int`      | <p>Group creator id</p>                   |
| creatorName       | `String`   | <p>Group creator name</p>                 |
| creatorEmail      | `String`   | <p>Group creator email</p>                |
| storageId         | `Int`      | <p>Storage id</p>                         |
| vfs               | `Object[]` | <p>Virtual directory</p>                  |
| vfs.alias         | `String`   | <p>Alias</p>                              |
| vfs.storageId     | `Int`      | <p>Storage ID</p>                         |
| vfs.path          | `String`   | <p>Path</p>                               |
| relativeAdminList | `Object[]` | <p>Associated admin list</p>              |
| relativeUserList  | `Object[]` | <p>Associated user list</p>               |
| relativeDeptList  | `Object[]` | <p>Associated department list</p>         |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "groupList": [
            {
                "groupId": 1,
                "groupName": "1",
                "groupHome": "",
                "group_creator_id": 1,
                "userHomeSize": 0,
                "userHomeTotal": 0,
                "roleId": 2,
                "file_count": 0,
                "folder_count": 0,
                "userHomeFlag": false,
                "creatorName": "admin",
                "creatorEmail": null,
                "relativeAdminList": [
                    {
                        "adminId": 1,
                        "adminEmail": null,
                        "adminAccount": "admin"
                    }
                ],
                "relativeUserList": [
                    {
                        "id": 1,
                        "account": "test",
                        "home": "",
                        "name": "",
                        "email": "test@test.com",
                        "accountType": 2,
                        "userGroupPermission": 16383
                    }
                ],
                "vfs": [],
                "relativeDeptList": [
                    {
                        "deptId": 1,
                        "parentId": 0,
                        "deptPath": "/0/1",
                        "deptName": "testDept",
                        "status": 0,
                        "creatorId": 1,
                        "deptGroupPermission": 16383,
                        "id": 1
                    }
                ]
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

# <a name='PermissionGroupResource'></a> PermissionGroupResource

## <a name='Get Group File Library Permission List'></a> Get Group File Library Permission List

[Back to top](#top)

```
GET /api/permission/group/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type     | Description                 |
| -------- | -------- | --------------------------- |
| roleName | `String` | <p>(Optional) Role Name</p> |

### Parameters examples

`String` - Request-Example:  

```String
/api/permission/group/list?roleName=1
```

### Success response

#### Success response 

| Name               | Type      | Description                   |
| ------------------ | --------- | ----------------------------- |
| roleId             | `Int`     | <p>Role ID</p>                |
| roleName           | `String`  | <p>Role name</p>              |
| isDefault          | `Boolean` | <p>Is default role</p>        |
| creatorName        | `String`  | <p>Creator name</p>           |
| lastUpdatedName    | `String`  | <p>Last updated by</p>        |
| createTime         | `String`  | <p>Creation time</p>          |
| updateTime         | `String`  | <p>Update time</p>            |
| relativeUserCount  | `Int`     | <p>Associated user count</p>  |
| relativeGroupCount | `Int`     | <p>Associated group count</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "roleInfo": [
            {
                "roleId": 2,
                "roleName": "Default Group1233",
                "isDefault": true,
                "creatorName": "Admin",
                "lastUpdatedName": "Admin",
                "createTime": "2025-01-13 11:55:05",
                "updateTime": "2025-01-22 16:58:37",
                "relativeGroupCount": 3,
                "relativeUserCount": 2
            }
        ]
    },
    "result": true,
    "message": "OK"
}
```

# <a name='NodeResource'></a> NodeResource

## <a name='Get node information'></a> Get node information

[Back to top](#top)

```
POST /api/machine/node
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name | Type     | Description                 |
| ---- | -------- | --------------------------- |
| url  | `String` | <p>(Necessary) Node url</p> |

### Parameters examples

`json` - Request-Example:

```json
{
  "url": "/api/node_list?page_index=0&page_size=10",
}
```

### Success response

#### Success response

| Name                            | Type       | Description                                                 |
| ------------------------------- | ---------- | ----------------------------------------------------------- |
| body                            | `String`   | <p>json format</p>                                          |
| node                            | `Object[]` | <p>Node list</p>                                            |
| node.node_id                    | `Int`      | <p>Node ID</p>                                              |
| node.node_ip                    | `String`   | <p>Node IP</p>                                              |
| node.node_port                  | `Int`      | <p>Node port</p>                                            |
| node.node_name                  | `String`   | <p>Node name</p>                                            |
| node.node_mac                   | `String`   | <p>Node MAC address </p>                                    |
| node.node_remark                | `String`   | <p>Remark</p>                                               |
| node.node_cpu_percent_total     | `Int`      | <p>Total CPU usage rate</p>                                 |
| node.node_cpu_percent_using     | `Int`      | <p>Current CPU usage rate</p>                               |
| node.node_memory_size_total     | `Int`      | <p>Total memory size, unit: MB</p>                          |
| node.node_memory_size_using     | `Int`      | <p>Current usage size of memory, unit: MB</p>               |
| node.node_cpu_core_count        | `Int`      | <p>Number of CPU cores</p>                                  |
| node.node_pause_times           | `String`   | <p>Node pause times</p>                                     |
| node.node_status                | `String`   | <p>Node status, " offline&quot; or &quot; running&quot;</p> |
| node.node_task_running          | `Boolean`  | <p>Whether a node task is running</p>                       |
| node.node_operating_system      | `String`   | <p>Operating system</p>                                     |
| node.node_computer_name         | `String`   | <p>Computer name</p>                                        |
| node.node_user_name             | `String`   | <p>User name</p>                                            |
| node.node_system_start_datetime | `String`   | <p>Node startup time</p>                                    |
| node.node_connect_datetime      | `String`   | <p>Node connection time</p>                                 |
| node.node_disconnect_datetime   | `String`   | <p>Node disconnection time</p>                              |
| node.node_disk_count            | `Int`      | <p>Number of disks</p>                                      |
| node.node_disks                 | `Object[]` | <p>Disk information list</p>                                |
| node.node_disks.name            | `String`   | <p>Disks name</p>                                           |
| node.node_disks.size_total      | `Int`      | <p>Total disk capacity (unit: MB)</p>                       |
| node.node_disks.size_using      | `Int`      | <p>The used capacity of the disk (unit: MB)</p>             |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "code": 202,
        "body": "{\"version\":\"1.0.0\",\"result\":true,\"code\":1000,\"message\":\"ok\",\"node_size\":1,\"node\":[{\"node_id\":1048576,\"node_ip\":\"127.0.0.1\",\"node_port\":62270,\"node_name\":\"\",\"node_remark\":\"\",\"node_cpu_percent_total\":800,\"node_cpu_percent_using\":520,\"node_memory_size_total\":16271,\"node_memory_size_using\":11550,\"node_cpu_core_count\":8,\"node_pause_times\":0,\"node_status\":\"running\",\"node_task_running\":false,\"node_operating_system\":\"Windows 10  LTSC\",\"node_computer_name\":\"LINYONGJIE\",\"node_user_name\":\"linyj\",\"node_mac\":\"94:de:80:62:8d:ac\",\"node_system_start_datetime\":\"2021-05-17 09:33:20\",\"node_connect_datetime\":\"2021-06-05 14:19:37\",\"node_disconnect_datetime\":\"\",\"node_disk_count\":4,\"node_disks\":[{\"name\":\"C:\",\"size_total\":114471,\"size_using\":53050},{\"name\":\"D:\",\"size_total\":307200,\"size_using\":52693},{\"name\":\"E:\",\"size_total\":323584,\"size_using\":5791},{\"name\":\"F:\",\"size_total\":323081,\"size_using\":6884}]}]}",
        "error": null
    },
    "result": true,
    "message": "OK"
}
```

# <a name='TransmissionResource'></a> TransmissionResource

## <a name='Get real-time information of peer-to-peer transfer'></a> Get real-time information of peer-to-peer transfer

[Back to top](#top)

```
GET /api/transmission/ptp/current
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Success response

#### Success response

| Name                                  | Type       | Description                                                  |
| ------------------------------------- | ---------- | ------------------------------------------------------------ |
| account                               | `String`   | <p>User account</p>                                          |
| email                                 | `String`   | <p>User Email</p>                                            |
| file_max                              | `Int`      | <p>Total number of files</p>                                 |
| file_max_size                         | `Int`      | <p>Total file size (unit :Byte)</p>                          |
| file_size                             | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| ip                                    | `String`   | <p>IP address</p>                                            |
| node_mac                              | `String`   | <p>Node mac address</p>                                      |
| run_timestamp                         | `Int`      | <p>Start time stamp</p>                                      |
| end_timestamp                         | `Int`      | <p>End time stamp</p>                                        |
| storage_id                            | `List`     | <p>Storage ID</p>                                            |
| task_speed                            | `Int`      | <p>Average task transfer speed</p>                           |
| show_name                             | `String`   | <p>Show name</p>                                             |
| task_name                             | `String`   | <p>Task name, which can be used to stop a task</p>           |
| receiver_id                           | `String`   | <p>Receiving ID</p>                                          |
| task_guid                             | `String`   | <p>User GUID</p>                                             |
| type                                  | `Int`      | <p>Transmission type. 1: Upload 2 : Download</p>             |
| country_name                          | `String`   | <p>Country name</p>                                          |
| region_name                           | `String`   | <p>Region</p>                                                |
| city_name                             | `String`   | <p>City</p>                                                  |
| transferring_file_list                | `Object[]` | <p>Per file details</p>                                      |
| transferring_file_list.account        | `String`   | <p>User account</p>                                          |
| transferring_file_list.bytes          | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| transferring_file_list.file           | `String`   | <p>File path</p>                                             |
| transferring_file_list.id             | `Int`      | <p>File list id</p>                                          |
| transferring_file_list.ip             | `String`   | <p>Ip address of the file transfer device</p>                |
| transferring_file_list.offset         | `Int`      | <p>Offset</p>                                                |
| transferring_file_list.progress       | `Int`      | <p>Progress</p>                                              |
| transferring_file_list.speed          | `Int`      | <p>File transfer speed (unit :Byte/s)</p>                    |
| transferring_file_list.task_filecnt   | `Int`      | <p>Number of files</p>                                       |
| transferring_file_list.task_filename  | `String`   | <p>File name</p>                                             |
| transferring_file_list.task_timestamp | `Int`      | <p>Task start time</p>                                       |
| transferring_file_list.task_name      | `String`   | <p>Task name, which can be used to stop a task</p>           |
| transferring_file_list.type           | `Int`      | <p>Transmission type: 1: upload, 2: download</p>             |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "list": [
            {
                "account": "LS@TEST",
                "delete_src_on_finish": false,
                "email": "123456@qq.com",
                "file_max": 1,
                "file_max_size": 487201112,
                "file_pos": 0,
                "file_size": 46661632,
                "from_ip": "127.0.0.1",
                "ip": "127.0.0.1",
                "is_deliver_task": false,
                "is_sync": false,
                "node_mac": "50:EB:F6:EB:27:37",
                "receiver_id": "5974165428",
                "show_name": "pycharm-community-2024.2.1.exe|1|20240905104944536651500",
                "source_path": "C:\\Users\\hehaoming\\Downloads\\pycharm-community-2024.2.1.exe",
                "status": 2,
                "storage_id": [],
                "target_path": "/pycharm-community-2024.2.1.exe",
                "task_guid": "e53092dd0dce4330615b4467fb841803b4a86026885fe479b259f0f9f190c139",
                "task_name": "LS@TEST_pycharm-community-2024.2.1.exe_20240905104944536651500",
                "task_speed": 131216,
                "transferring_file_list": [
                    {
                        "account": "LS@TEST",
                        "bytes": 46661632,
                        "file": "pycharm-community-2024.2.1.exe",
                        "id": 4,
                        "ip": "127.0.0.1",
                        "offset": 0,
                        "progress": 0.09577488899230957,
                        "speed": 130582.3203125,
                        "task_filecnt": 1,
                        "task_filename": "pycharm-community-2024.2.1.exe",
                        "task_timestamp": "20240905104944536651500",
                        "taskname": "LS@TEST_pycharm-community-2024.2.1.exe_20240905104944536651500",
                        "type": 1
                    }
                ],
                "type": 1,
                "country_name": "\u5185\u7f51",
                "region_name": "\u5185\u7f51",
                "city_name": ""
            }
        ],
        "all_file_info": []
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get real-time information of general transfer'></a> Get real-time information of general transfer

[Back to top](#top)

```
GET /api/transmission/ordinary/current
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Success response

#### Success response

| Name                                  | Type       | Description                                                  |
| ------------------------------------- | ---------- | ------------------------------------------------------------ |
| account                               | `String`   | <p>User account</p>                                          |
| email                                 | `String`   | <p>User Email</p>                                            |
| file_max                              | `Int`      | <p>Total number of files</p>                                 |
| file_max_size                         | `Int`      | <p>Total file size (unit :Byte)</p>                          |
| file_size                             | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| ip                                    | `String`   | <p>IP address</p>                                            |
| node_mac                              | `String`   | <p>Node mac address</p>                                      |
| run_timestamp                         | `int`      | <p>Start time stamp</p>                                      |
| end_timestamp                         | `int`      | <p>End time stamp</p>                                        |
| storage_id                            | `List`     | <p>Storage ID</p>                                            |
| task_speed                            | `Int`      | <p>Average task transfer speed (unit :Byte/s)</p>            |
| show_name                             | `String`   | <p>Show name</p>                                             |
| task_name                             | `String`   | <p>Task name, which can be used to stop a task</p>           |
| type                                  | `Int`      | <p>Transmission type. 1: Upload； 2 : Download</p>           |
| country_name                          | `String`   | <p>Country name</p>                                          |
| region_name                           | `String`   | <p>Region</p>                                                |
| city_name                             | `String`   | <p>City</p>                                                  |
| transferring_file_list                | `Object[]` | <p>Per file details</p>                                      |
| transferring_file_list.bytes          | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| transferring_file_list.file           | `String`   | <p>File path</p>                                             |
| transferring_file_list.id             | `Int`      | <p>File list id</p>                                          |
| transferring_file_list.ip             | `String`   | <p>Ip address</p>                                            |
| transferring_file_list.offset         | `Int`      | <p>Offset</p>                                                |
| transferring_file_list.progress       | `Int`      | <p>Progress (0: start; 1: complete. For example, 0.5 indicates that the transfer progress is 50%.</p> |
| transferring_file_list.speed          | `Int`      | <p>File transfer speed (unit :Byte/s)</p>                    |
| transferring_file_list.task_filecnt   | `Int`      | <p>Number of files</p>                                       |
| transferring_file_list.task_filename  | `String`   | <p>File name</p>                                             |
| transferring_file_list.task_timestamp | `String`   | <p>Task start time</p>                                       |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "list": [
            {
                "account": "test",
                "email": "test@test.com",
                "end_timestamp": 1720599869,
                "file_max": 1,
                "file_max_size": 48047752,
                "file_pos": 0,
                "file_size": 786432,
                "ip": "127.0.0.1",
                "is_deliver_task": false,
                "is_sync": false,
                "node_mac": "00:FF:20:F1:20:F1",
                "run_timestamp": 1720599864,
                "server_task_uid": "",
                "show_name": "RayLink_v8.0.8.9.exe|1|20240710162424373799700",
                "storage_id": [
                    1
                ],
                "task_name": "test_RayLink_v8.0.8.9.exe_20240710162424373799700",
                "task_speed": 78855,
                "transferring_file_list": [
                    {
                        "bytes": 786432,
                        "file": "/root/user/test/RayLink_v8.0.8.9.exe",
                        "id": 6,
                        "ip": "127.0.0.1",
                        "offset": 0,
                        "progress": 0.0163677167147398,
                        "speed": 138140.171875,
                        "task_filecnt": 1,
                        "task_filename": "RayLink_v8.0.8.9.exe",
                        "task_timestamp": "20240710162424373799700"
                    }
                ],
                "type": 1,
                "country_name": "Internal Network",
                "region_name": "Internal Network",
                "city_name": ""
            }
        ],
        "all_file_info": []
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get real-time information of sync transfer'></a> Get real-time information of sync transfer

[Back to top](#top)

```
POST /api/machine/node
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name    | Type     | Description                |
| ------- | -------- | -------------------------- |
| url     | `String` | <p>(Necessary)  url</p>    |
| headers | `String` | <p>(Necessary) headers</p> |

### Parameters examples

`json` - Request-Example:

```json
{
  "url": "/api/task_list",
  "headers": {
    "Content-Type": "application/json;charset=UTF-8"
  }
}
```

### Success response

#### Success response

| Name                                  | Type       | Description                                                  |
| ------------------------------------- | ---------- | ------------------------------------------------------------ |
| body                                  | `String`   | <p>json format</p>                                           |
| account                               | `String`   | <p>User account</p>                                          |
| email                                 | `String`   | <p>User Email</p>                                            |
| start_timestamp                       | `Int`      | <p>Start time stamp</p>                                      |
| end_timestamp                         | `Int`      | <p>End time stamp</p>                                        |
| run_timestamp                         | `Int`      | <p>Run timestamp</p>                                         |
| speed                                 | `Int`      | <p>Speed</p>                                                 |
| show_name                             | `String`   | <p>Show name</p>                                             |
| task_id                               | `Int`      | <p>Task ID</p>                                               |
| task_name                             | `String`   | <p>Task name</p>                                             |
| task_type                             | `Int`      | <p>Transmission type. 1: Upload； 2 : Download</p>           |
| source_path                           | `String`   | <p>Source path</p>                                           |
| target_path                           | `String`   | <p>Target path</p>                                           |
| status                                | `Int`      | <p>Status: 1: In the queue. 2: In transmission; 3: Stopping; 4: Stopped</p> |
| file_max                              | `Int`      | <p>Total number of files</p>                                 |
| file_max_size                         | `Int`      | <p>Total file size (unit :Byte)</p>                          |
| file_size                             | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| file_pos                              | `Int`      | <p>File offset</p>                                           |
| interval_time                         | `Int`      | <p>Interval time</p>                                         |
| ip                                    | `String`   | <p>IP address</p>                                            |
| node_mac                              | `String`   | <p>Node mac address</p>                                      |
| check_before_transfer                 | `Object`   | <p>Check configuration information before transfer</p>       |
| check_before_transfer.check_time      | `Int`      | <p>check time</p>                                            |
| check_before_transfer.enable          | `Boolean`  | <p>Check whether enabled</p>                                 |
| delete_src_on_finish                  | `Boolean`  | <p>Whether to delete the source file after the transfer is complete</p> |
| duplex_sync                           | `Boolean`  | <p>Whether it is bidirectional synchronization</p>           |
| enable_regex_filter                   | `Boolean`  | <p>Whether to enable the regular expression filter</p>       |
| enable_save_acl                       | `Boolean`  | <p>Whether to save ACL attributes</p>                        |
| enable_share_file_after_upload        | `Boolean`  | <p>Whether to enable enable sharing others' downloads after successful upload</p> |
| enable_sync_source_file_updated       | `Boolean`  | <p>Whether to synchronize source file updates</p>            |
| file_update_type                      | `Int`      | <p>File update type</p>                                      |
| full_path                             | `Boolean`  | <p>Whether to use the full path</p>                          |
| is_enabled                            | `Boolean`  | <p>Enable or not</p>                                         |
| is_p2p                                | `Boolean`  | <p>Is it P2P transmission</p>                                |
| node_id                               | `Int`      | <p>Node ID</p>                                               |
| only_trans_src_include                | `Boolean`  | <p>Whether to transfer only source files</p>                 |
| receiver_id                           | `String`   | <p>Receiver ID</p>                                           |
| regex_filter                          | `String`   | <p>Regular filter</p>                                        |
| save_file_modify_time                 | `Boolean`  | <p>Whether to save the file modification time</p>            |
| server_task_uid                       | `String`   | <p>Server task UID</p>                                       |
| share_emails                          | `String`   | <p>Email address for sharing others downloads when upload is successful'</p> |
| share_emails_content                  | `String`   | <p>The content of the email</p>                              |
| share_emails_password                 | `String`   | <p>Password for sharing link</p>                             |
| skip_more_than_size                   | `Int`      | <p>Skip when the file exceeds the specified size</p>         |
| sync_delete_target_file               | `Boolean`  | <p>Whether to delete the target file synchronously</p>       |
| transIgnoreReg                        | `String`   | <p>Ignore the transmitted regular expression</p>             |
| transIgnoreRegSwitch                  | `Boolean`  | <p>The switch of Ignore transmitted regular expressions</p>  |
| transIncludeReg                       | `String`   | <p>Contains the regular expression of the transfer</p>       |
| transIncludeRegSwitch                 | `Boolean`  | <p>The switch for containing transmitted regular expressions</p> |
| trigger_type                          | `Int`      | <p>Trigger type</p>                                          |
| upload_task                           | `Boolean`  | <p>Whether it is an upload task</p>                          |
| use_ssl                               | `Boolean`  | <p>Whether to use SSL/p>                                     |
| weekly_trigger                        | `Int`      | <p>Weekly triggering</p>                                     |
| country_name                          | `String`   | <p>Country name</p>                                          |
| region_name                           | `String`   | <p>Region</p>                                                |
| city_name                             | `String`   | <p>City</p>                                                  |
| transferring_file_list                | `Object[]` | <p>Per file details</p>                                      |
| transferring_file_list.bytes          | `Int`      | <p>The size of the file transferred this time (unit :Byte)<</p> |
| transferring_file_list.file           | `String`   | <p>File path</p>                                             |
| transferring_file_list.id             | `Int`      | <p>File list id</p>                                          |
| transferring_file_list.ip             | `String`   | <p>Ip address</p>                                            |
| transferring_file_list.offset         | `Int`      | <p>Offset</p>                                                |
| transferring_file_list.progress       | `Int`      | <p>Progress (0: start; 1: complete. For example, 0.5 indicates that the transfer progress is 50%.</p> |
| transferring_file_list.speed          | `Int`      | <p>Speed (unit : Byte/s)</p>                                 |
| transferring_file_list.task_filecnt   | `Int`      | <p>Number of files</p>                                       |
| transferring_file_list.task_filename  | `String`   | <p>File name</p>                                             |
| transferring_file_list.task_timestamp | `Int`      | <p>Task start time</p>                                       |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "code": 200,
        "body": "{}", //JSON format string, see below
        "error": null
    },
    "result": true,
    "message": "OK"
}
// body:
{
    "code": 200,
    "value": "OK",
    "data": {
        "list": [
            {
                "account": "nina",
                "check_before_transfer": {
                    "check_time": 0,
                    "enable": false
                },
                "delete_src_on_finish": false,
                "duplex_sync": false,
                "enable_regex_filter": false,
                "enable_save_acl": false,
                "enable_share_file_after_upload": false,
                "enable_sync_source_file_updated": false,
                "end_timestamp": 1721294741,
                "file_max": 1,
                "file_max_size": 4379901952,
                "file_name_size_list": [
                    {
                        "name": "CentOS-7-x86_64-DVD-1611.iso",
                        "size": "4.08GB"
                    }
                ],
                "file_pos": 1,
                "file_size": 4379901952,
                "file_update_type": 0,
                "full_path": false,
                "interval_time": 3600,
                "ip": "172.16.4.206",
                "is_enabled": true,
                "is_p2p": true,
                "node_id": 1048594,
                "node_mac": "F0:2F:74:F4:8A:31",
                "only_trans_src_include": false,
                "receiver_id": "1021855273",
                "regex_filter": "",
                "run_timestamp": 1721294739,
                "save_file_modify_time": true,
                "server_task_uid": "",
                "share_emails": "",
                "share_emails_content": "",
                "share_emails_password": "",
                "show_name": "CentOS-7-x86_64-DVD-1611.iso|1|20240718172539618371100",
                "skip_more_than_size": -1,
                "source_path": "E:\\CentOS-7-x86_64-DVD-1611.iso",
                "speed": 0,
                "start_timestamp": 0,
                "status": 5,
                "sync_delete_target_file": false,
                "target_path": "/",
                "task_id": 31,
                "task_name": "CentOS-7-x86_64-DVD-1611.iso|1|20240718172539618371100",
                "task_type": 2,
                "transIgnoreReg": "",
                "transIgnoreRegSwitch": false,
                "transIncludeReg": "",
                "transIncludeRegSwitch": false,
                "trigger_type": 2,
                "upload_task": true,
                "use_ssl": false,
                "weekly_trigger": 0,
                "email": "liutianhua@rayvision.coma",
                "from_ip": "",
                "transferring_file_list": [],
                "type": 1,
                "task_speed": 0,
                "country_name": "\u5185\u7f51",
                "region_name": "\u5185\u7f51",
                "city_name": ""
            }
        ],
        "all_file_info": []
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get real-time information of web transfer'></a> Get real-time information of web transfer

[Back to top](#top)

```
GET /api/transmission/web/current
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Success response

#### Success response

| Name                                  | Type       | Description                                                  |
| ------------------------------------- | ---------- | ------------------------------------------------------------ |
| account                               | `String`   | <p>User account</p>                                          |
| email                                 | `String`   | <p>User Email</p>                                            |
| file_max                              | `Int`      | <p>Total number of files</p>                                 |
| file_max_size                         | `Int`      | <p>Total file size (unit :Byte)</p>                          |
| file_size                             | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| ip                                    | `String`   | <p>IP address</p>                                            |
| node_mac                              | `String`   | <p>Node mac address</p>                                      |
| run_timestamp                         | `String`   | <p>Start time stamp</p>                                      |
| end_timestamp                         | `String`   | <p>End time stamp</p>                                        |
| storage_id                            | `List`     | <p>Storage ID</p>                                            |
| task_speed                            | `Int`      | <p>Average task transfer speed</p>                           |
| show_name                             | `String`   | <p>Show name</p>                                             |
| task_name                             | `String`   | <p>Task name, which can be used to stop a task</p>           |
| type                                  | `Int`      | <p>Transmission type. 1: Upload； 2 : Download</p>           |
| country_name                          | `String`   | <p>Country name</p>                                          |
| region_name                           | `String`   | <p>Region</p>                                                |
| city_name                             | `String`   | <p>City</p>                                                  |
| transferring_file_list                | `Object[]` | <p>Per file details</p>                                      |
| transferring_file_list.bytes          | `Int`      | <p>The size of the file transferred this time (unit :Byte)</p> |
| transferring_file_list.file           | `String`   | <p>File path</p>                                             |
| transferring_file_list.id             | `Int`      | <p>File list id</p>                                          |
| transferring_file_list.ip             | `String`   | <p>Ip address</p>                                            |
| transferring_file_list.offset         | `Int`      | <p>Offset</p>                                                |
| transferring_file_list.progress       | `Int`      | <p>Progress (0: start; 1: complete. For example, 0.5 indicates that the transfer progress is 50%.</p> |
| transferring_file_list.speed          | `Int`      | <p>File transfer speed (unit :Byte/s)</p>                    |
| transferring_file_list.task_filecnt   | `Int`      | <p>Number of files</p>                                       |
| transferring_file_list.task_filename  | `String`   | <p>File name</p>                                             |
| transferring_file_list.task_timestamp | `String`   | <p>Task start time</p>                                       |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "list": [
            {
                "account": "test",
                "email": "test@test.com",
                "end_timestamp": 1720689524,
                "file_max": 1,
                "file_max_size": 704645989,
                "file_pos": 0,
                "file_size": 142868480,
                "ip": "127.0.0.1",
                "is_deliver_task": false,
                "node_mac": "",
                "run_timestamp": 1720689513,
                "server_task_uid": "",
                "show_name": "RaySync-6.8.8.0-Pro-win64.zip|1|20240711171833877545700",
                "storage_id": [
                    1
                ],
                "task_name": "RaySync-6.8.8.0-Pro-win64.zip|1|20240711171833877545700",
                "task_speed": 14140709,
                "transferring_file_list": [
                    {
                        "bytes": 162529280,
                        "file": "/RaySync-6.8.8.0-Pro-win64.zip",
                        "id": 89501194,
                        "ip": "127.0.0.1",
                        "offset": 0,
                        "progress": 0.2306537926197052,
                        "speed": 14643597.0,
                        "task_filecnt": 1,
                        "task_filename": "RaySync-6.8.8.0-Pro-win64.zip",
                        "task_timestamp": "20240711171833770548600"
                    }
                ],
                "type": 1,
                "country_name": "Internal Network",
                "region_name": "Internal Network",
                "city_name": "",
            }
        ],
        "all_file_info": []
    },
    "result": true,
    "message": "OK"
}
```

# <a name='EventResource'></a> EventResource

## <a name='Create event'></a> Create event

[Back to top](#top)

```
POST /api/event/create
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name                | Type     | Description                                                  |
| ------------------- | -------- | ------------------------------------------------------------ |
| eventName           | `String` | <p> (Necessary) Event name</p>                               |
| eventType           | `int`    | <p>(Necessary)  Event type. 1: File upload done; 2: File upload failed; 3: File download done; 4: File download failed; 5: File(s) delete done; 7: Folder(s) delete done; 9: Folder(s) created done ; 11: File renamed done; 13: Folder renamed done; 67: Web-side upload completed; 68: Web-side upload failed; 69: Web-side download completed; 70: Web-side download failed; 71: Client-side upload completed; 72: Client-side upload failed; 73: Client-side download completed; 74: Client-side download failed; 75:Upload sync completed ; 76: Upload sync failed; 77: Download sync completed; 78: Download sync failed; 79: Two-way sync completed; 80: Two-way sync failed; 81: Peer to Peer sending completed ; 82: Peer to Peer sending failed; 83: Peer to Peer receving completed; 84: Peer to Peer receving failed</p> |
| eventAction         | `int`    | <p>(Optional) Event operation. 1: Command execution; 2: HTTP callback (default value is 1)</p> |
| eventStatus         | `int`    | <p>(Necessary) 0: Disabled; 1: Enable</p>                    |
| eventRemark         | `String` | <p>(Optional)  Remark</p>                                    |
| eventCmdProgramPath | `String` | <p>(Optional)  Event executable program path. This parameter is mandatory when eventAction is set to 1</p> |
| eventCmdArgs        | `String` | <p>(Optional) Executive program parameter</p>                |
| eventCmdTimeout     | `int`    | <p>(Optional) Completion wait time</p>                       |
| httpUrl             | `String` | <p>(Optional) Callback url. This parameter is mandatory when eventAction is set to 2</p> |
| httpHeaders         | `Object` | <p>(Optional) Callback request header. This parameter is mandatory when eventAction is set to 2</p> |
| httpBody            | `Object` | <p>(Optional) Callback request body. This parameter is mandatory when eventAction is set to 2</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "eventStatus": 1,
    "eventType": 1,
    "eventName": "1",
    "eventRemark": "",
    "eventAction": 1,
    "eventCmdTimeout": 10,
    "eventCmdProgramPath": "/root",
    "eventCmdArgs": "test.sh 1",
}
{
  "eventStatus": 1,
  "eventType": 2,
  "eventName": "test2",
  "eventAction": 2,
  "httpUrl": "http://127.0.0.1:8888/api/test",
  "httpHeaders": {
    "Content-Type": "application/json"
  },
  "httpBody": {},
  "eventCmdTimeout": 10
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1043,
    "value": "path not found",
    "data": null,
    "result": false,
    "message": "path not found"
}
```

## <a name='Get event'></a> Get event

[Back to top](#top)

```
GET /api/event/list
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name     | Type  | Description                          |
| -------- | ----- | ------------------------------------ |
| pageNum  | `Int` | <p>(Optional)  Page number</p>       |
| pageSize | `Int` | <p>(Optional)  Quantity per page</p> |

### Success response

#### Success response

| Name                | Type     | Description                                                  |
| ------------------- | -------- | ------------------------------------------------------------ |
| eventName           | `String` | <p>Event name</p>                                            |
| eventType           | `int`    | <p>Event type. 1: File upload done; 2: File upload failed; 3: File download done; 4: File download failed; 5: File(s) delete done; 7: Folder(s) delete done; 9: Folder(s) created done ; 11: File renamed done; 13: Folder renamed done; 67: Web-side upload completed; 68: Web-side upload failed; 69: Web-side download completed; 70: Web-side download failed; 71: Client-side upload completed; 72: Client-side upload failed; 73: Client-side download completed; 74: Client-side download failed; 75:Upload sync completed ; 76: Upload sync failed; 77: Download sync completed; 78: Download sync failed; 79: Two-way sync completed; 80: Two-way sync failed; 81: Peer to Peer sending completed ; 82: Peer to Peer sending failed; 83: Peer to Peer receving completed; 84: Peer to Peer receving failed</p> |
| eventAction         | `int`    | <p>Event operation. 1: Command execution; 2: HTTP callback (default value is 1)</p> |
| eventStatus         | `int`    | <p>0: Disabled; 1: Enable</p>                                |
| eventRemark         | `String` | <p>Remark</p>                                                |
| eventCmdProgramPath | `String` | <p>Event executable program path. This parameter is mandatory when eventAction is set to 1</p> |
| eventCmdArgs        | `String` | <p>Executive program parameter</p>                           |
| eventCmdTimeout     | `int`    | <p>Completion wait time</p>                                  |
| httpUrl             | `String` | <p>Callback url. This parameter is mandatory when eventAction is set to 2</p> |
| httpHeaders         | `Object` | <p>Callback request header. This parameter is mandatory when eventAction is set to 2</p> |
| httpBody            | `Object` | <p>Callback request body. This parameter is mandatory when eventAction is set to 2</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 2,
        "eventList": [
            {
                "eventId": 1,
                "eventName": "test1",
                "eventType": 1,
                "eventAction": 1,
                "eventStatus": 1,
                "eventRemark": "",
                "eventCmdProgramPath": "D:/",
                "eventCmdArgs": "",
                "eventCmdTimeout": 10,
                "httpUrl": "",
                "httpHeaders": {
                    "Content-Type": "application/json"
                },
                "httpBody": {}
            },
            {
                "eventId": 3,
                "eventName": "test2",
                "eventType": 2,
                "eventAction": 2,
                "eventStatus": 1,
                "eventRemark": "",
                "eventCmdProgramPath": "",
                "eventCmdArgs": "",
                "eventCmdTimeout": 10,
                "httpUrl": "http://127.0.0.1:8888/api/test",
                "httpHeaders": {
                    "Content-Type": "application/json"
                },
                "httpBody": {}
            }
        ]
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Delete event'></a> Delete event

[Back to top](#top)

```
DELETE /api/event/delete
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name        | Type   | Description                                                  |
| ----------- | ------ | ------------------------------------------------------------ |
| eventIdList | `list` | <p>(Necessary) List of event IDs that need to be deleted</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "eventIdList": [1,2,3]
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4034,
    "value": "EventId is not exist",
    "data": null,
    "result": false,
    "message": "EventId is not exist"
}
```

## <a name='Modify Event'></a> Modify Event

[Back to top](#top)

```
PUT /api/event/modify
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name                | Type     | Description                                                  |
| ------------------- | -------- | ------------------------------------------------------------ |
| eventId             | `Int`    | <p>(Necessary)  Event Id</p>                                 |
| eventName           | `String` | <p>(Necessary) Event name</p>                                |
| eventType           | `Int`    | <p>(Necessary) Event type. 1: File upload done; 2: File upload failed; 3: File download done; 4: File download failed; 5: File(s) delete done; 7: Folder(s) delete done; 9: Folder(s) created done ; 11: File renamed done; 13: Folder renamed done; 67: Web-side upload completed; 68: Web-side upload failed; 69: Web-side download completed; 70: Web-side download failed; 71: Client-side upload completed; 72: Client-side upload failed; 73: Client-side download completed; 74: Client-side download failed; 75:Upload sync completed ; 76: Upload sync failed; 77: Download sync completed; 78: Download sync failed; 79: Two-way sync completed; 80: Two-way sync failed; 81: Peer to Peer sending completed ; 82: Peer to Peer sending failed; 83: Peer to Peer receving completed; 84: Peer to Peer receving failed</p> |
| eventAction         | `int`    | <p>(Optional)  Event operation. 1: Command execution; 2: HTTP callback (default value is 1)</p> |
| eventStatus         | `int`    | <p>(Necessary) 0: Disabled; 1: Enable</p>                    |
| eventRemark         | `String` | <p>(Optional)  Remark</p>                                    |
| eventCmdProgramPath | `String` | <p>(Optional)  Event executable program path. This parameter is mandatory when eventAction is set to 1</p> |
| eventCmdArgs        | `String` | <p>(Optional)  Executive program parameter</p>               |
| eventCmdTimeout     | `int`    | <p>(Optional)   Completion wait time</p>                     |
| httpUrl             | `String` | <p>(Optional)  Callback url. This parameter is mandatory when eventAction is set to 2</p> |
| httpHeaders         | `Object` | <p>(Optional) Callback request header. This parameter is mandatory when eventAction is set to 2</p> |
| httpBody            | `Object` | <p>(Optional)   Callback request body. This parameter is mandatory when eventAction is set to 2</p> |

### Parameters examples

`json` - Request-Example:

```json
 {
      "eventStatus": 1,
      "eventType": 1,
      "eventName": "test1",
      "eventRemark": "",
      "eventAction": 1,
      "httpHeaders": {
        "Content-Type": "application/json"
      },
      "httpBody": {},
      "eventCmdTimeout": 10,
      "eventCmdProgramPath": "D:/"
}
{
      "eventStatus": 1,
      "eventType": 3,
      "eventName": "test2",
      "eventAction": 2,
      "httpUrl": "http://127.0.0.1:8888/api/test",
      "httpHeaders": {
        "Content-Type": "application/json"
      },
      "httpBody": {},
      "eventCmdTimeout": 10
}
```

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 4035,
    "value": "EventName is exist",
    "data": null,
    "result": false,
    "message": "EventName is exist"
}
```

# <a name='LogsResource'></a> LogsResource

## <a name='Get Transfer Log Details'></a> Get Transfer Log Details

[Back to top](#top)

```
GET /api/logs/transmission/detail
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name           | Type     | Description                                                  |
| -------------- | -------- | ------------------------------------------------------------ |
| subTableDbName | `String` | <p>(Necessary) File name</p>                                 |
| type           | `Int`    | <p>(Necessary) (0-3) 0 for Normal Transfer, 1 for Peer-to-Peer, 2 for Synchronous Transfer, 3 for Web</p> |
| isAll          | `Bool`   | <p>(Optional) Whether to query all</p>                       |
| pageNum        | `String` | <p>(Optional) Page number</p>                                |
| pageSize       | `String` | <p>(Optional) Number of items per page</p>                   |

### Parameters examples

`String` - Request-Example:  

```String
/api/logs/transmission/detail?type=0&subTableDbName=test_20250225180640861.sqlite&pageNum=1&pageSize=10
```

### Success response

#### Success response

| Name                         | Type       | Description                                                  |
| ---------------------------- | ---------- | ------------------------------------------------------------ |
| translogDetail               | `Object[]` | <p>File Details</p>                                          |
| translogDetail.fullName      | `String`   | <p>File Path</p>                                             |
| translogDetail.type          | `Int`      | <p>Transfer Type: 1 for Upload, 2 for Download</p>           |
| translogDetail.status        | `Int`      | <p>Task Status: 0 for Completed, 1 for Incomplete, 2 for Failed</p> |
| translogDetail.username      | `String`   | <p>User Account</p>                                          |
| translogDetail.errorCode     | `Int`      | <p>Error Code: 0 for Normal Transfer, 1 for Network Unconnected or Other Exceptions</p> |
| translogDetail.errorMessage  | `String`   | <p>Error Message</p>                                         |
| translogDetail.startTime     | `String`   | <p>Start Time</p>                                            |
| translogDetail.endTime       | `String`   | <p>End Time</p>                                              |
| translogDetail.timeConsuming | `Int`      | <p>Transfer Duration</p>                                     |
| translogDetail.transSize     | `Int`      | <p>Transfer Size</p>                                         |
| translogDetail.targetSize    | `Int`      | <p>Actual Size Written to Target</p>                         |
| translogDetail.actualSize    | `Int`      | <p>Total Size of Source File</p>                             |
| translogDetail.averageSpeed  | `Int`      | <p>Average Transfer Speed</p>                                |
| translogDetail.clientIP      | `String`   | <p>Client IP</p>                                             |
| translogDetail.dpID          | `String`   | <p>Receiver ID</p>                                           |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "translogDetail": [
            {
                "startTime": "2024-07-10 18:27:13,233",
                "endTime": "2024-07-10 18:27:27,247",
                "username": "test",
                "type": 2,
                "fullName": "/RayLink_v8.0.8.9.exe",
                "timeConsuming": 13.439,
                "transSize": 1835008,
                "targetSize": 1835008,
                "actualSize": 48047752,
                "clientIP": "127.0.0.1",
                "averageSpeed": 136543.4928194062,
                "status": 1,
                "errorCode": 0,
                "errorMessage": ""
            }
        ],
        "size": 10,
        "current": 1,
        "total": 1,
        "pages": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get Single Transfer Log'></a> Get Single Transfer Log

[Back to top](#top)

```
GET /api/logs/transmission/download
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name           | Type     | Description                                                  |
| -------------- | -------- | ------------------------------------------------------------ |
| subTableDbName | `String` | <p>(Necessary) Subtable Name</p>                             |
| type           | `Int`    | <p>(Necessary) (0-4) 0 for Normal Transfer, 1 for Peer-to-Peer, 2 for Synchronous Transfer, 3 for Web Transfer, 4 for Task Dispatch</p> |

### Parameters examples

`String` - Request-Example:

```String
api/logs/transmission/detail?type=0&fileName=test_20240710182713550.log&currentPage=1&pageSize=10
```

### Success response

#### Success response

| Name                         | Type       | Description                                                  |
| ---------------------------- | ---------- | ------------------------------------------------------------ |
| translogDetail               | `Object[]` | <p>Details of Each File</p>                                  |
| translogDetail.fullName      | `String`   | <p>File Path</p>                                             |
| translogDetail.type          | `Int`      | <p> Transfer Type: 1 for Upload, 2 for Download</p>          |
| translogDetail.status        | `Int`      | <p>Task Status: 0 for Completed, 1 for Incomplete, 2 for Failed</p> |
| translogDetail.username      | `String`   | <p>User Account</p>                                          |
| translogDetail.errorCode     | `Int`      | <p>Error Code: 0 for Normal Transfer, 1 for Network Unconnected or Other Exceptions</p> |
| translogDetail.errorMessage  | `String`   | <p>Error Message</p>                                         |
| translogDetail.startTime     | `String`   | <p>Start Time</p>                                            |
| translogDetail.endTime       | `String`   | <p>End Time</p>                                              |
| translogDetail.timeConsuming | `Int`      | <p>Transfer Duration</p>                                     |
| translogDetail.transSize     | `Int`      | <p>Transfer Size</p>                                         |
| translogDetail.targetSize    | `Int`      | <p>Actual Size Written to Target</p>                         |
| translogDetail.actualSize    | `Int`      | <p>Total Size of Source File</p>                             |
| translogDetail.averageSpeed  | `Int`      | <p>Average Transfer Speed</p>                                |
| translogDetail.clientIP      | `String`   | <p>Client IP</p>                                             |
| translogDetail.dpID          | `String`   | <p>Receiver ID</p>                                           |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "translogDetail": [
            {
                "startTime": "2024-07-10 18:27:13,233",
                "endTime": "2024-07-10 18:27:27,247",
                "username": "test",
                "type": 2,
                "fullName": "/RayLink_v8.0.8.9.exe",
                "timeConsuming": 13.439,
                "transSize": 1835008,
                "targetSize": 1835008,
                "actualSize": 48047752,
                "clientIP": "127.0.0.1",
                "averageSpeed": 136543.4928194062,
                "status": 1,
                "errorCode": 0,
                "errorMessage": ""
            }
        ],
        "size": 10,
        "current": 1,
        "total": 1,
        "pages": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get peer-to-peer transfer logs'></a> Get peer-to-peer transfer logs

[Back to top](#top)

```
GET /api/logs/transmission/ptp
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name       | Type     | Description                                                  |
| ---------- | -------- | ------------------------------------------------------------ |
| startTime  | `Int`    | <p>(Optional)Start Time</p>                                  |
| endTime    | `Int`    | <p>(Optional) End Time</p>                                   |
| account    | `String` | <p>(Optional)  User account</p>                              |
| dpID       | `String` | <p>(Optional)  Recipient ID</p>                              |
| pageSize   | `Int`    | <p>(Optional) Page number</p>                                |
| pageNum    | `Int`    | <p>(Optional) Quantity per page</p>                          |
| taskName   | `String` | <p>(Optional) Task name</p>                                  |
| taskStatus | `Int`    | <p>(Optional) Task status. 0: Completed; 1: Not completed; 2: Failed, default returns all types</p> |

### Success response

#### Success response

| Name                  | Type       | Description                                                  |
| --------------------- | ---------- | ------------------------------------------------------------ |
| fileinfo              | `Object[]` | <p>Per file details</p>                                      |
| fileinfo.dpID         | `String`   | <p>Recipient ID</p>                                          |
| fileinfo.taskName     | `String`   | <p>Task name</p>                                             |
| fileinfo.filename     | `String`   | <p>Log file name, used for downloading log interface</p>     |
| fileinfo.taskStatus   | `Int`      | <p>Task status. 0: Completed; 1: Not completed; 2: Failed</p> |
| fileinfo.u_account    | `String`   | <p>User account</p>                                          |
| fileinfo.u_email      | `String`   | <p>User Email</p>                                            |
| fileinfo.errorCode    | `String`   | <p>Error code. 0: Normal transmission; 1: Network disconnected or other abnormalities</p> |
| fileinfo.errorMessage | `String`   | <p>Error message</p>                                         |
| fileinfo.type         | `Int`      | <p>Transmission type. 1: Upload; 2: Download</p>             |
| fileinfo.sourcePath   | `List`     | <p>Source path</p>                                           |
| fileinfo.targetPath   | `List`     | <p>Target path</p>                                           |
| fileinfo.startTime    | `String`   | <p>Start Time</p>                                            |
| fileinfo.endTime      | `String`   | <p>End Time</p>                                              |
| fileinfo.fileCount    | `Int`      | <p>Number of files transferred</p>                           |
| fileinfo.targetSize   | `Int`      | <p>Transmission target size</p>                              |
| fileinfo.averageSpeed | `Int`      | <p>Average transmission speed</p>                            |
| fileinfo.clientIP     | `String`   | <p>Client IP</p>                                             |
| fileinfo.shareAccount | `String`   | <p>The sharer's account</p>                                  |
| fileinfo.country_name | `String`   | <p>Country name</p>                                          |
| fileinfo.region_name  | `String`   | <p>Region</p>                                                |
| fileinfo.city_name    | `String`   | <p>City</p>                                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "fileinfo": [
            {
                "filename": "LS@TEST_7130981242_20240905110003259783300.log",
                "taskName": "2w.xls|1|20240905104758552635800",
                "taskStatus": 0,
                "errorCode": 0,
                "errorMessage": "",
                "sourcePath": [
                    "C:\\Users\\test\\Downloads\\wff\\test\\2w.xls"
                ],
                "targetPath": [
                    "/2w.xls"
                ],
                "clientIP": "172.16.4.35",
                "fileCount": 0,
                "targetSize": 0,
                "startTime": "2024-09-05 11:00:03,203",
                "endTime": "2024-09-05 11:00:03,203",
                "type": 1,
                "averageSpeed": 0.0,
                "u_account": "LS@TEST",
                "shareAccount": "",
                "dpID": "7130981242",
                "country_name": "\u5185\u7f51",
                "region_name": "\u5185\u7f51",
                "city_name": "",
                "u_email": "123456@qq.com"
            }
        ],
        "total": 16,
        "pages": 2,
        "size": 10,
        "current": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get general transfer logs'></a> Get general transfer logs

[Back to top](#top)

```
GET /api/logs/transmission/ordinary
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name       | Type     | Description                                                  |
| ---------- | -------- | ------------------------------------------------------------ |
| startTime  | `Int`    | <p>(Optional) Start Time</p>                                 |
| endTime    | `Int`    | <p>(Optional) End Time</p>                                   |
| account    | `String` | <p>(Optional) User account</p>                               |
| pageSize   | `Int`    | <p>(Optional) Page number</p>                                |
| pageNum    | `Int`    | <p>(Optional)  Quantity per page</p>                         |
| clientIP   | `String` | <p>(Optional) Client IP</p>                                  |
| taskName   | `String` | <p>(Optional) Task name</p>                                  |
| taskStatus | `Int`    | <p>(Optional) Task status. 0: Completed; 1: Not completed; 2: Failed</p> |

### Success response

#### Success response

| Name                  | Type       | Description                                                  |
| --------------------- | ---------- | ------------------------------------------------------------ |
| fileinfo              | `Object[]` | <p>Per file details</p>                                      |
| fileinfo.taskName     | `String`   | <p>Task name</p>                                             |
| fileinfo.filename     | `String`   | <p>Log file name, used for downloading log interface</p>     |
| fileinfo.taskStatus   | `Int`      | <p>Task status. 0: Completed; 1: Not completed; 2: Failed</p> |
| fileinfo.u_account    | `String`   | <p>User account</p>                                          |
| fileinfo.u_email      | `String`   | <p>User Email</p>                                            |
| fileinfo.errorCode    | `String`   | <p>Error code. 0: Normal transmission; 1: Network disconnected or other abnormalities</p> |
| fileinfo.errorMessage | `String`   | <p>Error message</p>                                         |
| fileinfo.type         | `Int`      | <p>Transmission type. 1: Upload; 2: Download</p>             |
| fileinfo.sourcePath   | `List`     | <p>Source path</p>                                           |
| fileinfo.targetPath   | `List`     | <p>Target path</p>                                           |
| fileinfo.startTime    | `String`   | <p>Start Time</p>                                            |
| fileinfo.endTime      | `String`   | <p>End Time</p>                                              |
| fileinfo.fileCount    | `Int`      | <p>Number of files transferred</p>                           |
| fileinfo.targetSize   | `Int`      | <p>Transmission target size</p>                              |
| fileinfo.averageSpeed | `Int`      | <p>Average transmission speed</p>                            |
| fileinfo.clientIP     | `String`   | <p>Client IP</p>                                             |
| fileinfo.shareAccount | `String`   | <p>The sharer's account</p>                                  |
| fileinfo.p_account    | `String`   | <p>Account</p>                                               |
| fileinfo.country_name | `String`   | <p>Country name</p>                                          |
| fileinfo.region_name  | `String`   | <p>Region</p>                                                |
| fileinfo.city_name    | `String`   | <p>City</p>                                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "fileinfo": [
            {
                "filename": "test_20240710171244950.log",
                "taskName": "RayLink_v8.0.8.9.exe|1|20240710162424373799700",
                "taskStatus": 1,
                "errorCode": 26,
                "errorMessage": "Stop by server",
                "sourcePath": [
                    "/download/RayLink_v8.0.8.9.exe"
                ],
                "targetPath": [
                    "/RayLink_v8.0.8.9.exe"
                ],
                "clientIP": "127.0.0.1",
                "fileCount": 1,
                "targetSize": 48047752,
                "startTime": "2024-07-10 17:12:44,764",
                "endTime": "2024-07-10 17:12:49,769",
                "type": 1,
                "averageSpeed": 152261.76185866407,
                "u_account": "test",
                "shareAccount": "",
                "country_name": "Internal Network",
                "region_name": "Internal Network",
                "city_name": "",
                "p_account": "",
                "u_email": "test@test.com"
            },
        ],
        "total": 9,
        "pages": 1,
        "size": 10,
        "current": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get All Transfer Logs'></a> Get All Transfer Logs

[Back to top](#top)

```
GET /api/logs/user/trans_log/get_all
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Success response

#### Success response - `回参`

| Name                  | Type       | Description                                                  |
| --------------------- | ---------- | ------------------------------------------------------------ |
| fileinfo              | `Object[]` | <p>Per file details</p>                                      |
| fileinfo.dpID         | `String`   | <p>Recipient ID</p>                                          |
| fileinfo.taskName     | `String`   | <p>Task name</p>                                             |
| fileinfo.filename     | `String`   | <p>Log file name, used for downloading log interface</p>     |
| fileinfo.taskStatus   | `Int`      | <<p>Task status. 0: Completed; 1: Not completed; 2: Failed</p> |
| fileinfo.u_account    | `String`   | <p>User account</p>                                          |
| fileinfo.u_email      | `String`   | <p>User Email</p>                                            |
| fileinfo.errorCode    | `String`   | <p>Error code. 0: Normal transmission; 1: Network disconnected or other abnormalities</p> |
| fileinfo.errorMessage | `String`   | <p>Error message</p>                                         |
| fileinfo.type         | `Int`      | <p>Transmission type. 1: Upload; 2: Download</p>             |
| fileinfo.sourcePath   | `List`     | <p>Source path</p>                                           |
| fileinfo.targetPath   | `List`     | <p>Target path</p>                                           |
| fileinfo.startTime    | `String`   | <p>Start Time</p>                                            |
| fileinfo.endTime      | `String`   | <p>End Time</p>                                              |
| fileinfo.fileCount    | `Int`      | <p>Number of files transferred</p>                           |
| fileinfo.targetSize   | `Int`      | <p>Transmission target size</p>                              |
| fileinfo.averageSpeed | `Int`      | <p>Average transmission speed</p>                            |
| fileinfo.clientIP     | `String`   | <p>Client IP</p>                                             |
| fileinfo.shareAccount | `String`   | <p>The sharer's account</p>                                  |
| fileinfo.country_name | `String`   | <p>Country name</p>                                          |
| fileinfo.region_name  | `String`   | <p>Region</p>                                                |
| fileinfo.city_name    | `String`   | <p>City</p>                                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "fileinfo": [
            {
                "id": 47,
                "taskName": "test.key|1|20250214144752567312500",
                "targetSize": 536,
                "u_account": "test",
                "shareAccount": "",
                "taskStatus": 0,
                "type": 1,
                "averageSpeed": 1624.242431640625,
                "clientIP": "127.0.0.1",
                "clientMac": "00:FF:8C:8B:8A:E1",
                "dpID": "",
                "startTime": 1739515672,
                "endTime": 1739515673,
                "errorCode": 0,
                "errorMessage": "",
                "fileCount": 1,
                "fileSize": 1,
                "failedCount": 0,
                "finishedCount": 1,
                "transSize": 1,
                "transferredSize": 536,
                "subTableDbName": "test_20250214144752354.sqlite",
                "quickCount": 0,
                "sourcePath": [
                    "D:\\download/test.key"
                ],
                "targetPath": [
                    "/test.key"
                ],
                "country_name": "",
                "region_name": "",
                "city_name": "",
                "p_account": "",
                "u_email": "test@123.com"
            },
        ]
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get sync transfer logs'></a> Get sync transfer logs

[Back to top](#top)

```
GET /api/logs/transmission/synchronize
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name       | Type     | Description                                                  |
| ---------- | -------- | ------------------------------------------------------------ |
| startTime  | `Int`    | <p>(Optional) Start Time</p>                                 |
| endTime    | `Int`    | <p>(Optional) End Time</p>                                   |
| account    | `String` | <p>(Optional)  User account</p>                              |
| pageSize   | `Int`    | <p>(Optional) Page number</p>                                |
| pageNum    | `Int`    | <p>(Optional) Quantity per page</p>                          |
| taskName   | `String` | <p>(Optional) Task name</p>                                  |
| taskStatus | `Int`    | <p>(Optional) Task status. 0: Completed; 1: Not completed; 2: Failed</p> |

### Success response

#### Success response

| Name                  | Type       | Description                                                  |
| --------------------- | ---------- | ------------------------------------------------------------ |
| fileinfo              | `Object[]` | <p>Per file details</p>                                      |
| fileinfo.taskName     | `String`   | <p>Task name</p>                                             |
| fileinfo.filename     | `String`   | <p>Log file name, used for downloading log interface</p>     |
| fileinfo.taskStatus   | `Int`      | <p>Task status. 0: Completed; 1: Not completed; 2: Failed</p> |
| fileinfo.u_account    | `String`   | <p>User account</p>                                          |
| fileinfo.u_email      | `String`   | <p>User Email</p>                                            |
| fileinfo.errorCode    | `String`   | <p>Error code. 0: Normal transmission; 1: Network disconnected or other abnormalities</p> |
| fileinfo.errorMessage | `String`   | <p>Error message</p>                                         |
| fileinfo.type         | `Int`      | <p>Transmission type. 1: Upload; 2: Download</p>             |
| fileinfo.sourcePath   | `List`     | <p>Source path</p>                                           |
| fileinfo.targetPath   | `List`     | <p>Target path</p>                                           |
| fileinfo.startTime    | `String`   | <p>Start Time</p>                                            |
| fileinfo.endTime      | `String`   | <p>End Time</p>                                              |
| fileinfo.fileCount    | `Int`      | <p>Number of files transferred</p>                           |
| fileinfo.targetSize   | `Int`      | <p>Transmission target size</p>                              |
| fileinfo.averageSpeed | `Int`      | <p>Average transmission speed</p>                            |
| fileinfo.clientIP     | `String`   | <p>Client IP</p>                                             |
| fileinfo.shareAccount | `String`   | <p>The sharer's account</p>                                  |
| fileinfo.p_account    | `String`   | <p>Account</p>                                               |
| fileinfo.country_name | `String`   | <p>Country name</p>                                          |
| fileinfo.region_name  | `String`   | <p>Region</p>                                                |
| fileinfo.city_name    | `String`   | <p>City</p>                                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "fileinfo": [
            {
                "taskName": "$R0",
                "taskStatus": 0,
                "errorCode": 0,
                "errorMessage": "",
                "sourcePath": [
                    "/Users/mlm/Downloads/RaysyncDesktopClient-6.8.81-Win64-Setup/$R0"
                ],
                "targetPath": [
                    "/$R0"
                ],
                "clientIP": "192.168.1.2",
                "fileCount": 1,
                "targetSize": 429163,
                "startTime": "2024-07-10 17:22:58,378",
                "endTime": "2024-07-10 17:22:58,378",
                "type": 1,
                "averageSpeed": 0.0,
                "u_account": "test",
                "shareAccount": "",
                "country_name": "Internal Network",
                "region_name": "Internal Network",
                "city_name": "",
                "p_account": "",
                "u_email": "test@test.com"
            }
        ],
        "total": 1,
        "pages": 1,
        "size": 10,
        "current": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get Web transfer logs'></a> Get Web transfer logs

[Back to top](#top)

```
GET /api/logs/transmission/web
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name       | Type     | Description                                                  |
| ---------- | -------- | ------------------------------------------------------------ |
| startTime  | `Int`    | <p>(Optional) Start Time</p>                                 |
| endTime    | `Int`    | <p>(Optional) End Time</p>                                   |
| account    | `String` | <p>(Optional)  User account</p>                              |
| pageSize   | `Int`    | <p>(Optional) Page number</p>                                |
| pageNum    | `Int`    | <p>(Optional) Quantity per page</p>                          |
| clientIP   | `String` | <p>(Optional) Client IP</p>                                  |
| taskName   | `String` | <p>(Optional) Task name</p>                                  |
| taskStatus | `Int`    | <p>(Optional) Task status. 0: Completed; 1: Not completed; 2: Failed, default returns all types</p> |

### Success response

#### Success response

| Name                  | Type       | Description                                                  |
| --------------------- | ---------- | ------------------------------------------------------------ |
| fileinfo              | `Object[]` | <p>Per file details</p>                                      |
| fileinfo.taskName     | `String`   | <p>Task name</p>                                             |
| fileinfo.filename     | `String`   | <p>Log file name, used for downloading log interface</p>     |
| fileinfo.taskStatus   | `Int`      | <p>Task status. 0: Completed; 1: Not completed; 2: Failed</p> |
| fileinfo.u_account    | `String`   | <p>User account</p>                                          |
| fileinfo.u_email      | `String`   | <p>User Email</p>                                            |
| fileinfo.errorCode    | `String`   | <p>Error code. 0: Normal transmission; 1: Network disconnected or other abnormalities</p> |
| fileinfo.errorMessage | `String`   | <p>Error message</p>                                         |
| fileinfo.type         | `Int`      | <p>Transmission type. 1: Upload; 2: Download</p>             |
| fileinfo.sourcePath   | `List`     | <p>Source path</p>                                           |
| fileinfo.targetPath   | `List`     | <p>Target path</p>                                           |
| fileinfo.startTime    | `String`   | <p>Start Time</p>                                            |
| fileinfo.endTime      | `String`   | <p>End Time</p>                                              |
| fileinfo.fileCount    | `Int`      | <p>Number of files transferred</p>                           |
| fileinfo.targetSize   | `Int`      | <p>Transmission target size</p>                              |
| fileinfo.averageSpeed | `Int`      | <p>Average transmission speed</p>                            |
| fileinfo.clientIP     | `String`   | <p>Client IP</p>                                             |
| fileinfo.shareAccount | `String`   | <p>The sharer's account</p>                                  |
| fileinfo.p_account    | `String`   | <p>Account</p>                                               |
| fileinfo.country_name | `String`   | <p>Country name</p>                                          |
| fileinfo.region_name  | `String`   | <p>Region</p>                                                |
| fileinfo.city_name    | `String`   | <p>City</p>                                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "fileinfo": [
            {
                "taskName": "raysync-test|1|20240710175035701235200",
                "taskStatus": 0,
                "errorCode": 0,
                "errorMessage": "",
                "sourcePath": [
                    "raysync-test"
                ],
                "targetPath": [
                    "/raysync-test"
                ],
                "clientIP": "127.0.0.1",
                "fileCount": 1,
                "targetSize": 131072,
                "startTime": "2024-07-10 17:50:35,035",
                "endTime": "2024-07-10 17:50:35,035",
                "type": 1,
                "averageSpeed": 468114.2857142857,
                "u_account": "test",
                "shareAccount": "",
                "country_name": "Internal Network",
                "region_name": "Internal Network",
                "city_name": "",
                "p_account": "",
                "u_email": "test@test.com"
            },
        ],
        "total": 5,
        "pages": 1,
        "size": 10,
        "current": 1
    },
    "result": true,
    "message": "OK"
}
```

# 

# <a name='ShareLinkResource'></a> ShareLinkResource

## <a name='Get share links for all users'></a> Get share links for all users
[Back to top](#top)

```
GET /api/share/link/list
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| StartTime | `Int` | <p>(Optional) Start Time</p> |
| EndTime | `Int` | <p>(Optional) End Time</p> |
| account | `String` | <p>(Optional)  User account</p> |
| order | `Int` | <p>(Optional) Order. 1: Ascending system; 2: descending order</p> |
| orderBy | `Int` | <p>(Optional) OrderBy. 1: file name; 2: creation time '3: expiration time. 4: Share status</p> |
| pageSize | `Int` | <p>(Optional) Number of items per page</p> |
| pageNum | `Int` | <p>(Optional) Page number</p> |
| shareType | `Int` | <p>(Optional) Share type. 0: download for sharing; 1: Invite to upload</p> |
| shareStatus | `String` | <p>(Optional) Link status</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code | `Int` | <p>Response status code</p> |
| message | `String` | <p>Response message</p> |
| result | `Boolean` | <p>Response data processing results</p> |
| value | `String` | <p>Response value</p> |
| data | `json` | <p>Response data</p> |
| sharelinkinfo | `list` | <p>List of Share link information</p> |
| shareLink | `String` | <p>Share link address</p> |
| shareCreateTime | `Float` | <p>Link creation time, timestamp</p> |
| shareExpireTime | `Float` | <p>Link expiration time, timestamp</p> |
| filename | `list` | <p>List of shared files</p> |
| downloadTimes | `Int` | <p>Number of downloads</p> |
| sharePassword | `String` | <p>Link password</p> |
| shareEmail | `String` | <p>Share link creator email</p> |
| notifyEmail | `String` | <p>Notification email for sharing links</p> |
| shareLinkStatus | `Int` | <p>Link status. 1: In use</p> |
| account | `Sting` | <p>Share the link creator account</p> |
| type | `Int` | <p>0: file, 1: dir, 2: Share multiple</p> |
| shareDisableUser | `String` | <p>Sharing scope</p> |
| shareDisableTime | `Int` | <p>Disable time</p> |
| shareServerPath | `String` | <p>The file path of Share Link</p> |
| accountType | `Int` | <p>The account type of Share Link</p> |
| bindDevice | `String` | <p>Bind the device ID</p> |
| bindSwitch | `Boolean` | <p>The switch for 'binding the first device'</p> |
| shareAllowDownload | `Int` | <p>Share link allows download</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
   {
    "code": 200,
    "value": "OK",
    "data": {
        "current": 1,
        "pages": 1,
        "size": 10,
        "sharelinkinfo": [
            {
                "shareLink": "https://demo.raysync.cn:8091/share/MvkriU7W6LqIPjxonwBX", # Share link address
                "shareCreateTime": 1623298963.6622226, # Link creation time
                "shareExpireTime": 1623466864.691, # Link expiration time
                "filename": [ # List of shared files
                    "logo.png"
                ],
                "downloadTimes": 0,  # Number of downloads
                "sharePassword": "pIJI",  # Link password
                "shareEmail": "linyj_work@raysync.com",  # Share link creator email
                "notifyEmail": "1647@raysync.com",  # Notification email for sharing links
                "shareLinkStatus": 1,  # Link status. 1: In use
                "account": "linyj",  # Share the link creator account
                "type": 0,  # 0: file, 1: dir, 2: Share multiple
                "shareDisableUser": "",  # Sharing scope
                "shareDisableTime": 0,  # Disable time
                "shareServerPath": "/",  # The file path of Share Link
                "accountType": 2, # The account type of Share Link
                "bindDevice": "", # Bind the device ID
                "bindSwitch": false, # The switch for 'binding the first device'
                "shareAllowDownload": 1 # Share link allows download
            }
        ],
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Cancel share link'></a> Cancel share link
[Back to top](#top)

```
PATCH /api/share/link/cancel
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| shareUrlList | `list` | <p>(Necessary)Links that need to be cancelled</p> |

### Parameters examples

`json` - Request-Example:

```json
{
"shareUrlList":["https://linyj.raysync.cn:8091/share/c85485ec-9499-43d3-8914-d08abc66d685"]
}
```
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code | `int` | <p>Response status code</p> |
| message | `String` | <p>Response message</p> |
| result | `Bool` | <p>Response data processing results</p> |
| value | `String` | <p>Response value</p> |
| data | `json` | <p>Response data</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true
}
```

## <a name='Delete External Link'></a> Delete External Link

[Back to top](#top)

```
DELETE /api/share/link/delete
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name         | Type   | Description                               |
| ------------ | ------ | ----------------------------------------- |
| shareUrlList | `list` | <p>(Necessary) Link Cancellation List</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "shareUrlList":["https://raysync.io/share/c85485ec-9499-43d3-8914-d08abc66d685"]
}
```

### Success response

#### Success response - `Success 200`

| Name    | Type     | Description                             |
| ------- | -------- | --------------------------------------- |
| code    | `int`    | <p>Response status code</p>             |
| message | `String` | <p>Response message</p>                 |
| result  | `Bool`   | <p>Response data processing results</p> |
| value   | `String` | <p>Response value</p>                   |
| data    | `json`   | <p>Response data</p>                    |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": null,
    "result": true
}
```

# <a name='StatisticsResource'></a> StatisticsResource

## <a name='Member traffic statistics'></a> Member traffic statistics
[Back to top](#top)

```
GET /api/statistics/flow/user
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| startTime | `float` | <p>(Necessary)  Start time, timestamp</p> |
| endTime | `float` | <p>(Necessary) End time, timestamp</p> |
| pageNum | `Int` | <p>(Optional)   Page number</p> |
| pageSize | `Int` | <p>(Optional)   Quantity per page</p> |
| isAll | `Boolean` | <p>(Optional)   Is all or not</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code | `int` | <p>Response status code</p> |
| message | `String` | <p>Response message</p> |
| result | `Bool` | <p>Response data processing results</p> |
| value | `String` | <p>Response value</p> |
| data | `json` | <p>Response data</p> |
| userId | `Int` | <p>User id</p> |
| userName | `String` | <p>Username</p> |
| userAccount | `String` | <p>User account</p> |
| userEmail | `String` | <p>User email</p> |
| uploadFileCount | `Int` | <p>Number of uploaded files</p> |
| downloadFileCount | `Int` | <p>Downloaded files</p> |
| uploadTraffic | `Int` | <p>Upload traffic, unit: bytes</p> |
| downloadTraffic | `Int` | <p>Download traffic, unit: bytes</p> |
| current | `Int` | <p>Current page</p> |
| pages | `Int` | <p>Total pages</p> |
| size | `Int` | <p>Page size</p> |
| total | `Int` | <p>Total</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "userId": 1, # User ID
                "userName": "", # User Name
                "userAccount": "aaaa", # User Account
                "userEmail": "aaaa@raysync.com", # User Email
                "uploadFileCount": 17364, # Number of Uploaded Files
                "downloadFileCount": 0,  # Number of Downloaded Files
                "uploadTraffic": 846096555,  # Upload Traffic, Unit: Bytes
                "downloadTraffic": 0 # Download Traffic, Unit: Bytes
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get personal file storage usage'></a> Get personal file storage usage
[Back to top](#top)

<p>Gets the storage usage of the space personal file</p>

```
GET /api/statistics/storage/user
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| pageNum | `Int` | <p>(Optional)   Page number</p> |
| pageSize | `Int` | <p>(Optional)  Quantity per page</p> |
### Success response

#### Success response 

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code         | `int`    | <p>Response status code</p>                             |
| message      | `String` | <p>Response message</p>                                 |
| result       | `Bool`   | <p>Response data processing results</p>                 |
| value        | `String` | <p>Response value</p>                                   |
| data         | `json`   | <p>Response data</p>                                    |
| userId       | `Int`    | <p>User id</p>                                          |
| userHomeSize | `Int` | <p>Total file size of user home directory, in Bytes</p> |
| fileCount | `Int` | <p>User file count</p> |
| folderCount | `Int` | <p>Number of user folders</p> |
| userAccount | `String` | <p>User account</p> |
| userEmail | `String` | <p>User email</p> |
| current | `Int` | <p>Current page</p> |
| pages | `Int` | <p>Total pages</p> |
| size | `Int` | <p>Page size</p> |
| total | `Int` | <p>Total</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "userId": 1, # User ID
                "userHomeSize": 289128454, # Total Size of User Home Directory Files, Unit: Bytes
                "fileCount": 8456,  # Number of User Files
                "folderCount": 554,  # Number of User Folders
                "userAccount": "aaaa",  # User Account
                "userEmail": "aaaa@raysync.com"  # User Email
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get space group file library storage usage'></a> Get space group file library storage usage
[Back to top](#top)

<p>Gets the storage usage of the space group file</p>

```
GET /api/statistics/storage/group
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| pageNum | `Int` | <p>(Optional)   Page number</p> |
| pageSize | `Int` | <p>(Optional)  Quantity per page</p> |
### Success response

#### Success response 

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code          | `int`    | <p>Response status code</p>                                |
| message       | `String` | <p>Response message</p>                                    |
| result        | `Bool`   | <p>Response data processing results</p>                    |
| value         | `String` | <p>Response value</p>                                      |
| data          | `json`   | <p>Response data</p>                                       |
| groupId | `Int` | <p>Group id</p> |
| groupName | `String` | <p>Group name</p> |
| groupHomeSize | `Int` | <p>Total size of group file library files, unit: bytes</p> |
| fileCount | `Int` | <p>Group file count</p> |
| folderCount | `Int` | <p>Group folder count</p> |
| current | `Int` | <p>Current page</p> |
| pages | `Int` | <p>Total pages</p> |
| size | `Int` | <p>Page size</p> |
| total | `Int` | <p>Total</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "groupId": 1,  # Group ID
                "groupName": "666",  # Group Name
                "groupHomeSize": 1675,  # Total Size of Group File Library Files, Unit: Bytes
                "fileCount": 1,  # Number of Group Files
                "folderCount": 0  # Number of Group Folders
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get space file statistics'></a> Get space file statistics
[Back to top](#top)

```
GET /api/statistics/storage/space
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| pageNum | `Int` | <p>(Optional)   Page number</p> |
| pageSize | `Int` | <p>(Optional)   Quantity per page</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code      | `int`    | <p>Response status code</p>                   |
| message   | `String` | <p>Response message</p>                       |
| result    | `Bool`   | <p>Response data processing results</p>       |
| value     | `String` | <p>Response value</p>                         |
| data      | `json`   | <p>Response data</p>                          |
| HomeSize | `Int` | <p>Total size of space files, unit: bytes</p> |
| fileCount | `Int` | <p>Total number of space files</p> |
| current   | `Int`    | <p>Current page</p>                           |
| pages     | `Int`    | <p>Total pages</p>                            |
| size      | `Int`    | <p>Page size</p>                              |
| total     | `Int`    | <p>Total</p>                                  |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "HomeSize": 289128454, # Total Size of Space Files, Unit: Bytes
                "fileCount": 8456 # Total Number of Space Files
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Space traffic statistics'></a> Space traffic statistics

[Back to top](#top)

```
GET /api/statistics/flow/space
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| startTime | `float` | <p>(Necessary)  Start time, timestamp</p> |
| endTime | `float` | <p>(Necessary) End time, timestamp</p> |
| type | `Int` | <p>(Optional) Query type, 0: File size 1: Number of files</p> |
| isAll | `Boolean` | <p>(Optional)   Is all or not</p> |
### Success response

#### Success response 

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code            | `int`    | <p>Response status code</p>                                |
| message         | `String` | <p>Response message</p>                                    |
| result          | `Bool`   | <p>Response data processing results</p>                    |
| value           | `String` | <p>Response value</p>                                      |
| data            | `json`   | <p>Response data</p>                                       |
| 1720454400 | `Dict` | <p>Specify the number of files and traffic for one day</p> |
| upload | `Int` | <p>Number of uploaded files</p> |
| download | `Int` | <p>Number of downloaded files</p> |
| uploadTraffic | `Int` | <p>Upload traffic, unit: bytes</p> |
| downloadTraffic | `Int` | <p>Download traffic, unit: bytes</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": { # Using days as the key, represent the number of files and traffic per day
            "1720454400": { # Time, convertible to days
                "upload": 556968101, # Number of uploaded files
                "download": 0,  # Number of downloaded files
                "uploadTraffic": 556968101, # Upload traffic, unit: bytes
                "downloadTraffic": 0 # Download traffic, unit: bytes
            },
            "1720540800": {
                "upload": 289128454,
                "download": 0,
                "uploadTraffic": 289128454,
                "downloadTraffic": 0
            }
        }
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Collaborative statistics'></a> Collaborative statistics
[Back to top](#top)

```
GET /api/statistics/cooperation
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| startTime | `float`   | <p>(Necessary)  Start time, timestamp</p> |
| endTime   | `float`   | <p>(Necessary) End time, timestamp</p>    |
| pageNum | `Int` | <p>(Optional)   Page number</p> |
| pageSize | `Int` | <p>(Optional)  Quantity per page</p> |
| isAll | `Boolean` | <p>(Optional)   Is all or not</p> |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code               | `int`    | <p>Response status code</p>                       |
| message            | `String` | <p>Response message</p>                           |
| result             | `Bool`   | <p>Response data processing results</p>           |
| value              | `String` | <p>Response value</p>                             |
| data               | `json`   | <p>Response data</p>                              |
| userId | `Int` | <p>User id</p> |
| userAccount | `String` | <p>User account</p> |
| userEmail | `String` | <p>User Email</p> |
| shareDownloadCount | `Int` | <p>Number of times users share download links</p> |
| shareUploadCount | `Int` | <p>Number of user invitations to upload links</p> |
| deliveryCount | `Int` | <p>Number of files delivered by users</p> |
| current            | `Int`    | <p>Current page</p>                               |
| pages              | `Int`    | <p>Total pages</p>                                |
| size               | `Int`    | <p>Page size</p>                                  |
| total              | `Int`    | <p>Total</p>                                      |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "userId": 1, # User id
                "userAccount": "aaaa", # User account
                "userEmail": "aaaa@aaa.com", # User Email
                "shareDownloadCount": 4, # Number of times users share download links
                "shareUploadCount": 1, # Number of user invitations to upload links
                "deliveryCount": 0 # Number of files delivered by users
            }
        ],
        "current": 1,   # Current page
        "pages": 1, # Total pages
        "size": 10, # Page size
        "total": 1 # Total
    },
    "result": true,
    "message": "OK"
}
```

## <a name='IP traffic statistics'></a> IP traffic statistics
[Back to top](#top)

```
GET /api/statistics/flow/ip
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzMzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2Njk3Mjl9.cpXBD5bmL6AdCEMoD2c9fJ5vxI5wYegVxUU-7Z0WOEg"
 }
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| startTime | `float` | <p>(Necessary)  Start time, timestamp</p> |
| endTime | `float` | <p>(Necessary) End time, timestamp</p> |
| pageNum   | `Int`     | <p>(Optional)   Page number</p>           |
| pageSize  | `Int`     | <p>(Optional)   Quantity per page</p>     |
| isAll     | `Boolean` | <p>(Optional)   Is all or not</p>         |
### Success response

#### Success response

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| code              | `int`    | <p>Response status code</p>             |
| message           | `String` | <p>Response message</p>                 |
| result            | `Bool`   | <p>Response data processing results</p> |
| value             | `String` | <p>Response value</p>                   |
| data              | `json`   | <p>Response data</p>                    |
| ip | `String` | <p>IP</p> |
| uploadFileCount   | `Int`    | <p>Number of uploaded files</p>         |
| downloadFileCount | `Int`    | <p>Downloaded files</p>                 |
| uploadTraffic     | `Int`    | <p>Upload traffic, unit: bytes</p>      |
| downloadTraffic   | `Int`    | <p>Download traffic, unit: bytes</p>    |
| current           | `Int`    | <p>Current page</p>                     |
| pages             | `Int`    | <p>Total pages</p>                      |
| size              | `Int`    | <p>Page size</p>                        |
| total             | `Int`    | <p>Total</p>                            |

### Success response example

#### Success response example - `Success-Response:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "result": [
            {
                "ip": "121.12.80.215", # ip
                "uploadFileCount": 17364, # Number of uploaded files
                "downloadFileCount": 0, # Downloaded files
                "uploadTraffic": 846096555, # Upload traffic, unit: bytes
                "downloadTraffic": 0    # Download traffic, unit: bytes
            }
        ],
        "current": 1,
        "pages": 1,
        "size": 10,
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

