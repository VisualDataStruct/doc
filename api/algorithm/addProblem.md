# `POST` /classification/{id}/algorithm/{id}/problem

## 添加题目

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | True | |
| link | String | True | |

### Authorization

`Login`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `404` 找不到分类 / 算法
- `401` 未登录
