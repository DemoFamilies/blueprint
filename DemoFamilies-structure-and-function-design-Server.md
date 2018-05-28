# DemoFamilies结构和功能设计-Server

## Api
### 统一格式标准
> 普通格式

``` json
{
    "code":200,
    "msg":"ok",
    "data": {}
}
```

> 统一分页格式

``` json
{
    "code":200,
    "msg":"ok",
    "data":[

    ],
    "page":{
        "item_count":1,
        "page_size":10,
        "page_count":1,
        "page_index":1,
        "offset":0,
        "limit":10,
        "has_next":false,
        "has_previous":false
    }
}
```

1. code 请求状态码

|code|意义|
|-|-|
|`200`|请求成功，其他状态则全为失败（可只判断200，除了一些需要特殊单独处理的错误）|
|`201`|注册信息错误|
|`202`|登录信息错误|
|`203`|登录失效（全局判断）|

2. msg 错误或正确返回结果的提示信息，字符类型

3. data 展示数据等

|type|name|
|-|-|
|`{}`|对象结构|
|`[]`|数组结构|

4. page 有分页功能

|key|value|
|-|-|
|`item_count`|数据总条数|
|`page_size`|一页多少条数据|
|`page_count`|总页数有多少|
|`page_index`|当前页数的下标（从1开始）|
|`offset`|当前数据偏移数量|
|`limit`|当页查询出的数量|
|`has_next`|是否有下一页|
|`has_previous`|是否有上一页|


## SQL
