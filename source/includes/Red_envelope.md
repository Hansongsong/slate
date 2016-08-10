#Red envelope 红包
所有和红包支付相关的要素信息都存储在 `red_envelope` 对象之中，你可以通过发起红包请求创建新的 `red_envelope` 对象，也可以随时查看红包对象的状态。每个 `red_envelope` 对象都拥有一个标识 `id`，该 `id` 在系统内唯一。

###canshu
参数 | 类型 | 描述
---- | ---- | ----
id | **string** | 红包对象 id ，由 Ping++ 生成，28 位长度字符串。
object | **string** | 值为 red_envelope。
created | **timestamp** | 支付红包的时间，用 Unix 时间戳表示。
received | **timestamp** | 红包的接收时间，用 Unix 时间戳表示。
livemode | **boolean** | 支付是否处于 live 模式。
status | **string** | 红包状态。目前支持 5 种状态（sending: 发放中; sent: 已发放待领取; failed: 发放失败; received: 已领取; refund: 已退款）。
app | **string** | 红包使用的 app 对象的 id。expandable 可展开。
channel | **string** | 红包使用的第三方支付渠道。目前支持 wx(新渠道)、 wx_pub。
order_no | **string** | 红包使用的商户订单号。wx(新渠道)、wx_pub 规定为 1 ~ 28 位一天内不能重复的数字。
transaction_no | **string** | 第三方支付渠道侧的交易流水号。
amount | **integer and > 0** | 总金额，单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>。wx_pub 限制在 100 ~ 20000 之间，即 1 ~ 200 元。
currency | **currency** | 三位 ISO 货币代码，目前仅支持人民币 cny。
recipient | **string** | 接收者 id， 为用户在 wx(新渠道)、wx_pub 为用户的 open id。
subject | **string** | 红包主题名称，最多 32 个字节。
body | **string** | 红包祝福语，最多 128 个字节。
description | **string** | 备注信息，最多 255 个字节。
extra | **object** | 支付渠道相关的附加参数，参考[extra参数说明]()。


