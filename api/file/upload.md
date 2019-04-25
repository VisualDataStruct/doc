# `POST` /file/upload

## 上传文件

### Request

| Key | Type | Required | Commit |
| --- | --- | --- | --- |
| file | File | True | |

### Authorization

`Logined`

### Response

Success

`200 OK`

| Key | Type | Commit |
| --- | --- | --- |
| filename | String | |

Failed

- `401` 未登录
- `422` 表单验证失败
