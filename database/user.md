# User

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | String | True | | | Use short UUId |
| username | String | True | | | |
| password | String | | | | |
| realname | String | True | | | People's true name |
| email | String | True | | | |
| github | String | | NULL | True | |
| phone | String | | NULL | True | |
| QQ | String | | NULL | True | |
| contribution | Integer | | 0 | | |
| created_at | Timestamp | | | | |
| updated_at | Timestamp | | | | |
| deleted_at | Timestamp | | NULL | True | For soft delete |
