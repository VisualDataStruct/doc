# VisualDataStruct-Doc

This is the doc of visual-ds's api and database.

`API`

- [Auth](./api/auth/index.md "list of auth api")

     - [`POST` /login](./api/auth/login.md "doc of login api")

     - [`PUT` /auth/security/{id}](./api/auth/security.md "doc of change password api")

     - [`POST` /auth/forget](./api/auth/forget.md "doc of forget password api")

     - [`POST` /auth/reset](./api/auth/reset.md "doc of reset password api")

- [User](./api/user/index.md "list of user api")

     - [`POST` /user/add](./api/user/add.md "doc of add user api")

     - [`GET` /user](./api/user/userList.md "doc of user list api")

     - [`GET` /user/{id}](./api/user/userDetail.md "doc of user detail api")

     - [`PUT` /user/{id}](./api/user/profile.md "doc of change user api")

- [Classification](./api/classification/index.md "list of classification api")

     - [`GET` /classification](./api/classification/classificationList.md "doc of get classification list api")

     - [`POST` /classification](./api/classification/add.md "doc of add classification api")

     - [`PUT` /classification/{id}](./api/classification/change.md "doc of change classification api")

`Database`

- [user](./database/user.md "doc of table user")

- [classification](./database/classification.md "doc of table classification")

- [algorithm](./database/algorithm.md "doc of table algorithm")

- [verify](./database/verify.md "doc of table verify") 