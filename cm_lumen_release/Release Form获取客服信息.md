##Release Form 获取客服名单


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/cs_role     |
| Controller |    CSRoleController    |
|    验证方式    | app/Authentication.php |

####速查表:
| HTTP请求方式 | 对应函数  | 对应Procedure | 对应表格                                     |
| -------- | ----- | ----------- | ---------------------------------------- |
| GET      | index | CSInfo      | cm_user_group_link, cm_user, cm_user_role |

####程序层:

| 函数    | 请求参数 | 说明                                       |
| ----- | ---- | ---------------------------------------- |
| index | 无    | 将CSInfo()的返回值进行处理，返回bp等于Monitor的uid, username |

####数据库层:

| Procedure | CSInfo                                   |
| --------- | ---------------------------------------- |
| 请求参数      | 无                                        |
| 返回值       | uid, username, start_at, bp, role        |
| 使用表格      | cm_user_group_link, cm_user, cm_user_role |
| 备注        | 无                                        |
