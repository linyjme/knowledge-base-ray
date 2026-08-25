<a name="top"></a>

# Raysync Web User API Documentation v8.1.8.4

[TOC]

Raysync Web User API interface for integrating web user portal functions

# API interface authentication mode description

**1.API authentication mode**

The Raysync user portal authenticates each access request, that is, each request needs to include the Authorization parameter in the public request parameter to verify the user identity. The information is generated after the user logs in successfully. Otherwise, the API interface cannot be invoked.



**2. Instructions for using authentication mode**

The password is encrypted using Hashids (Hashids is a small open source library that generates short, unique, non-sequential ids from numbers). The salt value can be configured by yourself. The configuration file is **config.ini** and the field is **hashid_salt**, for example: 'hashid_salt = eRuYuw'; The default length is **64** characters.

**Note ** : Modifying the hashid_salt field of the config.ini file will affect the normal background login. To log in to the background normally, delete the hashid_salt configuration.

Encoding step: Convert the string to byte - convert the byte string to the corresponding hexadecimal - encode the string with hashids.

After obtaining the corresponding encryption string, test the login in postman. If the login succeeds, the token value will be returned. When requesting other interfaces, add **Authorization: Bearer JWT_TOKEN** in **headers** to request interfaces normally. As follows:

| Authorization | Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2NzE2MjE5MzIsInVzZXJfaWQiOjEsInJvbGVfaWQiOjEsImFjY291bnQiOiJhZG1pbiIsImFjY291bnRfdHlwZSI6MX0.cRwaH440E6rmqy-KSyMbhLFF-8LkDuu_RX7O0veaIrU |
| ------------- | ------------------------------------------------------------ |



**3. Authentication Example code **

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

**Js example **

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

# <a name='User'></a> User

## Renewal token

