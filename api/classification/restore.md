# `POST` /classification/{id}

## 恢复被删除的分类

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| | | | |

### Authorization

`Logined`

### Response

Success

`200 OK`

Failed

- `401` 未登录
- `404` 找不到这个分类
- `422` 表单验证失败
