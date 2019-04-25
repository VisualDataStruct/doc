# `POST` /classification/{id}/algorithm

## 添加算法

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | True | |
| blocksXml | String(XML) | True | |
| blocksJson | String(Json) | True | |
| initVar | Json | True | |
| tagName | String | True | |
| CPlusCode | Json | | |

### Authorization

`Login`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |

Failed

- `404` 找不到分类
- `401` 未登录
- `422` 表单验证错误
