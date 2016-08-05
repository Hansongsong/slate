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
  - <a href='#'>测 试 页 面</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors
  - Test
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
# Errors 错误处理

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

/*###参数*/有问题 加了这个标题 就不行了
### canshu

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

```Curl
    这里的所有的请求示例 和 返回示例 在admin上都加好了 可以直接复制粘贴 这里不在加过来了。
```


# Test暂时留着

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

# Charges支付


```Curl
admin可以复制粘贴
```

一些 Ping++ 对象支持加入用户指定的 `metadata` 参数。你可以使用键值对的形式来构建自己的 `metadata`，例如 metadata[color] = red，你可以在每一个 `charge` 对象中加入订单的一些详情，如颜色、型号等属性，在查询时获得更多信息。每一个对象的 `metadata` 最多可以拥有 10 个键值对，数据总长度在 1000 个 Unicode 字符以内。

### 1参数
参数 | 类型 | 描述
---- | ---- | ----
id | **string** | 支付对象 id ，由 Ping++ 生成，27 位长度字符串。
object | **string** | 值为 charge。
created | **timestamp** | 支付创建的时间，用 Unix 时间戳表示。
livemode | **boolean** | 支付是否处于 live 模式。
paid | **boolean** | 是否已付款。
refunded | **boolean** | 是否存在退款信息，无论退款是否成功。
app | **string** | 支付使用的 `app` 对象的 `id`。expandable 可展开。
channel | **string** | 支付使用的第三方支付渠道，详情参考[取值范围](#channel)。
order_no | **string** | 商户订单号，适配每个渠道对此参数的要求，必须在商户系统内唯一。(alipay: 1-64 位， wx: 1-32 位，bfb: 1-20 位，upacp: 8-40 位，yeepay_wap:1-50 位，jdpay_wap:1-30 位，cnp_u:8-20 位，cnp_f:8-20 位，推荐使用 8-20 位，要求数字或字母，不允许特殊字符)。
client_ip | **ip address** | 发起支付请求终端的 ip 地址，格式为 IPV4 整型，如 127.0.0.1。
amount | **integer and > 0** | 订单总金额，单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如订单总金额为 1 元，此处请填 100）。
amount_settle | **integer** | 清算金额，单位为对应币种的最小货币单位，例如：人民币为分。
currency | **currency** | 三位 ISO 货币代码，人民币为 `cny`。
subject | **string** | 商品的标题，该参数最长为 32 个 Unicode 字符，银联全渠道（upacp/upacp_wap）限制在 32 个字节。
body | **string** | 商品的描述信息，该参数最长为 128 个 Unicode 字符，yeepay_wap 对于该参数长度限制为 100 个 Unicode 字符。
extra | **object** | 特定渠道发起交易时需要的额外参数以及部分渠道支付成功返回的额外参数，详细参考[extra参数说明]()。
time_paid | **timestamp** | 订单支付完成时间，用 Unix 时间戳表示。
time_expire | **timestamp** | 订单失效时间，用 Unix 时间戳表示。时间范围在订单创建后的 1 分钟到 15 天，默认为 1 天，创建时间以 Ping++ 服务器时间为准。 微信对该参数的有效值限制为 2 小时内；银联对该参数的有效值限制为 1 小时内。
time_settle | **timestamp** | 订单清算时间，用 Unix 时间戳表示。（仅针对个人开发者）
transaction_no | **string** | 支付渠道返回的交易流水号。
refunds | **list** | 退款详情列表，详见 refund 退款对象。
amount_refunded | **integer and > 0** | 已退款总金额，单位为对应币种的最小货币单位，例如：人民币为分。
failure_code | **string** | 订单的错误码，[详见 Errors 错误处理机制](https://www.pingxx.com/document/api#api-errors)中的错误码描述。
failure_msg | **string** | 订单的错误消息的描述。
metadata | **metadata hash** | [参考 Metadata 元数据。](https://www.pingxx.com/document/api#api-metadata)
credential | **object** | 支付凭证，用于客户端发起支付。
description | **string** | 订单附加说明，最多 255 个 Unicode 字符。

### channel 参数说明

参数 | 对应渠道 
---- | ---- 
alipay | 支付宝手机支付
alipay_wap | 支付宝手机网页支付
alipay_pc_direct | 支付宝 PC 网页支付
alipay_qr | 支付宝扫码支付
bfb | 百度钱包移动快捷支付
bfb_wap | 百度钱包手机网页支付
upacp | 银联全渠道支付（2015 年 1 月 1 日后的银联新商户使用。若有疑问，请与 Ping++ 或者相关的收单行联系）
upacp_wap | 银联全渠道手机网页支付（2015 年 1 月 1 日后的银联新商户使用。若有疑问，请与 Ping++ 或者相关的收单行联系）
upacp_pc | 银联 PC 网页支付
cp_b2b | 银联企业网银支付
wx | 微信支付
wx_pub | 微信公众号支付
wx_pub_qr | 微信公众号扫码支付
wx_wap | 微信WAP支付
yeepay_wap | 易宝手机网页支付
jdpay_wap | 京东手机网页支付
cnp_u | 应用内快捷支付（银联）
cnp_f | 应用内快捷支付（外卡）
applepay_upacp | Apple Pay
fqlpay_wap | 分期乐支付
qgbc_wap | 量化派支付
cmb_wallet | 招行一网通

<h4>extra参数说明:</h4>
1.这个是Charges支付对应的表格:
<table border="1">
    <tr>
        <th>渠道</th>
        <th>参数</th>
        <th>类型</th>
        <th>描述</th>
    </tr>
    <tr>
        <td rowspan="4" valign="middle">alipay(支付宝手机支付)</td>
        <th>extern_token</th>
        <th>optional</th>
        <th>开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串.</th>
    </tr>
    <tr>
        <th>rn_check</th>
        <th>optional</th>
        <th>是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验</th>
    </tr>
    <tr>
        <th>buyer_account</th>
        <th>返回参数</th>
        <th>支付完成将额外返回付款用户的支付宝账号</th>
    </tr>
    <tr><th colspan="3">注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。</th></tr>
</table>

2.这个是创建Charge对象对应的表格
<table border="1">
    <tr>
        <th>渠道</th>
        <th>参数</th>
        <th>描述</th>
        <th>是否必须</th>
    </tr>
    <tr>
        <td rowspan="4" valign="middle">alipay(支付宝手机支付)</td>
        <th>extern_token</th>
        <th>开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串。</th>
        <th>optional</th>
    </tr>
    <tr>
        <th>rn_check</th>
        <th>是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验</th>
        <th>optional</th>
    </tr>
    <tr>
        <th>buyer_account</th>
        <th>支付完成将额外返回付款用户的支付宝账号</th>
        <th>返回参数</th>
    </tr>
    <tr><th colspan="3">注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。</th></tr>
</table>
### extra参数说明 好像只能这么写 下面就暂时不写表格了
渠道 | 参数 | 说明 
---- | ---- | ----
alipay(支付宝手机支付) | extern_token[string] | 开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串，optional；
alipay(支付宝手机支付) | rn_check[string] | 是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验；optional；
alipay(支付宝手机支付) | buyer_account | 支付完成将额外返回付款用户的支付宝账号。
alipay_wap (支付宝手机网页支付)。
参数 success_url[string] 为支付成功的回调地址，required；
参数 cancel_url[string] 为支付取消的回调地址，optional；
参数 new_version[boolean] 2016 年 6 月 16 日之前登录 Ping++ 管理平台填写支付宝手机网站的渠道参数的旧接口商户，需要更新接口时设置此参数值为true，6月16号后接入的新接口商户不需要设置该参数，optional；
支付完成将额外返回付款用户的支付宝账号 buyer_account。
alipay_pc_direct:
(支付宝 PC 网页支付)。
参数 success_url[string] 为支付成功的回调地址，required；
参数 enable_anti_phishing_key[boolean]为是否开启防钓鱼网站的验证参数（如果已申请开通防钓鱼时间戳验证，则此字段必填），optional；
参数 exter_invoke_ip[string] 为客户端 IP ，用户在创建交易时，该用户当前所使用机器的IP（如果商户申请后台开通防钓鱼IP地址检查选项，此字段必填，校验用），optional；
wx:
(微信支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
wx_pub:
(微信
公众号支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
参数 open_id[string] 为用户在商户 appid 下的唯一标识，required；
支付完成将额外返回付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
upacp_wap:
(银联全渠道 
手机网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
upacp_pc:
(银联 PC 网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
bfb_wap:
(百度钱包 
手机网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
参数 bfb_login[boolean] 为是否需要登录百度钱包来进行支付，required；
wx_pub_qr:
(微信公众号
扫码支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
参数 product_id[string] 为商品 ID，1-32 位字符串。此 id 为二维码中包含的商品 ID，商户自行维护，required；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
yeepay_wap:
(易宝
手机网页支付)。
参数 product_category[string] 为商品类别码，详见商品类型码表，required；
参数 identity_id[string] 为用户标识,商户生成的用户账号唯一标识，最长 50 位字符串，required；
参数 identity_type[int] 为用户标识类型，详见用户标识类型码表，required；
参数 terminal_type[int] 为终端类型，对应取值 0:IMEI, 1:MAC, 2:UUID, 3:other，required；
参数 terminal_id[string] 为终端 ID，required；
参数 user_ua[string] 为用户使用的移动终端的 UserAgent 信息，required；
参数 result_url[string] 为前台通知地址，required。
jdpay_wap:
(京东
手机网页支付)。
参数 success_url[string] 为支付成功页面跳转路径，required；
参数 fail_url[string] 为支付失败页面跳转路径，required；
参数 token[string] 为用户交易令牌，用于识别用户信息，支付成功后会调用 success_url 返回给商户。商户可以记录这个 token 值，当用户再次支付的时候传入该 token，用户无需再次输入银行卡信息，直接输入短信验证码进行支付。32 位字符串，optional；
cnp_u:
应用内快捷支付（银联）
参数 source[string] 为 Token 对象 id，required；
参数 sms_code[id][string] 为 SMS Code 对象 id，当为银联卡时必填，required；
参数 sms_code[code][string] 为短信验证码，当为银联卡时必填。，required；
cnp_f:
应用内快捷支付（外卡）
参数 source[string] Token 对象 id，required；
fqlpay_wap:
(分期乐支付)
参数 c_merch_id [string]子商户编号，需要提交该订单商户的所属子商户编号，required；
参数 return_url [string]前端回调地址，交易完成跳转的链接，不能带自定义参数，optional；
qgbc_wap:
(量化派支付)
参数 phone [string]手机号码，required；
参数 term [integer]分期参数，0 代表不分期，1 代表分 3 期，2 代表分 6 期，3 代表分 9 期，4 代表分 12 期，optional；
参数 return_url [string]交易完成跳转的地址，optional；
参数 activate_url [string]账户激活中状态跳转链接，optional；
参数 has_header [boolean]是否显示量化派页面顶部 header，即是否显示 H5 顶部标题栏，默认 true 显示，optional；
cmb_wallet:
(招行一网通)
参数 result_url[string] 为支付完成的前端回调地址，required；
参数 p_no[string] 为客户协议号，不超过 30 位的纯数字字符串，required；
参数 seq[string] 为协议开通请求流水号，不超过 20 位的纯数字字符串，请保证系统内唯一，required；
参数 m_uid[string] 为协议用户 ID，不超过 20 位的纯数字字符串，required；
参数 mobile[string] 为协议手机号，11 位数字，required；
注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。
wx_wap:
(微信WAP支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；

##创建 Charge 对象

发起一次支付请求时需要创建一个新的 `charge` 对象，获取一个可用的支付凭证用于客户端向第三方渠道发起支付请求。如果使用测试模式的 API Key，则不会发生真实交易。当支付成功后，Ping++ 会发送 Webhooks 通知。

###can数  channel 和 extra参数部分 和上面一样 
参数 | 描述 | 是否必须
---- | ---- | ----
order_no |  商户订单号，适配每个渠道对此参数的要求，必须在商户系统内唯一。(alipay: 1-64 位， wx: 1-32 位，bfb: 1-20 位，upacp: 8-40 位，yeepay_wap:1-50 位，jdpay_wap:1-30 位，cnp_u:8-20 位，cnp_f:8-20 位，推荐使用 8-20 位，要求数字或字母，不允许特殊字符)。 | **required**
app[id] |  支付使用的 `app` 对象的 `id`。| **required**
channel |  支付使用的第三方支付渠道，取值范围。| **required**
amount |  订单总金额, 单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如订单总金额为 1 元，此处请填 100）。| **required**
client_ip |  发起支付请求终端的 IP 地址，格式为 IPV4，如: 127.0.0.1。|**required**
currency |  三位 ISO 货币代码，目前仅支持人民币 `cny`。| **required**
subject |  商品的标题，该参数最长为 32 个 Unicode 字符，银联全渠道（upacp/upacp_wap）限制在 32 个字节。| **required**
body | **required** 商品的描述信息，该参数最长为 128 个 Unicode 字符，yeepay_wap 对于该参数长度限制为 100 个 Unicode 字符。
extra | 特定渠道发起交易时需要的额外参数以及部分渠道支付成功返回的额外参数。| **optional**
time_expire |  订单失效时间，用 Unix 时间戳表示。时间范围在订单创建后的 1 分钟到 15 天，默认为 1 天，创建时间以 Ping++ 服务器时间为准。 微信对该参数的有效值限制为 2 小时内；银联对该参数的有效值限制为 1 小时内。 | **optional**
metadata | [参考 Metadata 元数据](https://www.pingxx.com/document/api#api-metadata)。| **optional**
description | 订单附加说明，最多 255 个 Unicode 字符。| **optional**

###返回参shu 
鉴于支付渠道对 order_no 的合法性要求，为了保证支付请求的正确处理，请务必保证对于同一支付渠道下，不同支付产品间 order_no 的唯一性。例如：已在微信公众号下使用的 order_no 则无法在微信支付以及微信公众号扫码下重复使用，该规则同样适用于其他同类渠道。如果发生错误，则会返回错误码和错误详情，[详见 Errors 错误处理机制](#api-errors)。

##查询 Charge  对象//点击二级标题有的没反应 或不对应
通过`charge`对象的`id`查询一个已创建的`charge`对象。可以在后台异步通知之前，通过查询接口确认支付状态。

###canshu
参数 | 描述
---- | ----
id | **required** 查询的 `charge` 对象 `id`。

###返回s
返回一个已存在的 `charge` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。


##查询 Charge 对象列表
参数 | 描述  | 是否必须
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional** 
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = <code>obj_end </code> 去获取下一页。| **optional** 
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示，详情参考[created参数说明](链接)。| **optional**
app[id] | 支付使用的 `app` 对象的 `id`。| **required** 
channel | 支付使用的支付渠道：alipay, alipay_wap, wx, upacp<sup>*</sup>, upacp_wap<sup>*</sup>, bfb, wx_pub 对应支付宝，支付宝手机网页支付，微信，银联，银联手机网页支付，百度钱包，微信公众账号支付。<br />(*工作室用户使用 upmp、upmp_wap，公司用户使用 upacp、upacp_wap) | **optional** 
paid | 是否已付款。| **optional**
refunded | 是否存在退款信息，无论退款是否成功。| **optional**

###created参数说明
参数 | 描述 | 是否必须
---- | ---- | ----
created[gt] | 大于 charge 对象的创建时间，用 Unix 时间戳表示。| optional
created[gte]| 大于或等于 charge 对象的创建时间，用 Unix 时间戳表示。| optional
created[lt] | 小于 charge 对象的创建时间，用 Unix 时间戳表示。| optional 
created[lte]| 小于或等于 charge 对象的创建时间，用 Unix 时间戳表示。| optional

###返回内容
返回一个已存在的 `charge` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。























