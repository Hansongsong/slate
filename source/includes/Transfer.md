#Transfer 对象
所有与企业付款相关的要素信息都存储在 `transfer` 对象之中，你可以通过发起企业付款请求创建新的 `transfer` 对象，也可以随时查看企业付款对象的状态。每个 `transfer` 对象都拥有一个标识 `id`，该 `id` 在系统内唯一。

###canshu
参数 | 描述 | 类型
---- | ---- | ----
id | 企业付款对象 id ，由 Ping++ 生成，27 位长度字符串。| **string**
object | 值为 transfer。|**string** 
type | 付款类型 (当前仅支持 B2C 企业付款: b2c)。| **string** 
created | 创建时间，用 Unix 时间戳表示。| **timestamp** 
time_transferred | 支付完成时间, 用 Unix 时间戳表示。由第三方支付渠道返回。| **timestamp** 
livemode | 是否是 live 模式。| **boolean**
status | 付款状态。目前支持 3 种状态（pending: 处理中; paid: 付款成功; failed: 付款失败）。| **string** 
app | 付款对应的 app 对象的 id。expandable 可展开。| **string** 
channel | 付款使用的第三方支付渠道名称。目前支持 wx(新渠道)、 wx_pub。| **string** 
order_no | 付款使用的商户内部订单号。wx(新渠道)、wx_pub 规定为 1 ~ 50 位不能重复的数字字母组合。| **string** 
amount | 付款总金额。单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>。| **integer**
currency | 三位 ISO 货币代码，目前仅支持人民币 cny。| **currency**
recipient | 接收者 id， 为用户在 wx(新渠道)、wx_pub 为用户的 open id。| **string**  
description | 备注信息，最多 255 个 Unicode 字符,渠道为 chinapay 时，最多 99 个 Unicode 字符，不可以包含特殊字符。| **string**
transaction_no | 交易流水号，由于第三方渠道提供。| **string**
extra | 支付渠道相关的附加参数，参考[extra参数说明]()。| **object**

###extra参数说明  所有extra参数怎么写是个问题 若使用表格 那么这里需要改下语法 要么就要用html了 extra中不使用参数类型 只用optional 和required
参数 | 描述 | 类型
---- | ---- | ----
wx(微信新渠道) | 参数 `user_name`[string] 收款人姓名。当该参数为空，则不校验收款人姓名 | optional
wx(微信新渠道) | 参数 force_check[boolean] 是否强制校验收款人姓名。仅当 user_name 参数不为空时该参数生效 | optional 
wx_pub(微信公众号) | 参数 user_name[string] 收款人姓名。当该参数为空，则不校验收款人姓名 | optional；
wx_pub(微信公众号) | 参数 force_check[boolean] 是否强制校验收款人姓名。仅当 user_name 参数不为空时该参数生效 | optional 
unionpay 企业付款（银行卡）| 参数 card_number[string] 1~32位,收款人银行卡号或者存折号 | required
参数 user_name[string] 1~100位,收款人姓名，required
参数 open_bank[string] 1~50位,开户银行,required
参数 prov[string] 1～20位，省份,required
参数 city[string] 1～40位，城市,required
参数 term_type[string] 2位，企业付款（银行卡）业务使用场景, 07:互联网, 08:移动端,required
参数 sub_bank[string] 1～80位，开户支行名称,optional

##创建 Transfer 对象
发起一次企业付款请求以创建一个新的 `transfer` 对象。如果支付失败，请检查错误信息，一般是由于账户余额不足引起的。使用测试模式的 API Key，则不会发生真实交易。测试模式需要主动查询下 `transfer` 的状态，才会发送 Webhooks 通知。<b style="color: #f15467;">注：渠道为unionpay时，强制要求签名（Pingplusplus-Signature），需在管理平台上配置商户公钥，但无须开启;unionpay渠道的转账会延时5分钟发送，5分钟内可以调用更新Transfer接口取消该笔转账。</b>

