# `POST` /user/add

## 添加用户

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| username | String | True | |
| password | String | True | 前端随机生成并加密 |
| email | String | True | 联系用户的主要方式, 将解密后的密码发到用户的邮箱 |
| github | String | | |
| phone | String | | 11 位电话 |
| QQ | String | | |

### Authorization

`Admin`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `401` 未登录
- `403` 没有权限