###extra参数说明
参数 | 类型 | 描述
---- | ---- | ----
send_name | **string** | 商户名称，最多 32 个字节。
``` curl
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` php
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` java
com.pingplusplus.model.RedEnvelope JSON: {
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` ruby
#&lt;Pingpp::RedEnvelope id=red_KCabLO58W5G0rX90iT0az5a9&gt; JSON: {
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` nodejs
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` python
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` go
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` csharp
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```


##创建 Red envelope 对象
发起一次红包请求需要创建一个新的 `red_envelope` 对象。如果支付失败，请检查错误信息，一般是由于账户余额不足引起的。使用测试模式的 API Key，则不会发生真实交易。同步返回交易结果，不会发送 Webhooks 通知。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
app[id] | 红包使用的 `app` 对象的 `id`。| **required**
channel | 红包使用的第三方支付渠道。目前支持 wx(新渠道)、 wx_pub。| **required** 
order_no |  红包使用的商户订单号。wx(新渠道)、wx_pub 规定为 1 ~ 28 位一天内不能重复的数字。|**required** 
amount | 总金额，单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>。wx_pub 限制在 100 ~ 20000 之间，即 1 ~ 200 元。| **required** 
currency | 三位 ISO 货币代码，目前仅支持人民币 cny。| **required** 
recipient | 接收者 id， 为用户在 wx(新渠道)、wx_pub 为用户的 open id。| **required** 
subject | 红包主题名称，最多 32 个字节。| **required** 
body | 红包祝福语，最多 128 个字节。| **required** 
description | 备注信息，最多 255 个字节。|  **required** 
extra | 支付渠道相关的附加参数，参考[extra参数说明]()。| **required** 

###extra参数说明
参数 | 描述 | 是否必须
---- | ---- | ----
send_name | 商户名称，最多 32 个字节。| **required**

###fanhui
同步返回红包支付结果。如果发生错误，则会返回错误码和错误详情，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  POST https://api.pingxx.com/v1/red_envelopes
```
``` php
  \Pingpp\RedEnvelope::create();
```
``` java
  RedEnvelope.create();
```
``` ruby
  Pingpp::RedEnvelope.create()
```
``` nodejs
  pingpp.redEnvelopes.create();
```
``` python
  pingpp.RedEnvelope.create();
```
``` go
  redEnvelope, err := redEnvelope.New(&RedenvelopeParams)
```
``` csharp
  create(Dictionary&lt;String, Object&gt; params)
```
``` curl
  curl https://api.pingxx.com/v1/red_envelopes \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC: \
  -d order_no=123456789 \
  -d app[id]=app_1Gqj58ynP0mHeX1q \
  -d channel=wx_pub \
  -d amount=100 \
  -d currency=cny \
  -d subject="Your Subject" \
  -d body="Your Body" \
  -d extra[send_name]="Send Name" \
  -d reciprent=Openid \
  -d description="Your Description"
```
``` php
\Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

\Pingpp\RedEnvelope::create(
    array(
        'subject'     =&gt; 'Your Subject',
        'body'        =&gt; 'Your Body',
        'amount'      =&gt; 100,
        'order_no'    =&gt; '123456789',
        'currency'    =&gt; 'cny',
        'extra'       =&gt; array(
            'send_name' =&gt; 'Send Name'
        ),
        'recipient'   =&gt; 'Openid',
        'channel'     =&gt; 'wx_pub',
        'app'         =&gt; array('id' =&gt; 'app_1Gqj58ynP0mHeX1q'),
        'description' =&gt; 'Your Description'
    )
);
```
``` java
Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

Map&lt;String, Object&gt; redenvelope = new HashMap&lt;String, Object&gt;();
redenvelope.put("amount", 100);
redenvelope.put("currency", "cny");
redenvelope.put("subject",  "Your Subject");
redenvelope.put("body",  "Your Body");
redenvelope.put("order_no",  "123456789");
redenvelope.put("channel",  "wx_pub");
redenvelope.put("recipient", "Openid");
redenvelope.put("description", "Your Description");
Map&lt;String, String&gt; app = new HashMap&lt;String, String&gt;();
app.put("id", "app_1Gqj58ynP0mHeX1q");
redenvelope.put("app", app);
Map&lt;String, String&gt; extra = new HashMap&lt;String, String&gt;();
extra.put("send_name", "Send Name");
redenvelope.put("extra", extra);
RedEnvelope red = RedEnvelope.create(redenvelope);
System.out.println(red);
```
``` ruby
require "pingpp"
require "digest/md5"

Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"

red = Pingpp::RedEnvelope.create(
  :order_no    =&gt; "123456789",
  :app         =&gt; { :id =&gt; "app_1Gqj58ynP0mHeX1q" },
  :channel     =&gt; "wx_pub",
  :amount      =&gt; 100,
  :currency    =&gt; "cny",
  :subject     =&gt; "Your Subject",
  :body        =&gt; "Your Body",
  :extra       =&gt; {
    :send_name =&gt; "Send Name"
  },
  :recipient   =&gt; "Openid",
  :description =&gt; "Your Description"
)
```
``` nodejs
var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

pingpp.redEnvelopes.create({
  order_no:    "123456789",
  app:         { id: "app_1Gqj58ynP0mHeX1q" },
  channel:     "wx_pub",
  amount:      100,
  currency:    "cny",
  subject:     "Your Subject",
  body:        "Your Body",
  extra: {
    send_name: "Send Name"
  },
  recipient:   "Openid",
  description: "Your Description"
}, function(err, redEnvelope) {
  // YOUR CODE
});
```
``` python
pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'

redenvelope = pingpp.RedEnvelope.create(
    order_no='123456789',
    channel='wx_pub',
    amount=100,
    subject='Your Subject',
    body='Your Body',
    currency='cny',
    app=dict(id='app_1Gqj58ynP0mHeX1q'),
    extra=dict(send_name='Send Name'),
    recipient='Openid',
    description='Your Description'
)
```
``` go
  extra := make(map[string]interface{})
  extra["send_name"] = "Send Name"

  redenvelopeParams := &amp;pingpp.RedEnvelopeParams{
    App:         &amp;pingpp.App{Id: "app_1Gqj58ynP0mHeX1q"},
    Channel:     "wx_pub",
    Order_no:    "123456789",
    Amount:      100,
    Currency:    "cny",
    Recipient:   "Openid",//指定用户的 open_id
    Subject:     "Your Subject",
    Body:        "Your Body",
    Description: "Your Description",
    Extra:       extra,
  }
  redEnvelope, err := redEnvelope.New(redenvelopeParams)
```
``` csharp
    Dictionary&lt;String, String&gt; app = new Dictionary&lt;String, String&gt;();
    app.Add("id", "app_1Gqj58ynP0mHeX1q");
    Dictionary&lt;String, String&gt; extra = new Dictionary&lt;String, String&gt;();
    extra.Add("Nick Name");
    extra.Add("send_name", "Send Name");
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    params.Add("amount", 100);
    params.Add("currency", "cny");
    params.Add("subject",  "Your Subject");
    params.Add("body",  "Your Body");
    params.Add("order_no",  "123456789");
    params.Add("channel",  "wx_pub");
    params.Add("recipient", "Your Openid");
    params.Add("description", "Your Description");
    params.Add("app", app);
    params.Add("extra", extra);
    try {
        RedEnvelope red = RedEnvelope.create(params);
        Console.WriteLine(red);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` php
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` java
com.pingplusplus.model.RedEnvelope JSON: {
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` ruby
#&lt;Pingpp::RedEnvelope id=red_KCabLO58W5G0rX90iT0az5a9&gt; JSON: {
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` nodejs
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` python
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` go
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```
``` csharp
{
    "id": "red_KCabLO58W5G0rX90iT0az5a9",
    "object": "red_envelope",
    "created": 1428499439,
    "received": null,
    "refunded": null,
    "livemode": true,
    "status": "sending",
    "app": "app_1Gqj58ynP0mHeX1q",
    "channel": "wx_pub",
    "order_no": "123456789",
    "transaction_no": null,
    "amount": 100,
    "amount_settle": 100,
    "currency": "cny",
    "recipient": "Openid",
    "subject": "Your Subject",
    "body": "Your Body",
    "description": "Your Description",
    "failure_msg":null,
    "extra": {
        "send_name": "Send Name"
    }
}
```


