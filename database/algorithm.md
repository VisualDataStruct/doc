# Algorithm

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | Increment | True | | | |
| classification_id | Integer | | 0 | | refer to [classification.id](./classification.md "doc of talbe classification"), 0 for no classification |
| name | String | True | | | |
| pseudocode | Text(Json/Array) | | | | 伪代码 |
| CPlusCode | Text(Json/Array) | | NULL | True | C++ code |
| jscode | Text(Json/Array) | | | | include init data |
| explain | Text(Json/Array) | | | | the explain to pseudocode |
| problems | Text(Json/Array) | | "[]" | | the problem array of this algorithm |
| passed | TinyInt | | 0 | | Is admin Verified |
| created_at | Timestamp | | | | |
| updated_at | Timestamp | | | | |
| deleted_at | Timestamp | | NULL | True | For soft delete |
