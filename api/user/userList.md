# `GET` /user

## 用户列表

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| | | | |

### Authorization

`All`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| users | User[] | 用户数组 |

`User`

| Key | Type | Commit |
| --- | --- | --- |
| id | String | |
| realname | String | |
| email | String | |
| github | String | |
| contribution | Integer | |

Failed
