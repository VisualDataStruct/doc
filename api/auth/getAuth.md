# `GET` /auth

## 当前登录用户

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| | | | |

### Authorization

`Logined`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| id | String | |
| username | String | |
| realName | String | |
| phone | String | |
| email | String | |
| github | String | |
| contribution | Integer | |

Failed

- `401` 未登录
