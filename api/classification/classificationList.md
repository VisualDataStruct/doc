# `GET` /classification

## 分类列表

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
| classifications | Classification[] | logined user can get deleted classifications |

`Classification`

| Key | Type | Commit |
| --- | --- | --- |
| id | Integer | |
| name | String | |
| description | String | |
| sum | Integer | |
| deleted_at | Timestamp | |

Failed
