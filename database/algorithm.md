# Algorithm

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | Increment | True | | | |
| classification_id | Integer | | 0 | | refer to [classification.id](./classification "doc of talbe classification"), 0 for no classification |
| name | String | True | | | |
| pseudocode | Text(Json/Array) | | | | 伪代码 |
| CPlusCode | Text(Json/Array) | | NULL | True | C++ code |
| jscode | Text(Json/Array) | | | | include init data |
| explain | Text(Json/Array) | | | | the explain to pseudocode |
| problem | Text(Json/Array) | | "[]" | | the problem array of this algorithm |
