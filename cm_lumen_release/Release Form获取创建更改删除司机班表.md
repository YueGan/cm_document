##Release Form 获取、创建、更改、删除客服班表


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/dr_work     |
| Controller |    DRWorkController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数             | 对应Procedure | 对应表格                                     |
| -------- | ---------------- | ----------- | ---------------------------------------- |
| GET      | index            | 无           | cm_driver_zone_schedule, cm_driver_base, cm_driver_zone_base |
| GET      | getDRThisWeek    | 无           | cm_driver_zone_schedule, cm_driver_base, cm_driver_zone_base |
| GET      | getOneDRThisWeek | 无           | cm_driver_zone_schedule, cm_driver_base, cm_driver_zone_base |
| GEt      | getOneCSNextWeek | 无           | cm_driver_zone_schedule, cm_driver_base, cm_driver_zone_base |
| POST     | createDRWork     | 无           | cm_driver_zone_schedule                  |
| PUT      | updateCSWork     | 无           | cm_driver_zone_schedule                  |
| PATCH    | deleteCSWork     | 无           | cm_driver_zone_schedule                  |
####程序层:

| 函数    | 请求参数 | 说明                                       |
| ----- | ---- | ---------------------------------------- |
| index | 无    | 所有司机班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数            | 请求参数 | 说明                                       |
| ------------- | ---- | ---------------------------------------- |
| getDRThisWeek | 无    | 本周所有司机班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数               | 请求参数 | 说明                                       |
| ---------------- | ---- | ---------------------------------------- |
| getOneDRThisWeek | uid  | 本周司机个人班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----
| 函数               | 请求参数 | 说明                                       |
| ---------------- | ---- | ---------------------------------------- |
| getOneDRNextWeek | uid  | 下周司机个人班表。将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

----

| 函数           | 请求参数                                  | 说明                                       |
| ------------ | ------------------------------------- | ---------------------------------------- |
| createDRWork | driver_id, valid_from, valid_to, zone | 将valid_from, valid_to从 'Y-m-d H:i:s'转换为数字形式的timestamp存入数据库 |

| 参数         | 传入程序层  | 传入数据库层 | 说明                                     |
| ---------- | ------ | ------ | -------------------------------------- |
| driver_id  | int    | int    | 司机ID                                   |
| valid_from | string | int    | 上班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| valid_to   | string | int    | 下班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| zone       | int    | int    | 服务地区                                   |

----

| 函数           | 请求参数                                     | 说明                                       |
| ------------ | ---------------------------------------- | ---------------------------------------- |
| updateDRWork | id, driver_id, valid_from, valid_to, zone | 将valid_from, valid_to从 'Y-m-d H:i:s'转换为数字形式的timestamp存入数据库 |

| 参数         | 传入程序层  | 传入数据库层 | 说明                                     |
| ---------- | ------ | ------ | -------------------------------------- |
| id         | int    | int    | 班表ID                                   |
| driver_id  | int    | int    | 司机ID                                   |
| valid_from | string | int    | 上班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| valid_to   | string | int    | 下班时间, 从 'Y-m-d H:i:s'转换为数字形式的timestamp |
| zone       | int    | int    | 服务地区                                   |

----

| 函数           | 请求参数 | 说明                 |
| ------------ | ---- | ------------------ |
| deleteDRWork | id   | 将给予的ID对应的status改为1 |

| 参数   | 传入程序层 | 传入数据库层 | 说明   |
| ---- | ----- | ------ | ---- |
| id   | int   | int    | 班表ID |
