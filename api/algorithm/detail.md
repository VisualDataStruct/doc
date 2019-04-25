# `GET` /classification/{id}/algorithm/{id}

## 算法详情

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| | | | |

### Authorization

`All`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |
| classification_id | Integer | |
| tagName | String | |
| name | String | |
| initVar | Array/Json | |
| CPlusCode | Array/Json | |
| blocksXml | Array/Xml | |
| blocksJson | Array/Json | |
| problem | Array/Json | |
| passed | Boolean | |
| deleted_at | Timestamp | |

Failed

- `404` 找不到分类 or 找不到算法
