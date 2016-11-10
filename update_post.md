##更新文章API参数

| Tables |  说明 |  默认值|
| :-------------:| :-----:|:-----:|
| URL | 待编辑　||
| HTTP请求方式 | PUT |  |
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
|author_id|number|作者ID||
|title|string|标题||
|summary|string|内容梗概||
|icon_url|string|文章icon地址||
|content_url|string|文章地址||





返回字段说明:

| Tables | 类型及其范围 | 说明 |  默认值|
| ------------- |-------------|-----|-----|
| ev_result | number |  请求是否成功|0为成功, 1为错误|
| ev_message | string | 报错信息 | 空|

返回结果(默认JSON):
```
{
    result: number,
    message: string
}
```

