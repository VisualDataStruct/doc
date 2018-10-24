# `GET` /user/{id}

## 用户列表

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| | | | |

### Authorization

`Admin Or Self`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| id | String | |
| username | String | |
| realname | String | |
| phone | String | |
| email | String | |
| github | String | |
| contribution | Integer | |

Failed

- `401` 未登录
- `403` 没有权限
- `404` 找不到用户