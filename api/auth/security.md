# `PUT` /auth/{id}/security

## 修改密码

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| old_password | String | True | sha256 |
| new_password | String | True | sha256 |

### Authorization

`Self`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| token | string | |

Failed

- `422` 表单验证错误
- `404` 找不到用户
- `403` 没有权限
- `401` 密码错误