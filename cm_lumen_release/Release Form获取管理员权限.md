##Release Form 获取管理员权限


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/rr_role     |
| Controller |    RRRoleController    |
|    验证方式    | app/Authentication.php |
####速查表:
| HTTP请求方式 | 对应函数      | 对应Procedure | 对应表格 |
| -------- | --------- | ----------- | ---- |
| GET      | roleCheck | 无           | 无    |


程序层:

| 函数    | 请求参数 | 说明                                       |
| ----- | ---- | ---------------------------------------- |
| index | 无    | 使用app/Authentication.php验证, 返回值3为管理员, 0为非管理员 |


