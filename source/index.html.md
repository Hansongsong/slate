---
title: API Songsong Test

language_tabs:
  - Curl
  - PHP
  - Java
  - Ruby
  - Node.js
  - Python
  - Go
  - C#
toc_footers:
  - <a href='https://www.pingxx.com/document/api#ppp-ovw'>旧版API文档</a>

includes:
  - charge
  - Refunds
  - Red_envelope
  - Event
  - Transfer
  - Token 
  - Customer
  - Card
  - identification
  - customs
  - appendix
  - update

search: true
---

# API文档介绍

Ping++ API 采用 REST 风格设计。所有接口请求地址都是可预期的以及面向资源的。使用规范的 HTTP 响应代码来表示请求结果的正确或错误信息。使用 HTTP 内置的特性，如 HTTP Authentication 和 HTTP 请求方法让接口易于理解。所有的 API 请求都会以规范友好的 JSON 对象格式返回（包括错误信息）。

> To test, I try to use this code:

```Curl
Curl:Ping++ API 主站地址：https://api.pingxx.com
```

```PHP
PHP:Ping++ API 主站地址：https://api.pingxx.com
```

```Java
Java:Ping++ API 主站地址：https://api.pingxx.com
```

```Ruby
Ruby:Ping++ API 主站地址：https://api.pingxx.com
```

```Node.js
Node.js:Ping++ API 主站地址：https://api.pingxx.com
```

```Python
Python:Ping++ API 主站地址：https://api.pingxx.com
```

```Go
Go:Ping++ API 主站地址：https://api.pingxx.com
```

```C#
C#:Ping++ API 主站地址：https://api.pingxx.com
```
# Authentication认证
在调用 API 时，必须提供 API Key 作为每个请求的身份验证。你可以在管理平台内管理你的 API Key。API Key 是商户在 Ping++ 系统中的身份标识，请安全存储，确保其不要被泄露。如需更新，也可以在管理平台的「基本信息」内进行更新。

API Key 分为 live 和 test 两种模式。分别对应真实交易环境和模拟测试交易环境并且可以实时切换。测试模式下的 API Key 会模拟交易等请求，但是不会产生任何真实交易行为和费用，便于调试和接入。 所有的 API 请求必须通过 HTTPS 发送，使用 HTTP 会被 Ping++ 服务器拒绝。

```Curl
curl https://api.pingxx.com/v1/charges \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
                            
  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
Ping++ API 使用 HTTP Basic Auth 进行认证。 将 API Key 作为 basic auth 的用户名。不需要填写密码。
```
```PHP
 \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
                            
  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
调用 \Pingpp\Pingpp::setApiKey() 方法使用你的 API Key。 Ping++ SDK PHP 库文件会自动的将这个 key 应用到每个请求中。

```Java
 Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";
                    
  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
  将 Pingpp.apiKey 设置为你的 API Key。 Ping++ SDK Java 库文件会自动的将这个 key 应用到每个请求中
```
```Ruby
Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"

  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
  使用 Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC" 设置你的 API Key Ping++ SDK ruby 库文件会自动的将这个 key 应用到每个请求中
```
```Node.js
 var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
  调用 var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'); 使用你的 API Key。
```
```Python
pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'

  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
  使用 pingpp.api_key = 'API-KEY'; 设置你的 API Key。
```
```Go
Pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"

  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。
  Pingpp.Key = “sk_test_ibbTe5jLGCi5rzfH4OqPW9KC” 设置你的 API Key。
```
```C#
Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"

  注意将示例中的 sk_test_ibbTe5jLGCi5rzfH4OqPW9KC 替换成你自己的 API Key。