##查询 Red envelope 对象
通过 `red_envelope` 对象的 id 查询一个已创建的 `red_envelope` 对象。
###canshu
参数 | 描述
---- | ----
id | **required** 红包 id。

###fanhui
返回一个已存在的 `red_envelope` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

##查询 Red envelope 对象列表
返回之前创建 `red_envelope` 对象的一个列表。列表是按创建时间进行排序，总是将最新的 `red_envelope` 对象显示在最前。

###canshu
参数 | 描述 | 类型
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。|**optional** 
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。|  **optional**
created | 对象的创建时间，用 Unix 时间戳表示，参考[created参数说明](链接)。| **optional** 
app[id] | 支付使用的 `app` 对象的 `id`。| **optional** 
channel | 支付使用的第三方支付渠道，目前支持 wx(新渠道)、 wx_pub。| **optional** 
status | 红包状态。目前支持 5 种状态（sending: 发放中; sent: 已发放待领取; failed: 发放失败; received: 已领取; refund: 已退款）。| **string**

##created参数说明
参数 | 描述 | 是否必须
---- | ---- |----
created[gt] | 大于 `red_envelope` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[gte] | 大于或等于 `red_envelope` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lt] | 小于 `red_envelope` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lte] | 小于或等于 `red_envelope` 对象的创建时间，用 Unix 时间戳表示。| **optional**

###fanhui
根据请求参数返回一个 `red_envelope` 对象列表，如果列表为空，则返回的 `data` 为空数组。遇到错误时返回相应错误信息，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  GET https://api.pingxx.com/v1/red_envelopes/
```
``` php
  \Pingpp\RedEnvelope::all();
```
``` java
  RedEnvelope.all(Map options);
```
``` ruby
  Pingpp::RedEnvelope.all
```
``` nodejs
  pingpp.RedEnvelope.list();
```
``` python
  pingpp.RedEnvelope.all()
```
``` go
  redEnvelope.List(&RedenvelopeListParams)
```
``` csharp
  list(Dictionary&lt;String, Object&gt; params)
```
``` curl
  curl https://api.pingxx.com/v1/red_envelopes/?limit=3 \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  \Pingpp\RedEnvelope::all(array('limit' =&gt; 3));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Map&lt;String, Object&gt; redEnvelopeParams = new HashMap&lt;String, Object&gt;();
  redEnvelopeParams.put("limit", 3);

  RedEnvelope.all(redEnvelopeParams);
```
``` ruby
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::RedEnvelope.all(:limit =&gt; 3)
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.RedEnvelope.list({ limit: 3 }, function(err, RedEnvelope) {
    // 异步调用
  });
```
``` python
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  res = pingpp.RedEnvelope.all(limit=3)
```
``` go
  pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  params := &amp;pingpp.RedEnvelopeListParams{}
  params.Filters.AddFilter("limit", "", "3")
  //设置是不是只需要之前设置的 limit 这一个查询参数
  params.Single = true
  i := redEnvelope.List(params)
  for i.Next() {
    c := i.RedEnvelope()
  }
```
``` csharp
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    chargeParams.Add("limit", 3);
    try {
        RedEnvelopeList reds = RedEnvelope.list(params);
        Console.WriteLine(reds);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```
``` php
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```
``` java
#&lt;com.pingplusplus.model.RedEnvelopeCollection id=#&gt; JSON: {
  "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
    #&lt;com.pingplusplus.model.RedEnvelope[...] ...&gt;,
    #&lt;com.pingplusplus.model.RedEnvelope[...] ...&gt;
  ],
  "has_more": false
}
```
``` ruby
{
  "object": "list",
  "url": "/v1/red_envelopes",
  "has_more": false,
  "data": [
     {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
    #&lt;Pingpp::RedEnvelope[...] ...&gt;,
    #&lt;Pingpp::RedEnvelope[...] ...&gt;
  ]
}
```
``` nodejs
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```
``` python
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```
``` go
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```
``` csharp
{
    "object": "list",
    "url": "/v1/red_envelopes",
    "has_more": true,
    "data": [
        {
            "id": "red_KCabLO58W5G0rX90iT0az5a9",
            "object": "red_envelope",
            "created": 1428499439,
            "received": null,
            "refunded": null,
            "livemode": true,
            "status": "sending",
            "app": "app_1Gqj58ynP0mHeX1q",
            "channel": "wx_pub",
            "order_no": "123456789",
            "transaction_no": null,
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "recipient": "Openid",
            "subject": "Your Subject",
            "body": "Your Body",
            "description": "Your Description",
            "failure_msg":null,
            "extra": {
                "send_name": "Send Name"
            }
        },
        {...},
        {...}
    ]
}
```

























