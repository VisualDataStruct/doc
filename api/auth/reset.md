# `POST` /auth/reset

## 重置密码

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| email | String | True | |
| verify | String | True | |
| new_password | String | True | sha256 |

### Authorization

`All`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `404` 找不到用户
- `403` 验证码错误
