# Classification

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | Increment | True | | | |
| name | String | True | | | |
| description | String | | NULL | True | |
| sum | Integer | | 0 | | |
| cover | String | | NULL | True | 封面图 |
| created_at | Timestamp | | | | |
| updated_at | Timestamp | | | | |
| deleted_at | Timestamp | | NULL | True | For soft delete |
