# `POST` /user/add

## 添加用户

> 后端随机生成密码

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| username | String | True | Unique |
| realName | String | True | |
| email | String | True | 联系用户的主要方式, 将随机后的密码发到用户的邮箱, Unique |
| github | String | | |
| phone | String | | 11 位电话 |

### Authorization

`Admin`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `401` 未登录
- `403` 没有权限
