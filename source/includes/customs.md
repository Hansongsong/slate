#报关接口ssss

目前只针对支付成功的订单进行报关，报关金额为订单金额；
目前暂不支持拆单报关，报关渠道是支持的，
customs_code<br />是海关编号字段说明。

###canshu

参数 | 描述 | 类型
---- | ---- | ----
id | 报关对象id | **string**
app | 应用 ID,可登录管理平台查看 | **string**
channel | 支付使用的第三方支付渠道，[取值范围](link) | **string**
trade_no | 商户报关订单号,8~20位 | **string**
customs_code | 海关编号，详情参照API文档附录的[<a href="https://www.pingxx.com/document/api#api-appendix-4" style="text-decoration:underline;color:red">海关编号说明</a>]() | **string**
amount | 报关金额,(1～1000000000) | **int**
charge_id | charge对象id | **string**
extra | 自定义参数 | **metadata hash**
object | 值为 customs | **string**
created | 创建时间，用 Unix 时间戳表示 | **timestamp**
succeed | 处理时间，用 Unix 时间戳表示 |**timestamp**
status | 成功状态,成功返回true，失败返回false | **boolean**
failure_code | 错误码，详见 Errors 错误处理机制中的错误码描述。| **string**
failure_msg | 错误信息描述 | **string**
transaction_no | 渠道报关流水号 | **string**

###channel取值范围
参数 | 描述 
---- | ---- 
alipay | 支付宝手机支付
wx | 微信支付

##请求报关接口sss

请求报关接口，目前只针对支付成功的订单charge id进行报关请求，报关金额为订单金额，目前渠道限于alipay和wx，目前不支持拆单报关(报关渠道是支持的)，customs_code(海关编号)字段说明。<b style="color: #f15467;">注意：此接口强制要求签名（Pingplusplus-Signature），需在管理平台上配置商户公钥，但无须开启。</b>

###canshu

参数 | 描述 | 是否必须
---- | ---- | ----
app | 应用 ID,可登录管理平台查看 | **required**
channel | 支付使用的第三方支付渠道，[取值范围](link) | **required**
trade_no | 商户报关订单号,8~20位 | **required**
customs_code | 海关编号，详情参照API文档附录的[<a href="https://www.pingxx.com/document/api#api-appendix-4" style="text-decoration:underline;color:red">海关编号说明</a>]() | **required**
amount | 报关金额,(1～1000000000) | **int**
charge_id | charge对象id | **required**
extra | 自定义参数 | **optional**

###channel取值范围

参数 | 描述 
---- | ---- 
alipay | 支付宝手机支付
wx | 微信支付

###返回sss

返回一个`customs`报关对象，其中status为报关结果，为true时成功，false失败；`transaction_no`为渠道报关流水号。

##查询报关接口sss
通过`customs`对象的id查询一个已创建的`customs`对象。通过查询接口确认报关的状态。

###canshu

参数 | 描述 | 是否必须
---- | ---- | ----
id | 报关对象id | required

###fanhui
返回一个已存在的 `customs` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。











