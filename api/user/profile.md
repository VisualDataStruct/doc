# `PUT` /user/{id}

## 修改用户信息

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| email | String | | |
| username | String | | |
| github | String | | |
| phone | String | | |

### Authorization

`Self`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `401` 密码错误
- `403` 没有权限
- `404` 找不到用户