##Release Form 获取、创建、更新关店信息


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |    api/v1/rr_close     |
| Controller |   RRCloseController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数          | 对应Procedure | 对应表格                    |
| -------- | ------------- | ----------- | ----------------------- |
| GET      | index         | 无           | cm_rr_close, cm_rr_base |
| GET      | getOneClose   | 无           | cm_rr_close, cm_rr_base |
| POST     | createRRClose | 无           | cm_rr_close             |
| PUT      | updateRRClose | 无           | cm_rr_close             |

####程序层:
| 函数    | 请求参数 | 说明     |
| ----- | ---- | ------ |
| index | 无    | 所有关店记录 |

----

| 函数          | 请求参数 | 说明     |
| ----------- | ---- | ------ |
| getOneClose | rid  | 单个关店记录 |

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





