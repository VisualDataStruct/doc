# `POST` /classification

## 添加分类

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | True | Unique |
| description | String | |
| cover | String | | |

### Authorization

`Logined`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |

Failed

- `401` 未登录
- `422` 表单验证失败
