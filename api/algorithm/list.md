# `GET` /classification/{id}/algorithm

## 算法列表

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
| name | String | |
| description | String | |
| sum | Integer | |
| deleted_at | Timestamp | |
| algorithms | Algorithm[] | |

`Algorithm`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |
| classification_id | Integer | |
| name | String | |
| deleted_at | Timestamp | |

Failed

- `404` 找不到分类
