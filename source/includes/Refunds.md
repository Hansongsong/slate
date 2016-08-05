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

##查询 Refund 对象
可以通过 `charge` 对象的查询接口查询某一个 `charge` 对象的退款列表，也可以通过 `refund` 对象的 `id` 查询一个已创建的 `refund` 对象。可以在 Webhooks 通知之前，通过查询接口确认退款状态。

###can数
参数 | 描述
---- | ----
id | **required** 查询的 `refund` 对象 `id`。
charge | **required** 退款的 `charge` 对象 `id`。

###fan回
返回一个已存在的 `refund` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

##查询 Refund 对象列表

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




















