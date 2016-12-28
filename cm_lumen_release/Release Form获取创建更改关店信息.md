##Release Form 获取、创建、更新关店信息


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |    api/v1/rr_close     |
| Controller |   RRCloseController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数          | 对应Procedure    | 对应表格                    |
| -------- | ------------- | -------------- | ----------------------- |
| GET      | index         | get_rrclose    | cm_rr_close, cm_rr_base |
| POST     | createRRClose | insert_rrclose | cm_rr_close             |
| PUT      | updateRRClose | update_rrclose | cm_rr_close             |

####程序层:
| 函数    | 请求参数 | 说明            |
| ----- | ---- | ------------- |
| index | 无    | 使用get_rrclose |

----

| 函数            | 请求参数                      | 说明               |
| ------------- | ------------------------- | ---------------- |
| createRRClose | rid, start_time, end_time | 使用insert_rrclose |

| 参数         | 传入程序层  | 传入数据库层 | 说明   |
| ---------- | ------ | ------ | ---- |
| rid        | int    | int    | 餐厅ID |
| start_time | string | string | 关店时间 |
| end_time   | string | string | 重开时间 |

----

| 函数            | 请求参数                          | 说明               |
| ------------- | ----------------------------- | ---------------- |
| updateRRClose | rid, start_time, end_time, id | 使用update_rrclose |

| 参数         | 传入程序层  | 传入数据库层 | 说明   |
| ---------- | ------ | ------ | ---- |
| rid        | int    | int    | 餐厅ID |
| start_time | string | string | 关店时间 |
| end_time   | string | string | 重开时间 |
| id         | int    | int    | 关店ID |

####数据库层:

| Procedure | get_rrclose                         |
| --------- | ----------------------------------- |
| 请求参数      | 无                                   |
| 返回值       | id, rid, name, start_time, end_time |
| 影响表格      | cm_rr_close, cm_rr_base             |
| 备注        | 无                                   |

----

| Procedure | insert_rrclose                      |
| --------- | ----------------------------------- |
| 请求参数      | iv_rid, iv_start_time, iv_end_time  |
| 返回值       | 无                                   |
| 影响表格      | cm_rr_close                         |
| 备注        | status, updated_at, updated_by 默认为0 |

----

| Procedure | update_rrclose                           |
| --------- | ---------------------------------------- |
| 请求参数      | iv_close_id, iv_rid, iv_start_time, iv_end_time) |
| 返回值       | 无                                        |
| 影响表格      | cm_rr_close                              |
| 备注        | 无                                        |