```
# Errors 错误处理机制

Ping++ 使用 HTTP 状态码来表明一个 API 请求的成功或失败。通常，返回值 2xx 表明 API 请求成功。返回值 4xx 表明 API 请求时被提供了错误的信息（比如参数缺失，参数错误，支付渠道错误等）。返回值 5xx 表明 API 请求时，Ping++ 服务器发生了错误。

###Attribute
参数 |描述 
---- |---- 
type | 错误类型，可以是 `invalid_request_error`、`api_error`、`channel_error` 或 `card_error`。
message | 返回具体的错误描述。
code | 错误码，由第三方支付渠道返回的错误代码，optional。
param | 当发生参数错误时返回具体的参数名，如 id，optional。

###HTTP 返回状态码

状态码 | 解释 
---- | ---- 
200 | OK，一切正常。
400 | Bad Request，一般由缺失参数，参数格式不正确等引起。
401 | Unauthorized，没有提供正确的 API Key。
402 | Request Failed，参数格式正确但是请求失败，一般由业务错误引起。
403 | Forbidden，调用接口超过 Ping++ 套餐的并发限制，请[升级套餐](https://dashboard.pingxx.com/pricing)或限流。
404 | Not Found，请求的资源不存在。
500、502、503、504 | Server errors，Ping++ 服务器错误。


###错误类型

报错类型 | 错误解释 
---- | ---- 
invalid_request_error | 请求误，传入了不正确的地址，参数或值。
api_error | Ping++ 服务器出现的异常错误。
channel_error | 第三方支付渠道出现的错误导致请求出现错误。通常你需要对这些可能出现的情况进行处理或者联系我们。
card_error | 用户进行绑卡或使用卡片进行支付时出现的卡片错误,通常你需要对这些可能出现的情况进行处理。

### 错误码
错误码 | 错误解释 
---- | ---- 
charge_closed | 支付订单已结束，不能进行后续操作。
charge_unexpected_status | 支付返回意外的状态码。
refund_wait_operation | 退款需要等待用户进一步操作。
refund_refused | 退款失败，被支付渠道拒绝。
refund_retry | 退款失败，需要重新发起退款。
refund_manual_intervention | 退款失败，需要通过线下或转账进行退款。
refund_unexpected_status | 退款返回意外的状态码。
channel_connection_error | 支付渠道通讯异常。
channel_request_error | 请求支付渠道接口失败。
channel_parse_error | 支付渠道返回意外的数据格式发生的解析错误。
channel_sign_error | 支付渠道返回的数据没有通过签名验证。
card_declined | 卡片信息有误或未开通银联无卡支付业务。
under_verification | 卡片信息核实中，请稍后再试。
already_bound | 卡片已经进行过了绑定。
binding_unauthorized | 卡片绑定操作未授权。
cardholder_not_match | 绑定的卡片与原持卡人不匹配。
send_sms_failed | 支付短信发送失败。

# Pagination 分页机制

```Curl
  curl https://api.pingxx.com/v1/charges \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
```PHP
\Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  \Pingpp\Charge::all();
```
```Java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";
  Charge.all(new HashMap<String, Object>());
```
```Ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.all()
```
```Node.js
var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.list({}, function(err, charges) {
    // YOUR CODE
  });
```
```Python
 ch = pingpp.Charge.all()
```
```Go
charge.List(params)
```
```C#
 Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";
  Charge.list(new Dictionary<String, Object>());
```

所有的 Ping++ 资源都可以被 list API 方法支持，例如分页 charges 和 refunds。这些 list API 方法拥有相同的数据结构。Ping++ 是基于 cursor 的分页机制，使用参数 starting_after 来决定列表从何处开始。

### canshu 所有标题不支持纯中文

参数 | 类型 |描述 | 是否必须
---- | ---- |---- | ----
limit | int | 限制有多少对象可以被返回，限制范围是从 1-100 项，默认是 10 项。 |**optional**
starting_after | obj| 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。|**optional**
ending_before | obj | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。|**optional** 
created | timestamp | 对象的创建时间，用 Unix 时间戳表示。具体参考[created参数说明](created参数说明)|**optional**

### created参数说明
参数 | 描述 | 是否必须
---- |---- | ----
created[gt] | 大于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[gte] | 大于或等于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[lt] | 小于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**
created[lte] | 小于或等于 charge 对象的创建时间，用 Unix 时间戳表示。|**optional**

###返回canshu //目前这种字段不支持纯中文的标题
参数 | 类型 | 描述 
---- | ---- | ----
object | string | 值为list
date |array | 包含一个由请求参数分页后的返回元素实体。
has_more | boolean | 表明获取列表之后是否还有更多的元素实体。如果值为 false，表明当前页是最后一页。
url | string | 表明获取该列表所使用的 URL。



# Expanding 展开对象
``` curl

  curl https://api.pingxx.com/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD?expand%5b%5d=app \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  \Pingpp\Charge::retrieve(array('id' =&gt; 'ch_Hm5uTSifDOuTy9iLeLPSurrD', 'expand' =&gt; array('app')));
```
``` java

  Ping++ SDK Java 库暂不支持这个特性。
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.retrieve(:id =&gt; "ch_Hm5uTSifDOuTy9iLeLPSurrD", :expand =&gt; ['app'])
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.retrieve(
    "ch_Hm5uTSifDOuTy9iLeLPSurrD",
    { expand: ["app"] },
    function(err, charge) {
      // 异步调用
    }
  );
```
``` python
  import pingpp
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  ch = pingpp.Charge.retrieve(id='ch_Hm5uTSifDOuTy9iLeLPSurrD', expand='app')
```
``` go
  Ping++ SDK Go 库暂不支持这个特性。
```
``` csharp
  Ping++ SDK C# 库暂不支持这个特性。
```

Ping++ 内有很多对象包含了其他对象的 id，如果这些对象带有 `expand` 展开特性，你可以在请求参数后加入额外的展开参数来展开子对象。例如在创建 `charge` 对象时，使用 expand[] = app 参数来展开返回 `charge` 对象内部的 `app` 对象。

