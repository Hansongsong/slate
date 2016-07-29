---
title: API Songsong Test

language_tabs:
  - Curl
  - Php
  - Java
  - Ruby
  - Node.js
  - Python
  - Go
  - C#

toc_footers:
  - <a href='#'>测 试 页 面</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors
  - Test
search: true
---

# API文档介绍

Ping++ API 采用 REST 风格设计。所有接口请求地址都是可预期的以及面向资源的。使用规范的 HTTP 响应代码来表示请求结果的正确或错误信息。使用 HTTP 内置的特性，如 HTTP Authentication 和 HTTP 请求方法让接口易于理解。所有的 API 请求都会以规范友好的 JSON 对象格式返回（包括错误信息）。

> To test, I try to use this code:

```Curl
Curl:Ping++ API 主站地址：https://api.pingxx.com
```
```Php
Php:Ping++ API 主站地址：https://api.pingxx.com
```
```Java
Java:Ping++ API 主站地址：https://api.pingxx.com
```
```Ruby
Ruby:Ping++ API 主站地址：https://api.pingxx.com
```
# Pagination 分页机制

所有的 Ping++ 资源都可以被 list API 方法支持，例如分页 charges 和 refunds。这些 list API 方法拥有相同的数据结构。Ping++ 是基于 cursor 的分页机制，使用参数 starting_after 来决定列表从何处开始。

###参数
参数 | 类型 |描述 | 是否必须
---- | ---- |---- | ----
limit | int | 限制有多少对象可以被返回，限制范围是从 1-100 项，默认是 10 项。 |**optional**
starting_after | obj| 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。|**optional**
ending_before | obj | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。|**optional** 
created | timestamp | 对象的创建时间，用 Unix 时间戳表示。具体参考[created参数说明](链接)|**optional**
###created参数说明
参数 | 描述 | 是否必须
---- |---- | ----
created[gt] | 大于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[gte] | 大于或等于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[lt] | 小于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[lte] | 小于或等于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**

###返回
参数 | 类型 |描述 
---- | ---- |----
object | string|值为list

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```Curl
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```Php
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```Java
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```Ruby
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request他

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

# Chagres支付


```Curl
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```
### www参数（三级标题 貌似不支持纯中文）

所有和支付相关的要素信息都存储在 charge 这个对象中，你可以通过发起支付请求来创建一个新的 charge 对象，也可以随时查询一个或者多个支付对象的状态。每个 charge 对象都拥有一个标识 id，该 id 在系统内唯一。

表格 有待优化的说

Parameter | Type |  description | 是否必须
--------- | ---- |  ---------------- | --------
id | string | 支付对象 id ，由 Ping++ 生成，27 位长度字符串。| √




