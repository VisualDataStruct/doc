# `POST` /login

## 登录

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| username / email | String | True | 使用用户名或者邮箱登录 |
| password | String | True | sha256 |
| remember | Bool | | 记住我(30 days) |

### Authorization

`All`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| token | string | |

Failed

- `422` 表单验证错误
- `404` 找不到用户
- `401` 密码错误