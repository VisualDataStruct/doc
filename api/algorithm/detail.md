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
| name | String | |
| pseudocode | Array/Json | |
| CPlusCode | Array/Json | |
| jscode | Array/Json | |
| explain | Array/Json | |
| problem | Array/Json | |
| deleted_at | Timestamp | |

Failed

- `404` 找不到分类 or 找不到算法
