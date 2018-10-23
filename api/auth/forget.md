# `POST` /auth/forget

## 忘记密码

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| email | String | True | |

### Authorization

`All`

### Response

Success

`200 OK`

> 将验证码发到用户的邮箱中。

Failed

- `422` 表单验证错误
- `404` 找不到用户
