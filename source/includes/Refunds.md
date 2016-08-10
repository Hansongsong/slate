#Refunds退款
`refund` 对象允许你可以对已经支付的 `charge` 对象发起退款请求。
###can数
参数 | 类型 | 描述
---- | ---- | ----
id | **string** | 退款对象 id ，由 Ping++ 生成，27 位长度字符串。
object | **string** | 值为 refund。
order_no | **string** | 退款的订单号，<b style="color: #f15467;">由 Ping++ 生成</b>。这个地方的红色还是用html加的
amount | **integer and > 0** | 退款金额，单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如退款金额为 1 元，此处请填 100）。
succeed | **boolean** | 退款是否成功。
status | **string** | 退款状态（目前支持三种状态: pending: 处理中; succeeded: 成功; failed: 失败）。
created | **timestamp** | 退款创建的时间，用 Unix 时间戳表示。
time_succeed | **timestamp** | 退款成功的时间，用 Unix 时间戳表示。
description | **string** | 退款详情，最多 255 个 Unicode 字符。
failure_code | **string** | 退款的错误码，[详见 Errors 错误处理机制](#api-errors)中的错误码。
failure_msg | **string** | 退款消息的描述。
metadata | **metadata hash** | [参考 Metadata 元数据](#api-metadata)。
charge | **string** | `refund` 对象的所在 `charge` 对象的 `id`。
charge_order_no | **string** | 商户订单号，这边返回的是charge对象中的order_no参数。
transaction_no| **string** | 支付渠道返回的交易流水号，部分渠道返回该字段为空。
``` curl
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` php
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` java
com.pingplusplus.model.Refund JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` ruby
#&lt;Pingpp::Refund id=re_y1u944PmfnrTHyvnL0nD0iD1&gt; JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` nodejs
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` python
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` go
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` csharp
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```


##创建 Refund 对象
通过发起一次退款请求创建一个新的 `refund` 对象，只能对已经发生交易并且没有全额退款的 `charge` 对象发起退款。当进行全额退款之前，可以进行多次退款，直至全额退款。当一次退款成功后，会发送 Webhooks 通知。

###canshu

参数 | 描述
---- | ----
id | **required** `charge` 对象的 id。
amount | **optional** 退款的金额, 单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如退款金额为 1 元，此处请填 100）。必须小于等于可退款金额，默认为全额退款，应用内快捷支付目前只支持全额退款。
metadata | **optional** [参考 Metadata 元数据](#api-metadata)。
description | **required** 退款详情，最多 255 个 Unicode 字符。

###fanhui参数

如果发起退款成功，返回一个退款 `refund` 对象。如果发生错误，则会返回错误码和错误详情，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  POST https://api.pingxx.com/v1/charges/{CHARGE_ID}/refunds
```
``` php
  $ch = \Pingpp\Charge::retrieve({CHARGE_ID});
  $re = $ch->refunds->create();
```
``` java
  Map params = new HashMap();
  Charge ch = Charge.retrieve({CHARGE_ID});
  Refund re = ch.getRefunds().create(params);
```
``` ruby
  ch = Pingpp::Charge.retrieve({CHARGE_ID})
  re = ch.refunds.create
```
``` nodejs
  pingpp.charges.createRefund(
    {CHARGE_ID},
    {},
    function(err, refund) {
    }
  );
```
``` python
  ch = pingpp.Charge.retrieve('CHARGE_ID')
  re = ch.refunds.create(description='desc', amount=1)
```
``` go
  re, err := refund.New("CHARGE_ID", &RefundParams)
```
``` csharp
  create(String chId, Dictionary&lt;String, Object&gt; params)
```
``` curl
  curl https://api.pingxx.com/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC: \
  -d description="Refund Description" \
  -X POST
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  $ch = \Pingpp\Charge::retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4');
  $re = $ch->refunds->create(array('description'=&gt;'Refund Description'));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Map&lt;String, Object&gt; params = new HashMap&lt;String, Object&gt;();
  params.put("description", "Refund Description");
  Charge ch = Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4");
  Refund re = ch.getRefunds().create(params);
```
``` ruby
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  ch = Pingpp::Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4")
  re = ch.refunds.create(:description =&gt; "Refund Description")
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC')
  pingpp.charges.createRefund(
    "ch_L8qn10mLmr1GS8e5OODmHaL4",
    { description: "Refund Description" },
    function(err, refund) {
      // 异步调用
    }
  );
```
``` python
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  ch = pingpp.Charge.retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4')
  re = ch.refunds.create(description='Refund Description', amount=1)
```
``` go
  pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  refundParams := &amp;pingpp.RefundParams{
    Description: "Refund Description",
  }
  //charge_id 为待退款的 Charge 的 ID
  refund, err := refund.New("ch_L8qn10mLmr1GS8e5OODmHaL4", refundParams)
```
``` csharp
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    params.Add("amount", 100);
    params.Add("description", "Your Description");
    try {
        Refund re = Refund.create(chId, params);
        Console.WriteLine(re);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` php
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` java
com.pingplusplus.model.Refund JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` ruby
#&lt;Pingpp::Refund id=re_y1u944PmfnrTHyvnL0nD0iD1&gt; JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` nodejs
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` python
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` go
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` csharp
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```

##查询 Refund 对象

可以通过 `charge` 对象的查询接口查询某一个 `charge` 对象的退款列表，也可以通过 `refund` 对象的 `id` 查询一个已创建的 `refund` 对象。可以在 Webhooks 通知之前，通过查询接口确认退款状态。

###can数
参数 | 描述
---- | ----
id | **required** 查询的 `refund` 对象 `id`。
charge | **required** 退款的 `charge` 对象 `id`。

###fan回

返回一个已存在的 `refund` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  GET https://api.pingxx.com/v1/charges/{CHARGE_ID}/refunds/{REFUND_ID}
```
``` php
  $charge = \Pingpp\Charge::retrieve({CHARGE_ID});
  $refund = $charge->refunds->retrieve({REFUND_ID});
```
``` java
  Charge ch = Charge.retrieve({CHARGE_ID});
  Refund re = ch.refunds->retrieve({REFUND_ID});
```
``` ruby
  ch = Pingpp::Charge.retrieve({CHARGE_ID})
  re = ch.refunds.retrieve({REFUND_ID})
```
``` nodejs
  pingpp.charges.retrieveRefund(
    {CHARGE_ID},
    {REFUND_ID},
    function(err, refund) {
    }
  );
```
``` python
  ch = pingpp.Charge.retrieve('CHARGE_ID')
  re = ch.refunds.retrieve('REFUND_ID')
```
``` go
  re, err := refund.Get("CHARGE_ID", "REFUND_ID")
```
``` csharp
  retrieve(String chId, String reId)
```
``` curl
  curl https://api.pingxx.com/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds/re_TmbvDKHiXLCSG0mnj9jnDyjA \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  $ch = \Pingpp\Charge::retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4');
  $refund = $ch->refunds->retrieve('re_TmbvDKHiXLCSG0mnj9jnDyjA');
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Charge ch = Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4");
  Refund re = ch.getRefunds().retrieve("re_TmbvDKHiXLCSG0mnj9jnDyjA");
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  ch = Pingpp::Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4")
  re = ch.refunds.retrieve("re_TmbvDKHiXLCSG0mnj9jnDyjA")
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.retrieveRefund(
    "ch_L8qn10mLmr1GS8e5OODmHaL4",
    "re_TmbvDKHiXLCSG0mnj9jnDyjA",
    function(err, refund) {
      // 异步调用
    }
  );
```
``` python
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  import pingpp
  ch = pingpp.Charge.retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4')
  re = ch.refunds.retrieve('re_TmbvDKHiXLCSG0mnj9jnDyjA')
```
``` go
  pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  refund, err := refund.Get("ch_L8qn10mLmr1GS8e5OODmHaL4", "re_TmbvDKHiXLCSG0mnj9jnDyjA")
```
``` csharp
    try {
        Refund re = Refund.create(chId, reId);
        Console.WriteLine(re);
    } catch (AuthenticationException e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` php
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` java
com.pingplusplus.model.Refund JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` ruby
#&lt;Pingpp::Refund id=re_y1u944PmfnrTHyvnL0nD0iD1&gt; JSON: {
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` nodejs
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` python
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` go
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```
``` csharp
{
  "id": "re_y1u944PmfnrTHyvnL0nD0iD1",
  "object": "refund",
  "order_no": "y1u944PmfnrTHyvnL0nD0iD1",
  "amount": 9,
  "created": 1409634160,
  "succeed": true,
  "status": "succeeded",
  "time_succeed": 1409634192,
  "description": "Refund Description",
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "charge_order_no": "123456789",
  "transaction_no": "2004450349201512090096425284"
}
```


##查询 Refund 对象列表

``` curl
  GET https://api.pingxx.com/v1/charges/{CHARGE_ID}/refunds
```
``` php
  \Pingpp\Charge::retrieve({CHARGE_ID})->refunds->all();
```
``` java
  Charge.retrieve({CHARGE_ID}).getRefunds().all();
```
``` ruby
  Pingpp::Charge.retrieve({CHARGE_ID}).refunds.all
```
``` nodejs
  pingpp.charges.listRefunds({CHARGE_ID});
```
``` python

  ch = pingpp.Charge.retrieve('CHARGE_ID')
  res = ch.refunds.all(limit=3)
```
``` go
  refund.List("CHARGE_ID", &amp;pingpp.RefundListParams)
```
``` csharp
  list(String chId, Dictionary&lt;String, Object&gt; params)
```
``` curl
  curl https://api.pingxx.com/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds?limit=3 \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  \Pingpp\Charge::retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4')
  ->refunds->all(array('limit'=&gt;3));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Charge ch = Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4");
  Map&lt;String, Object&gt; refundParams = new HashMap&lt;String, Object&gt;();
  refundParams.put("limit", 3);
  ChargeRefundCollection refunds = ch.getRefunds().all(refundParams);
```
``` ruby
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4").refunds.all({:limit =&gt; 3})
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.listRefunds(
    "ch_L8qn10mLmr1GS8e5OODmHaL4",
    { limit: 3 },
    function(err, refunds) {
      // 异步调用
    }
  );
```
``` python
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  ch = pingpp.Charge.retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4')
  res = ch.refunds.all(limit=3)
```
``` go
  pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  params := &amp;pingpp.RefundListParams{}
  params.Filters.AddFilter("limit", "", "3")
  //设置是不是只需要之前设置的 limit 这一个查询参数
  params.Single = true
  i := refund.List("ch_L8qn10mLmr1GS8e5OODmHaL4", params)
  for i.Next() {
    c := i.Refund()
  }
```
``` csharp
    Dictionary&lt;String, Object&gt; refundParams = new Dictionary&lt;String, Object&gt;();
    refundParams.Add("limit", 3);
    try {
        RefundList res = Refund.list(chId, refundParams);
        Console.WriteLine(res);
    } catch (AuthenticationException e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
``` php
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
``` java
#&lt;com.pingplusplus.model.RefundCollection id=#&gt; JSON: {
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    com.pingplusplus.model.Refund JSON: {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    }
    #&lt;com.pingplusplus.model.Refund[...] ...&gt;,
    #&lt;com.pingplusplus.model.Refund[...] ...&gt;
  ]
}
```
``` ruby
#&lt;Pingpp::ListObject>JSON: {
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    #&lt;Pingpp::Refund[...] ...&gt;,
    #&lt;Pingpp::Refund[...] ...&gt;
  ]
}
```
``` nodejs
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
``` python
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
``` go
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
``` csharp
{
  "object": "list",
  "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
  "has_more": false,
  "data": [
    {
      "id": "re_TmbvDKHiXLCSG0mnj9jnDyjA",
      "object": "refund",
      "order_no": "TmbvDKHiXLCSG0mnj9jnDyjA",
      "amount": 100,
      "created": 1410835214,
      "succeed": true,
      "status": "succeeded",
      "time_succeed": 1410835652,
      "description": "Refund Description",
      "failure_code": null,
      "failure_msg": null,
      "metadata": {},
      "charge": "ch_L8qn10mLmr1GS8e5OODmHaL4",
      "charge_order_no": "123456789",
      "transaction_no": "2004450349201512090096425284"
    },
    {...},
    {...}
  ]
}
```
返回之前创建 `charge` 对象的一个 `refund` 对象列表。列表是按创建时间进行排序，总是将最新的 `refund` 对象显示在最前。

###canshu 
参数 | 描述
---- | ----
id | **required** 指定退款所在 `charge` 对象的 `id`。
limit | **optional** 限制每页可以返回多少对象，范围为 1-20 项，默认是 10 项。
starting_after | **optional** 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。
ending_before | **optional** 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。

###fanhui
根据请求参数返回一个 `refund` 对象列表，如果列表为空，则返回的 `data` 为空数组。遇到错误时返回相应错误信息，[详见 Errors 错误处理机制](#api-errors)。