# Metadate 元数据
一些 Ping++ 对象支持加入用户指定的 `metadata` 参数。你可以使用键值对的形式来构建自己的 `metadata`，例如 metadata[color] = red，你可以在每一个 `charge` 对象中加入订单的一些详情，如颜色、型号等属性，在查询时获得更多信息。每一个对象的 `metadata` 最多可以拥有 10 个键值对，数据总长度在 1000 个 Unicode 字符以内。

``` curl
  curl https://api.pingxx.com/v1/charges \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC: \
  -d order_no=123456789 \
  -d amount=100 \
  -d app[id]=app_1Gqj58ynP0mHeX1q \
  -d channel=upacp \
  -d currency=cny \
  -d client_ip=127.0.0.1 \
  -d subject="Your Subject" \
  -d body="Your Body" \
  -d metadata[color]=red
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  \Pingpp\Charge::create(array(
    'order_no'  =&gt; '123456789',
    'amount'    =&gt; '100',
    'app'       =&gt; array('id' =&gt; 'app_1Gqj58ynP0mHeX1q'),
    'channel'   =&gt; 'upacp',
    'currency'  =&gt; 'cny',
    'client_ip' =&gt; '127.0.0.1',
    'subject'   =&gt; 'Your Subject',
    'body'      =&gt; 'Your Body'
    'metadata'  =&gt; array('color'=&gt;'red')
  ));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Map&lt;String, Object&gt; chargeParams = new HashMap&lt;String, Object&gt;();
  chargeParams.put("order_no",  "123456789");
  chargeParams.put("amount", 100);
  Map&lt;String, String&gt; app = new HashMap&lt;String, String&gt;();
  app.put("id", "app_1Gqj58ynP0mHeX1q");
  chargeParams.put("app", app);
  chargeParams.put("channel",  "upacp");
  chargeParams.put("currency", "cny");
  chargeParams.put("client_ip",  "127.0.0.1");
  chargeParams.put("subject",  "Your Subject");
  chargeParams.put("body",  "Your Body");
  Map&lt;String, String&gt; initialMetadata = new HashMap&lt;String, String&gt;();
  initialMetadata.put("color", "red");
  chargeParams.put("metadata", initialMetadata);

  Charge.create(chargeParams);
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.create(
    :subject  =&gt; "Your Subject",
    :body     =&gt; "Your Body",
    :amount   =&gt; 100,
    :order_no =&gt; "123456789",
    :channel  =&gt; "upacp",
    :currency =&gt; "cny",
    :client_ip=&gt; '127.0.0.1',
    :app =&gt; {'id' =&gt; "app_1Gqj58ynP0mHeX1q"},
    :metadata =&gt; {'color' =&gt; "red"}
  )
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.create({
    subject: "Your Subject",
    body: "Your Body",
    amount: 100,
    order_no: "123456789",
    channel: "upacp",
    currency: "cny",
    client_ip: "127.0.0.1",
    app: {id: "app_1Gqj58ynP0mHeX1q"},
    metadata: {'color': 'red'}
  }, function(err, charge) {
    // 异步调用
  });
```
``` python
ch = pingpp.Charge.create(
  order_no='1234567890',
  amount=100,
  app=dict(id='app_1Gqj58ynP0mHeX1q'),
  channel='upacp',
  currency='cny',
  client_ip='127.0.0.1',
  subject='Your Subject',
  body='Your Body',
  metadata=dict(color='red')
)
```
``` go
    metadata := make(map[string]interface{})
    metadata["color"] = "red"
    params := &amp;pingpp.ChargeParams{
        Order_no:  "1234567890",
        App:       pingpp.App{Id: "APP-ID"},
        Amount:    100,
        Channel:   "upacp",
        Currency:  "cny",
        Client_ip: "127.0.0.1",
        Subject:   "Your Subject",
        Body:      "Your Body",
        Metadata:  metadata,
    }
    //返回的第一个参数是 charge 对象，你需要将其转换成 json 给客户端，或者客户端接收后转换。
    ch, err := charge.New(params)
```
``` csharp

    Dictionary&lt;String, Object&gt; app = new Dictionary&lt;String, Object&gt;();
    app.Add("id", app_1Gqj58ynP0mHeX1q);
    Dictionary&lt;String,Object&gt; extra = new Dictionary&lt;String,Object&gt;();
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    params.Add("amount", 100);
    params.Add("currency", "cny");
    params.Add("subject", "Your Subject");
    params.Add("body", "Your Body");
    params.Add("order_no", "123456789");
    params.Add("channel", "upacp");
    params.Add("client_ip", "127.0.0.1");
    params.Add("app", app);
    params.Add("extra", extra);
    try {
        //发起交易请求
        Charge ch = Charge.create(params);
        Console.WriteLine(ch);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```



