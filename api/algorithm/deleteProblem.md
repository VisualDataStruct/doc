# `DELETE` /classification/{id}/algorithm/{id}/problem

## 删除题目

> 如果 name 相同，则删除 link 对应的题目，如果没有 link 就将 name 对应的题目全部删除

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | True | |
| link | String | | |

### Authorization

`Login`

### Response

Success

`200 OK`

Failed

- `422` 表单验证错误
- `404` 找不到分类 / 算法 / 题目
- `401` 未登录
