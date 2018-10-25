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
| algorithms | Algorithm[] | |

`Algorithm`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |
| classification_id | Integer | |
| name | String | |

Failed

- `404` 找不到分类
