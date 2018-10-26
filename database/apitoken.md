# ApiToken

| Col | Type | Unique | Default | Nullable | Comment |
| --- | --- | --- | --- | --- | --- |
| id | Increment | True | | | |
| user_id | String | | | | refer to [user.id](./user.md "doc of table user") |
| token | String | True | | | |
| expired_at | Timestamp | | | | |
| created_at | Timestamp | | | | |
| updated_at | Timestamp | | | | |
