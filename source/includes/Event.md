#Event事件
`Event` 对象属性定义如下。

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














