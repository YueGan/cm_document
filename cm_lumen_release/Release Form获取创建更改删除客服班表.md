##Release Form 获取、创建、更改、删除客服班表


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/cs_work     |
| Controller |    CSWorkController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数         | 对应Procedure | 对应表格                     |
| -------- | ------------ | ----------- | ------------------------ |
| GET      | index        | CSWork      | cm_cs_zone_user, cm_user |
| POST     | createCSWork | CSInsert    | cm_cs_zone_user          |
| PUT      | updateCSWork | CSUpdate    | cm_cs_zone_user          |
| PATCH    | deleteCSWork | 无           | cm_cs_zone_user          |
####程序层:

| 函数    | 请求参数 | 说明                                       |
| ----- | ---- | ---------------------------------------- |
| index | 无    | 使用CSWork, 将valid_from, valid_to从数字形式的timestamp 转换为'Y-m-d H:i:s'返回前端 |

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

####数据库层:

| Procedure | CSWork                                   |
| --------- | ---------------------------------------- |
| 请求参数      | 无                                        |
| 返回值       | id, uid, username, valid_from, valid_to, zone |
| 影响表格      | cm_cs_zone_user, cm_user                 |
| 备注        | 无                                        |

----
| Procedure | CSInsert                                 |
| --------- | ---------------------------------------- |
| 请求参数      | iv_uid, iv_valid_from, iv_valid_to, iv_zone |
| 返回值       | 无                                        |
| 影响表格      | cm_cs_zone_user                          |
| 备注        | status, updated_at, updated_by 默认为0      |

----
| Procedure | CSUpdate                                 |
| --------- | ---------------------------------------- |
| 请求参数      | iv_id, iv_uid, iv_valid_from, iv_valid_to, iv_zone |
| 返回值       | 无                                        |
| 影响表格      | cm_cs_zone_user                          |
| 备注        | 无                                        |

