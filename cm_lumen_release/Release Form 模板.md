##Release Form 获取、创建、更改、删除客服班表


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/cs_work     |
| Controller |    CSWorkController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数             | 对应Procedure | 对应表格                     |
| -------- | ---------------- | ----------- | ------------------------ |
| GET      | index            | 无           | cm_cs_zone_user, cm_user |
| GET      | getCSThisWeek    | 无           | cm_cs_zone_user, cm_user |
| GET      | getOneCSThisWeek | 无           | cm_cs_zone_user, cm_user |
| GEt      | getOneCSNextWeek | 无           | cm_cs_zone_user, cm_user |
| POST     | createCSWork     | 无           | cm_cs_zone_user          |
| PUT      | updateCSWork     | 无           | cm_cs_zone_user          |
| PATCH    | deleteCSWork     | 无           | cm_cs_zone_user          |
####程序层:

| 函数    | 请求参数 | 说明                                       |
| ----- | ---- | ---------------------------------------- |
| index | 无    | 所有客服班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数            | 请求参数 | 说明                                       |
| ------------- | ---- | ---------------------------------------- |
| getCSThisWeek | 无    | 本周所有客服班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数               | 请求参数 | 说明                                       |
| ---------------- | ---- | ---------------------------------------- |
| getOneCSThisWeek | uid  | 本周个人班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数               | 请求参数 | 说明                                       |
| ---------------- | ---- | ---------------------------------------- |
| getOneCSNextWeek | uid  | 下周个人班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----

| 函数           | 请求参数                            | 说明                                       |
| ------------ | ------------------------------- | ---------------------------------------- |
| createCSWork | uid, valid_from, valid_to, zone | 使用CSInsert, 将valid_from, valid_to从 'Y-m-d H:i:s'转换为数字形式的timestamp存入数据库 |

| 参数         | 传入程序层  | 传入数据库层 | 说明                                     |
| ---------- | ------ | ------ | -------------------------------------- |
| uid        | int    | int    | 客服ID                                   |
| valid_from | string | int    | 上班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| valid_to   | string | int    | 下班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| zone       | int    | int    | 服务地区                                   |

----

| 函数           | 请求参数                                | 说明                                       |
| ------------ | ----------------------------------- | ---------------------------------------- |
| updateCSWork | id, uid, valid_from, valid_to, zone | 使用CSUpdate, 将valid_from, valid_to从 'Y-m-d H:i:s'转换为数字形式的timestamp存入数据库 |

| 参数         | 传入程序层  | 传入数据库层 | 说明                                     |
| ---------- | ------ | ------ | -------------------------------------- |
| id         | int    | int    | 班表ID                                   |
| uid        | int    | int    | 客服ID                                   |
| valid_from | string | int    | 上班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| valid_to   | string | int    | 下班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| zone       | int    | int    | 服务地区                                   |

----

| 函数           | 请求参数 | 说明                 |
| ------------ | ---- | ------------------ |
| deleteCSWork | id   | 将给予的ID对应的status改为1 |

| 参数   | 传入程序层 | 传入数据库层 | 说明   |
| ---- | ----- | ------ | ---- |
| id   | int   | int    | 班表ID |
