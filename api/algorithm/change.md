# `PUT` /classification/{id}/algorithm/{id}

## 修改算法

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| name | String | | |
| classification_id | Integer | | |
| pseudocode | Json | | |
| jscode | Json | | |
| explain | Json | | |
| CPlusCode | Json | | |

### Authorization

`Login`

### Response

Success

`200 OK`

Failed

- `404` 找不到分类 / 算法
- `401` 未登录
- `422` 表单验证错误
