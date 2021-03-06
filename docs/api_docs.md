localhost
=========
**Version:** 0.1

### /api/v1/admin/locks
---
##### ***POST***
**Description:** Creates a lock given an admin id token

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| passwords | body | A list of passwords to initialize the lock with | No | [ string ] |
| nickname | body | A readable nickname for the lock | No | string |
| status | body | A lock status to initialize the lock to. One of ['CLOSED', 'OPEN', 'OPEN_REQUESTED'] | No | string |
| createdAt | body | The unix milliseconds since epoch in which the lock was registered | No | integer |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A AdminLocksResponse object | [AdminLocksResponse](#adminlocksresponse) |

### /api/v1/locks/{lock_id}/lockStatus
---
##### ***GET***
**Description:** Gets the lock status of a user owned lock

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| lock_id | path | A lock id that the user owns | Yes | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserLockStatusResponse object | [UserLockStatusResponse](#userlockstatusresponse) |

##### ***PUT***
**Description:** Updates a lock status

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| lock_id | path | A unique lock id | Yes | string |
| status | body | The latest lock status to update to. One of ['CLOSED', 'OPEN', 'OPEN_REQUESTED'] | Yes | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserLockStatusResponse object | [UserLockStatusResponse](#userlockstatusresponse) |

### /api/v1/user
---
##### ***GET***
**Description:** Returns user information

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserResponse object | [UserResponse](#userresponse) |

##### ***POST***
**Description:** Returns user information

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserResponse object | [UserResponse](#userresponse) |

### /api/v1/userLocks
---
##### ***GET***
**Description:** Returns a list of locks owned by a user

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserLockResponse object | [UserLockResponse](#userlockresponse) |

##### ***POST***
**Description:** Adds a valid lock id to a user's account

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ownedLockIds | body | A list of lock ids to add to the user | Yes | [ string ] |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 | A UserLockResponse object | [UserLockResponse](#userlockresponse) |

### Models
---

### AdminLocksResponse  

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| created_at | string |  | Yes |
| id | string |  | Yes |
| nickname | string |  | Yes |
| status | string |  | Yes |

### UserLockResponse  

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ownedLockIds | [ string ] |  | Yes |

### UserLockStatusResponse  

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | string |  | Yes |

### UserResponse  

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| displayName | string |  | Yes |
| email | string |  | Yes |
| id | string |  | Yes |