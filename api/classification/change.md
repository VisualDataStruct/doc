# `PUT` /classification/{id}

## 修改分类

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | | Unique |
| description | String | | |
| cover | String | | |

### Authorization

`Admin`

### Response

Success

`200 OK`

Failed

- `401` 未登录
- `404` 不存在该分类
- `422` 表单验证失败
