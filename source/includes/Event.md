#Event事件
`Event` 对象属性定义如下。

``` curl
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` php
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` java
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` ruby
{
    "id": "evt_15lLTI2eZvKYlo2CcIuYBxl7",
    "created": 1427555016,
    "livemode": false,
    "type": "account.summary.available",
    "data": {
        "object": {
            "acct_id": "acct_0eHSiDyzv9G09ejT",
            "object": "account_daily_summary",
            "acct_display_name": "xx 公司",
            "created": 1425139260,
            "summary_from": 1425052800,
            "summary_to": 1425139199,
            "charges_amount": 1000,
            "charges_count": 100
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null,
}
```
``` nodejs
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` python
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` go
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```
``` csharp
{
    "id": "evt_la06CoQAiPojSgJKe5gt3nwq",
    "created": 1427555016,
    "livemode": false,
    "type": "summary.weekly.available",
    "data": {
        "object": {
            "app_id": "app_b94eHsO1avrDyL8S",
            "object": "app_weekly_summary",
            "app_display_name": "App Name",
            "created": 1425830460,
            "summary_from": 1425225600,
            "summary_to": 1425830399,
            "charges_amount": 2000,
            "charges_count" : 200
        }
    },
    "object": "event",
    "pending_webhooks": 0,
    "request": null
}
```


###Canshu

参数 | 描述 | 类型
---- | ---- | ----
id | 事件对象 id ，由 Ping++ 生成，28 位长度字符串。| **string** 
object | 值为 event。| **string** 
livemode | 事件是否发生在生产环境。| **boolean** 
created | 事件发生的时间。| **timestamp** 
data | 绑定在事件上的数据对象，详情参考[data参数说明](link)。| **hash** 
pending_webhooks | 推送未成功的 webhooks 数量。| **positive integer or zero** 
type | 事件类型，详见事件类型。| **string** 
request | API Request ID。值 null 表示该事件不是由 API 请求触发的。| **string** 

###data参数说明
参数 | 描述 | 类型
---- | ---- | ----
object | 值为Event| **hash**
previous_attributes | 绑定对象属性变化之前的值。只有 *.updated 事件有这个属性。| **hash** 

##事件类型1
目前支持的事件包括：

事件类型 | 作用域 | 描述
---- | ---- | ----
summary.daily.available | 单个应用 | 上一天 0 点到 23 点 59 分 59 秒的交易金额和交易量统计，在每日 02:00 点左右触发
summary.weekly.available | 单个应用 | 上周一 0 点至上周日 23 点 59 分 59 秒的交易金额和交易量统计，在每周一 02:00 点左右触发
summary.monthly.available | 单个应用 | 上月一日 0 点至上月末 23 点 59 分 59 秒的交易金额和交易量统计，在每月一日 02:00 点左右触发
charge.succeeded | 单个应用 | 支付对象，支付成功时触发
refund.succeeded | 单个应用 | 退款对象，退款成功时触发
transfer.succeeded | 单个应用 | 企业支付对象，支付成功时触发
red_envelope.sent | 单个应用 | 红包对象，红包发送成功时触发
red_envelope.received | 单个应用 | 红包对象，红包接收成功时触发

下面用具体的 json 字符串展示针对 App 对象的各交易汇总事件类型的数据格式。

当事件类型为 summary.daily.available、summary.weekly.available、summary.monthly.available 的时候， data 中的 object 为 App 对象。

App 日/周/月统计对象主要字段定义如下：

参数 | 描述
---- | ----
app_id | 应用 ID。
object | 对象类型。
app_display_name | 应用名称。
created | 创建时间（timestamp）。
summary_from | 统计起始时间（timestamp）。
summary_to | 统计终止时间（timestamp）。
charges_amount | 交易金额（单位：分）。
charges_count | 交易量（笔）。

当事件类型为 charge.succeeded、refund.succeeded、transfer.succeeded、red_envelope.sent、red_envelope.received  的时候， data 中的 object 分别为 [charge](/document/api#api-charges)、[refund](/document/api#api-refunds)、[transfer](/document/api#api-transfer) 和 [red_envelope](/document/api#api-envelope) 对象。

##查询 Event 对象
通过 `event` 对象的 id 查询一个已创建的 `event` 对象。

###canshu
参数 | 描述
---- | ----
id | **required** 事件 id。
###fanhui 
返回一个已存在的 `event` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  GET https://api.pingxx.com/v1/events/{EVENT_ID}
```
``` php
  \Pingpp\Event::retrieve('EVENT_ID');
```
``` java
  Event.retrieve({EVENT_ID});
```
``` ruby
  Pingpp::Event.retrieve({EVENT_ID})
```
``` nodejs
  pingpp.event.retrieve({EVENT_ID});
```
``` python
  pingpp.Event.retrieve('EVENT_ID')
```
``` go
  pingpp.EventClient.get(EVENT_ID)
```
``` csharp
  retrieve(String id)
```
``` curl
  curl https://api.pingxx.com/v1/events/evt_lqVSy5gbL0A68pS8YKvJzdWZ \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey("sk_test_ibbTe5jLGCi5rzfH4OqPW9KC");
  \Pingpp\Event::retrieve('evt_lqVSy5gbL0A68pS8YKvJzdWZ');
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";
  Event.retrieve("evt_lqVSy5gbL0A68pS8YKvJzdWZ");
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Event.retrieve("evt_lqVSy5gbL0A68pS8YKvJzdWZ")
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.event.retrieve(
    "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    function(err, event) {
      // YOUR CODE
    }
  );
```
``` python
  import pingpp
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  pingpp.Event.retrieve('evt_lqVSy5gbL0A68pS8YKvJzdWZ')
```
``` go
  import (pingpp "github.com/pingplusplus/pingpp-go")
  Event, err := client.get("evt_lqVSy5gbL0A68pS8YKvJzdWZ")
```
``` csharp
    try {
        Event evt = Event.retrieve("evt_lqVSy5gbL0A68pS8YKvJzdWZ");
        Console.WriteLine(evt);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` php
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` java
com.pingplusplus.model.Event JSON: {
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` ruby
#&lt;Pingpp::Event id=evt_lqVSy5gbL0A68pS8YKvJzdWZ> JSON: {
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
}
```
``` nodejs
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` python
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` go
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```
``` csharp
{
    "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
    "created": 1430915345,
    "livemode": true,
    "object": "event",
    "data": {
        "object": {
            "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
            "object": "charge",
            "created": 1430915284,
            "livemode": true,
            "paid": true,
            "refunded": false,
            "app": "app_Xz9iXLn9ebX1SOe1",
            "channel": "wx",
            "order_no": "as223af2ds",
            "client_ip": "127.0.0.1",
            "amount": 100,
            "amount_settle": 100,
            "currency": "cny",
            "subject": "Your Subject",
            "body": "Your Body",
            "extra": [],
            "time_paid": 1430915344,
            "time_expire": 1431001684,
            "time_settle": null,
            "transaction_no": "1001680021201505060112980000",
            "refunds": {
                "object": "list",
                "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                "has_more": false,
                "data": []
            },
            "amount_refunded": 0,
            "failure_code": null,
            "failure_msg": null,
            "metadata": [],
            "credential": [],
            "description": null
        }
    },
    "pending_webhooks": 0,
    "type": "charge.succeeded",
    "request": "iar_0K8m90CCeDK8PabXD00yfTq"
}
```

##查询 Event 对象列表
返回之前创建 `event` 对象的一个列表。列表是按创建时间进行排序，总是将最新的 `event` 对象显示在最前。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。| **optional**
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示,参考[created参数说明](link)。| **optional**
type | `event` 对象的类型。| **optional**

###created参数说明
参数 | 描述 | 是否必须
---- | ---- | ----
created[gt] | 大于 `event` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[gte] | 大于或等于 `event` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lt] | 小于 `event` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lte] | 小于或等于 `event` 对象的创建时间，用 Unix 时间戳表示。| **optional

###fanhui
返回一个已存在的 `event` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  GET https://api.pingxx.com/v1/events/
```
``` php
  \Pingpp\Event::all();
```
``` java
  Event.all(Map options);
```
``` ruby
  Pingpp::Event.all
```
``` nodejs
  pingpp.event.list();
```
``` python
  pingpp.Event.all()
```
``` go
  pingpp.EventClient.List()
```
``` csharp
  list(Dictionary&lt;String, Object&gt; params)
```
``` curl
  curl https://api.pingxx.com/v1/events/?limit=3 \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  \Pingpp\Event::all(array('limit' =&gt; 3));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Map&lt;String, Object&gt; eventParams = new HashMap&lt;String, Object&gt;();
  eventParams.put("limit", 3);

  Event.all(eventParams);
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Event.all(:limit =&gt; 3)
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.event.list({ limit: 3 }, function(err, events) {
    // 异步调用
  });
```
``` python
  import pingpp
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  res = pingpp.Event.all(limit=3)
```
``` go
  import (pingpp "github.com/pingplusplus/pingpp-go")
  event, err := client.list(params)
```
``` csharp
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    params.Add("limit", 3);
    try {
        EventList evts = Event.list(params);
        Console.WriteLine(evts);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```
``` php
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```
``` java
#&lt;com.pingplusplus.model.EventCollection id=#&gt; JSON: {
  "data": [
        {
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        }

    #&lt;com.pingplusplus.model.Event[...] ...&gt;,
    #&lt;com.pingplusplus.model.Event[...] ...&gt;
  ],
  "has_more": false
}
```
``` ruby
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        }

    #&lt;Pingpp::Event[...] ...&gt;,
    #&lt;Pingpp::Event[...] ...&gt;
  ]
}
```
``` nodejs
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```
``` python
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```
``` go
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```
``` csharp
{
    "object": "list",
    "url": "/v1/events",
    "has_more": true,
    "data": [
        {
            "id": "evt_lqVSy5gbL0A68pS8YKvJzdWZ",
            "created": 1430915345,
            "livemode": true,
            "object": "event",
            "data": {
                "object": {
                    "id": "ch_ebT0y9iPGCKCL0aPy9X1WLmT",
                    "object": "charge",
                    "created": 1430915284,
                    "livemode": true,
                    "paid": true,
                    "refunded": false,
                    "app": "app_Xz9iXLn9ebX1SOe1",
                    "channel": "wx",
                    "order_no": "as223af2ds",
                    "client_ip": "127.0.0.1",
                    "amount": 100,
                    "amount_settle": 100,
                    "currency": "cny",
                    "subject": "Your Subject",
                    "body": "Your Body",
                    "extra": [],
                    "time_paid": 1430915344,
                    "time_expire": 1431001684,
                    "time_settle": null,
                    "transaction_no": "1001680021201505060112980000",
                    "refunds": {
                        "object": "list",
                        "url": "/v1/charges/ch_ebT0y9iPGCKCL0aPy9X1WLmT/refunds",
                        "has_more": false,
                        "data": []
                    },
                    "amount_refunded": 0,
                    "failure_code": null,
                    "failure_msg": null,
                    "metadata": [],
                    "credential": [],
                    "description": null
                }
            },
            "pending_webhooks": 0,
            "type": "charge.succeeded",
            "request": "iar_0K8m90CCeDK8PabXD00yfTq"
        },
        {...},
        {...}
    ]
}
```














