##调出单独文章信息API参数

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
|id|number|文章ID||

返回字段说明:

| Tables | 类型及其范围 | 说明 |  默认值|
| ------------- |-------------|-----|-----|
|id |number|文章ID||
|cid|number|专栏ID||
|author_id|number|作者ID||
|title|string|标题||
|summary|string|内容梗概||
|icon_url|string|文章icon地址||
|content_url|string|文章地址|
|created_at|number|创建时间||
|created_by|number|创建渠道||
|status|number|作者状态|0存在,1被删除|

返回结果(默认JSON):
```
  {
    "id": number,
    "author_id": number,
    "cid": number,
    "title": string,
    "summary": string,
    "icon_url":string,
    "content_url": string,
    "created_at": number,
    "created_by": number,
    "status": number
   }
```
