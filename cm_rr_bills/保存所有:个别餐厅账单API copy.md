##获取所有/个别餐厅账单API


|  Tables  |         说明         | 默认值  |
| :------: | :----------------: | :--: |
|   URL    | /api/v1/save_bills |      |
| HTTP请求方式 |        POST        |      |
|  是否需要登录  |         否          |      |
|  授权访问限制  |         暂无         |      |
|  授权范围()  |         暂无         |      |
|   支持格式   |        JSON        |      |


表头参数:

| Tables      | 类型及其范围 | 说明        | 默认值  |
| ----------- | ------ | --------- | ---- |
| Authortoken | string | token验证信息 |      |


请求参数:


| Tables     | 类型及其范围            | 说明   | 默认值                        |
| ---------- | ----------------- | ---- | -------------------------- |
| all_bills  | number            | 客服ID | 1为所有账单，0为选择账单              |
| start_date | string            | 上班时间 | 格式 YYYY-MM-DD              |
| end_date   | string            | 下班时间 | 格式 YYYY-MM-DD              |
| rids       | array(number,...) | 工作区域 | 当all_bills为0，选择此array里的rid |



返回字段说明:

| Tables     | 类型及其范围 | 说明     | 默认值        |
| ---------- | ------ | ------ | ---------- |
| ev_result  | number | 请求是否成功 | 0为成功, 1为错误 |
| ev_message | string | 报错信息   | 空          |
| ea_data    | array  | 客服班表信息 |            |


| ev_data    | 类型及其范围 | 说明     |
| ---------- | ------ | ------ |
| rid        | number | 餐厅ID   |
| pretax     | number | 税前     |
| name       | string | 餐厅名字   |
| rate       | number | 费率     |
| income     | number | 收入     |
| bill       | number | 账单     |
| start_date | string | 账单开始时间 |
| end_date   | string | 账单结束时间 |


返回结果(默认JSON):
```
{
ev_result :#0: successful 1:fail
ev_message:
ea_data:[
  {
   rid: number,
   pretax: number,
   name: string,
   rate: number,
   income: number,
   bill: number,
   start_date: string,
   end_date: string
  }
 ]
}
```