[Back to top](#top)

<p>The user renewed the token interface</p>

```
PUT /api/user/auth
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization: | `String` | <p>Bearer refresh_token</p> |

### Header examples

Header-Example:

```json
{
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjE4NzkzMjksInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiY3VycmVudF9oZWFydF90aW1lIjoxNzIwNjY5NzI5LCJpc19yZWZyZXNoIjp0cnVlLCJhY2NvdW50X3R5cGUiOjJ9.mCsOEBB0yqAn7oacqfSgvkT8iaS8T1G_CueVQ5A5kVs"
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
HTTP/1.1 200 OK
{
    "code": 200,
    "value": "OK",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA2NzQwNzEsInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA2NzA0NzF9.cWsQlOugyrEwYQY0mUwStv1XUgI1iwQmpjuj0UzjJfE",  # New token, valid for 1 hour
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjE4ODAwNzEsInVzZXJfaWQiOjEsImFjY291bnQiOiJhYWFhIiwiY3VycmVudF9oZWFydF90aW1lIjoxNzIwNjcwNDcxLCJpc19yZWZyZXNoIjp0cnVlLCJhY2NvdW50X3R5cGUiOjJ9.jrPyUU04yqyesB7Ne_FNIZK_QNIp0QhjdEPCtSjIu6s" # New renewal token, valid for 7 days
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1009,
    "value": "Invalid token",
    "data": null,
    "result": false,
    "message": "Invalid token"
}
```

## <a name='User logout'></a> User logout
[Back to top](#top)

<p>Raysync user logout</p>

```
POST /api/user/logout
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
    "result": true,
    "message": "OK",
}
```

## <a name='User login'></a> User login
[Back to top](#top)

<p>Raysync user login</p>

```
POST /api/user/login
```

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| account | `String` | <p>(Necessary)   Account</p> |
| password | `String` | <p>(Necessary)   Password (using hashid encrypted ciphertext password)</p> |
| emailCode | `String` | <p>(Optional)  Email verification code</p> |
| ==authWay== | `Int` | <p>(Optional) Authentication Method 1: Local User 2: LDAP User 4: Email User  8: System User 64: OIDC User 128: HTTP User 256: OAuth User</p> |



### Parameters examples

`json` - Request-Example:

```json
{
    "account": "aaaa",
    "password": "oEZrRevGojzW94bkV0DdAM8Xg81aoJDKNbNC1xy7Y5NB1OEP32lLp6maKywxJQO4",
    "authWay": 1
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

#### Success response example - `Success-Response 200:`

```json
{
    "code": 200,
    "value": "OK",
    "data": {
        "account": "aaaa", # User account
        "reconnectcnt": 0, # Failed retry times
        "softVersion": "raysync_enterprise",  # Software version
        "actived": 1, # User status
        "web_online": 0,  # Number of online Web users
        "client_online": 0, # Number of client connections
        "protocol_version": "6.8.8.2", # Protocol version
        "client_version": "6.8.8.2", # Client version
        "loginFailTimes": 0, # Login failures times
        "lockPeriod": 180, # Lockout period when a user fails to log in (unit: second)
        "maxLockTimes": 5, # The maximum number of failed login attempts
        "certSelect": 1,  # Obtaining the client certificate 0:oss 1: server
        "disk_capacity": 157120.84765625,  # Free disk space on the server (unit: MB)
        "userId": 7, # User ID
        "accountType": 2, # User account types 1: administrator, 2: general user, 3: sharing account, 4: Ldap/AD user, 5: email user, 6: Linux system user, 7: enterprise wechat user, 8: oidc user, 9: external http authentication user
        "userPwdSwitch": true,  # Whether to allow customers to change the password switch
        "plat_version": 0,
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjA1OTgwNDEsInVzZXJfaWQiOjcsImFjY291bnQiOiJhYWFhIiwiYWNjb3VudF90eXBlIjoyLCJjdXJyZW50X2hlYXJ0X3RpbWUiOjE3MjA1OTQ0NDF9.GAsVIjjZAB5EIMO0iDUz4tiV7oQqm0CGVA8e2wjPjMA", # User access credential token. The validity period is 1 hour
        "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MjE4MDQwNDEsInVzZXJfaWQiOjcsImFjY291bnQiOiJhYWFhIiwiY3VycmVudF9oZWFydF90aW1lIjoxNzIwNTk0NDQxLCJpc19yZWZyZXNoIjp0cnVlLCJhY2NvdW50X3R5cGUiOjJ9.9RAPo-SBqqFrH7_DNPJxaDG1rgHcEgdi9w0yuX6HgJ4", User renewal token; Valid for 7 days
        "loginNoticeSwitch": false,  # Switch of pop-up prompt during login
        "loginNotice": "" # Dialog box displayed during login
    },
    "result": true,
    "message": "OK"
}
```

### Error response example

#### Error response example - `Error-Response:`

```json
{
    "code": 1005,
    "value": "Password invalid",
    "data": {
        "account": "aaaa",
        "reconnectcnt": 0,
        "softVersion": "raysync_enterprise",
        "actived": 1,
        "web_online": 0,
        "client_online": 0,
        "protocol_version": "6.8.8.2",
        "client_version": "6.8.8.2",
        "loginFailTimes": 1,
        "lockPeriod": 180,
        "maxLockTimes": 5,
        "certSelect": 1,
        "disk_capacity": 157133.28515625
    },
    "result": false,
    "message": "Password invalid"
}
```

# <a name='Share link'></a> Share link

## <a name='Create share link'></a> Create share link
[Back to top](#top)

<p>Create share link under user space</p>

```
POST /api/share/link/create
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
| groupId | `int` | <p>(Optional)  Group id</p> |
| shareFiles | `list` | <p>(Necessary)  List of shared files</p> |
| needPassword | `bool` | <p>(Necessary)  Sharing requires a password</p> |
| shareUrlPasswd | `String` | <p>(Necessary)  Share Link password</p> |
| shareEmail | `String` | <p>(Necessary)  Email notification account when sharing</p> |
| shareUrlType | `int` | <p>(Necessary)  Share type (0: upload; 1 Download)</p> |
| shareAllowDownload | `int` | <p>(Necessary)  Download link Whether to allow download (0: not allowed 1 Allow)</p> |
| shareServerPath | `String` | <p>(Necessary)  Address of the shared file</p> |
| shareEmailContent | `String` | <p>(Necessary) Notification email content</p> |
| shareExpireTime | `int` | <p>(Necessary)  Share expiration time</p> |
| accountType | `int` | <p>(Necessary)  Share account type (Specified authentication account type: 2 Local account 4 ad/openldap 5 email 7 Enterprise wechat 8 oidc 9 External http authentication</p> |
| shareBaseUrl | `String` | <p>(Necessary)  Share link url</p> |
| notifyEmail | `String` | <p>(Necessary)  Share a reminder to me email</p> |
| shareSrcType | `int` | <p>(Necessary)  Share file type 0: file, 1: dir, 2: Share multiple files</p> |
| account | `String` | <p>(Necessary)  Creator account</p> |
| emailLanguage | `int` | <p>(Necessary)  0: Chinese, 1: English</p> |
| inviteMemberType | `int` | <p>(Optional)  Invitation Range. Default 0, 0: Owner , 1: Designated person (internal member)）</p> |
| userList | `list` | <p>(Optional)  **Specified user list**  [&quot;email@xx.com&quot;, &quot;account&quot;]</p> |
| fileAlias | `list` | <p>(Optional)   File alias list [{file: &quot;a.txt&quot;, alias: &quot;666&quot;}]</p> |
| deptList | `list` | <p>(Optional)  Designated department list  [id1, id2]</p> |
| allowDelete | `int` | <p>(Optional)  Upload link allowed delete. Default 0, 0: Disallowed, 1: Allowed</p> |
| downloadLimit | `int` | <p>(Optional)  0 No limit, anyone: no limit, 1-99999 times, internal members: no limit, 1-99999 times per person</p> |
| emailSendTime | `int` | <p>(Optional)  The mailbox sends the timestamp periodically. The default value is 0</p> |
| emailSendSwitch | `bool` | <p>(Optional)  Whether to send email notifications</p> |
| sharePrivateEmail | `String` | <p>(Optional)  Private recipient email</p> |
| sharePrivateEmailWithPwd | `bool` | <p>(Optional)  Private recipient whether to receive contains an access password</p> |
| externalEmail | `String` | <p>(Optional)  External recipient mailbox</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "needPassword":true,
    "notifyEmail":"",
    "shareEmail":"",
    "fileAlias": [{file: "a.txt", alias: "666"}]
    "shareEmailContent":"",
    "shareExpireTime":0,
    "shareBaseUrl":"https://linyj.raysync.cn:8091/share/",
    "shareFiles":["666"],
    "shareServerPath":"/",
    "shareUrlType":1,
    "shareUrlPasswd":"kJAF",
    "shareAllowDownload":1,
    "shareSrcType":1,
    "emailLanguage":0,
    "accountType":2,
    "spaceId":1,
    "groupId":0,
    "inviteMemberType":0,
    "userList":[],
    "emailSendTime":0,
    "emailSendSwitch":false
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
    "data": {
        "shareUrl": "https://linyj.raysync.cn:8091/share/55324da5-7182-4b7c-a5ce-cb1095f5b6f8"  # Share Url
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Get user share link'></a> Get user share link
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
| order | `int` | <p>(Optional)  Order.  1: ascending, >1: descending</p> |
| orderBy | `int` | <p>(Optional)  Order By. The value ranges from 1 to 4, 1: file sharing, 2: creation time,3: expiration time, and 4: connection status</p> |
| pageSize | `int` | <p>(Optional)  Page size. The value ranges from 10 to 100.</p> |
| pageNum | `int` | <p>(Optional)  Page start page</p> |
| shareUrlType | `int` | <p>(Optional)  Link type. The value ranges from 0 to 1, 0: upload 1: download</p> |
| ShareStatus | `int` | <p>(Optional)  Share link status. The value can be 1-3, 1: in use, 2: expired, 3: cancelled</p> |
| StartTime | `Int` | <p>(Optional)  </p> |
| EndTime | `Int` | <p>(Optional)  creation time</p> |
### Parameters examples

`json` - Request-Example:

```json
/api/share/link/list?shareUrlType=0&pageNum=1&pageSize=10&StartTime=1738166400&EndTime=1738684799&shareStatus=3&order=1&orderBy=4
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
HTTP/1.1 200 OK
{
    "code": 200,
    "value": "OK",
    "data": {
        "current": 1,
        "pages": 1,
        "size": 10,
        "sharelinkinfo": [ # Share a list of link information
            {
                "shareId": 1, #
                "shareLink": "https://linyj.raysync.cn:8091/share/73467e42-16b5-422a-8f8d-08085ea9ca6a",
                "shareCreateTime": 1720433309.1792657,
                "shareExpireTime": 0,
                "filename": [
                    "666"
                ],
                "downloadTimes": 0,
                "sharePassword": "SLVw",
                "shareEmail": "",
                "sharePrivateEmail": "",
                "sharePrivateEmailWithPwd": false,
                "notifyEmail": "",
                "shareStatus": 1,
                "account": "aaaa",
                "type": 1,
                "shareDisableUser": "",
                "shareDisableTime": 0,
                "shareServerPath": "/",
                "accountType": 2,
                "bindDevice": "",
                "bindSwitch": false,
                "shareAllowDownload": 0,
                "creatorEmail": "aaaa@qq.com",
                "spaceName": "\u9ed8\u8ba4\u7a7a\u95f4",
                "groupName": "",
                "groupId": 0,
                "allowDelete": false,
                "downloadLimit": 0,
                "inviteMemberType": 0,
                "userList": [],
                "deptList": [],
                "externalEmail": ""
            }
        ],
        "total": 1
    },
    "result": true,
    "message": "OK"
}
```

## <a name='Cancel external link'></a> Cancel external link

[Back to top](#top)

```
PATCH /api/share/link/cancel
```

### Headers - `Header`

| Name          | Type     | Description  |
| ------------- | -------- | ------------ |
| Authorization | `String` | <p>token</p> |

### Parameters - `Parameter`

| Name         | Type   | Description                               |
| ------------ | ------ | ----------------------------------------- |
| shareUrlList | `list` | <p>(Required) List of links to cancel</p> |

### Parameters examples

`json` - Request-Example:

```json
{
    "shareUrlList":["https://raysync.io/share/c85485ec-9499-43d3-8914-d08abc66d685"]
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

