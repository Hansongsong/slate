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

###查询 Red envelope 对象
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


























