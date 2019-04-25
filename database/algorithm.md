# Algorithm

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | Increment | True | | | |
| classification_id | Integer | | 0 | | refer to [classification.id](./classification.md "doc of talbe classification"), 0 for no classification |
| name | String | True | | | |
| tagName | String | | | | |
| blocksJson | Text(Json) | | | | 包含伪代码的用来运行的json |
| CPlusCode | Text(Json/Array) | | NULL | True | C++ code |
| blocksXml | Text(Xml) | | | | 用来恢复方块的xml |
| initVar | Text(Json/Array) | | | | 记录算法需要的初始变量及类型 |
| problems | Text(Json/Array) | | "[]" | | the problem array of this algorithm |
| passed | TinyInt | | 0 | | Is admin Verified |
| created_at | Timestamp | | | | |
| updated_at | Timestamp | | | | |
| deleted_at | Timestamp | | NULL | True | For soft delete |