###canshu
参数 | 描述 | 是否可选
---- | ---- | ----
app[id] | 付款使用的 `app` 对象的 `id`。| **required** 
channel | 付款使用的第三方支付渠道。目前只支持 wx(新渠道)、wx_pub。| **required**
order_no | 付款使用的商户订单号。wx(新渠道)、wx_pub 规定为 1 ~ 50 位一天内不能重复的数字。| **required**
amount | 付款金额。单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>。| **required**
type | 付款类型。 当前仅支持 B2C 企业付款。| **required**
currency | 三位 ISO 货币代码，目前仅支持人民币: cny。| **required** 
recipient | 接收者 id，为用户在 wx(新渠道)、wx_pub 为用户的 open id。| **required**
description | 付款备注信息，最多 255 个 Unicode 字符。| **required**
extra | 支付渠道相关的附加参数，参考[extra参数说明]()。| **object**

###cextra参数说明
参数 | 描述 | 类型
---- | ---- | ----
wx(微信新渠道) | 参数 `user_name`[string] 收款人姓名。当该参数为空，则不校验收款人姓名 | **optional**
wx(微信新渠道) | 参数 force_check[boolean] 是否强制校验收款人姓名。仅当 user_name 参数不为空时该参数生效 | **optional** 
wx_pub(微信公众号) | 参数 user_name[string] 收款人姓名。当该参数为空，则不校验收款人姓名 | **optional**
wx_pub(微信公众号) | 参数 force_check[boolean] 是否强制校验收款人姓名。仅当 user_name 参数不为空时该参数生效 | **optional** 
unionpay 企业付款（银行卡）| 参数 card_number[string] 1~32位,收款人银行卡号或者存折号 | **required**
参数 user_name[string] 1~100位,收款人姓名，required
参数 open_bank[string] 1~50位,开户银行,required
参数 prov[string] 1～20位，省份,required
参数 city[string] 1～40位，城市,required
参数 term_type[string] 2位，企业付款（银行卡）业务使用场景, 07:互联网, 08:移动端,required
参数 sub_bank[string] 1～80位，开户支行名称,optional

###fanhui

同步返回付款支付结果。如果发生错误，则会返回错误码和错误详情，[详见 Errors 错误处理机制](#api-errors)。

##查询 Transfer 对象
通过 `transfer` 对象的 id 查询一个已创建的 `transfer` 对象。

###canshu
参数 | 描述 | 是否可选
---- | ---- | ----
id | 付款对象 id。| **required**

###fanhui
返回一个已存在的 `transfer` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

##查询 Transfer 对象列表
返回之前创建过 `transfer` 对象的一个列表。列表是按创建时间进行排序，总是将最新的 `transfer` 对象显示在最前
###canshu
参数 | 描述 | 是否可选
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = `obj_end` 去获取下一页。| **optional**
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示，参考[created参数说明](link)。| **timestamp**
app[id] | 支付使用的 `app` 对象的 `id`。| **optional**
channel | 支付使用的第三方支付渠道，目前支持 wx(新渠道)、 wx_pub。| **optional**
status | 付款状态。目前支持 3 种状态（pending: 处理中; paid: 付款成功; failed: 付款失败)。| **optional**
type | 付款类型，目前仅支持 B2C。| **optional**

###created参数说明
参数 | 描述 | 是否可选
---- | ---- | ----
created[gt] | 大于 `transfer` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[gte] | 大于或等于 `transfer` 对象的创建时间，用时间戳表示。| **optional**
created[lt] | 小于 `transfer` 对象的创建时间，用时间戳表示。| **optional**
created[lte] | 小于或等于 `transfer` 对象的创建时间，用时间戳表示。| **optional**

###fanhui
返回一个已存在的 `transfer` 对象的列表或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

##更新 Transfer对象

更新 Transfer 对象接口只适用unionpay渠道，该渠道在 Transfer 对象请求成功后，延时5分钟发送转账，5分钟内订单处于scheduled的准备发送状态，且可调用该接口通过 Transfer 对象的 id 更新一个已创建的 Transfer 对象，即取消该笔转账。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
id | unionpay渠道的Transfer对象id。| **required**
status | 更新Transfer的状态，只支持canceled。| **required**

###fanhui
返回一个更新成功的 transfer 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。













