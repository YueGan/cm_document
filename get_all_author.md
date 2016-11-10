##调出所有作者信息API参数

| Tables |  说明 |  默认值|
| :-------------:| :-----:|:-----:|
| URL | 待编辑　||
| HTTP请求方式 | GET |  |
| 是否需要登录 | 否 |  |
| 授权访问限制 | 暂无 |  |
| 授权范围() | 暂无 | |
| 支持格式 | JSON | |


表头参数:

| Tables | 类型及其范围 | 说明 |  默认值|
| -------------|-------------| -----|-----|
| Authortoken | string | token验证信息 ||

请求参数:

| Tables | 类型及其范围 | 说明 |  默认值|
| ------------- |-------------| -----|-----|
|author_id|number|作者ID||

返回字段说明:

| Tables | 类型及其范围 | 说明 |  默认值|
| ------------- |-------------|-----|-----|
|  authors_index|    array    |   array of authors   ||



| author| 类型及其范围 | 说明 |  默认值|
| ------------- |-------------|-----|-----|
|author_id|number|作者ID||
| team | string| 待编辑 ||
| bio_name | string | 作者名字 ||
| bio_pic | string | 作者照片地址 ||
| bio_desc | string | 作者介绍 ||
|content_desc | string | 待编辑||
|status|number|作者状态|0存在,1被删除|
返回结果(默认JSON):

```
[
    {
      "author_id": number,
      "team": string,
      "bio_name": string,
      "bio_pic": string,
      "bio_desc": string,
      "content_desc": string,
      "status": number
    },
    {
      "author_id": number,
      "team": string,
      "bio_name": string,
      "bio_pic": string,
      "bio_desc": string,
      "content_desc": string,
      "status": number
    },
    ...
]
```

