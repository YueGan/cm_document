##Release Form 获取、创建、更新关店信息


|   Tables   |           说明           |
| :--------: | :--------------------: |
|   api接口    |     api/v1/rr_info     |
| Controller |   RRCloseController    |
|    验证方式    | app/Authentication.php |

####速查表:

| HTTP请求方式 | 对应函数           | 对应Procedure | 对应表格                 |
| -------- | -------------- | ----------- | -------------------- |
| GET      | getRRInfoClose | 无           | cm_rr_close + RRInfo |


####程序层:
| 函数             | 请求参数 | 说明            |
| -------------- | ---- | ------------- |
| getRRInfoClose | 无    | 所有店铺信息与本周关店记录 |







