#身份证银行卡信息认证接口ssss

根据姓名、身份证、银行卡、手机号码，检测信息是否匹配。

###canshu
参数 | 描述 | 类型
---- | ---- | ----
type | 身份证信息或者银行卡信息串，参考[type取值范围]()。| **string**
app | 应用 ID,可登录管理平台查看。| **string**
data | 验证数据，[data包含参数]()。| **map**
result_code | 返回码 详情参照API文档附录的[认证接口result_code说明](https://www.pingxx.com/document/api#api-appendix-3)。|**int**
message | 描述信息(接口调用失败时为错误描述，成功时为SUCCESS)。| **string**
paid | 是否已扣款，扣款为true，未扣款为false。| **boolean**

###type取值范围

参数 | 描述 
---- | ----
id_card | 身份证信息串
bank_card | 银行卡信息串

###data包含参数

参数 | 描述 | 类型
---- | ---- | ----
id_name | 身份证姓名(1~16位) | **string**
id_number | 身份证号码(15位或18位) | **string**
card_number | 银行卡号(12～19位) 仅在type参数为bankcard的时候必需要传此参数 | **string**
phone_number | 手机号(11位) 仅在type参数为bankcard的时候可以选择是否传此参数，暂不支持178开头的手机号 | **string**

##请求认证接口1

请求该接口，验证姓名、身份证、银行卡、手机号码的信息；每次请求可选择验证身份证信息或者银行卡信息是否匹配。<b style="color: #f15467;">注意：此接口强制要求签名（Pingplusplus-Signature），需在管理平台上配置商户公钥，但无须开启。</b>

###参数1
参数 | 描述 | 类型
---- | ---- | ----
type | 身份证信息或者银行卡信息串，参考[type取值范围]()。| **string**
app | 应用 ID,可登录管理平台查看。| **string**
data | 验证数据，[data包含参数]()。| **map**

###type取值范围
参数 | 描述 
---- | ----
id_card | 身份证信息串
bank_card | 银行卡信息串

###data包含参数
参数 | 描述 | 是否必须
---- | ---- | ----
id_name | 身份证姓名(1~16位) | **required**
id_number | 身份证号码(15位或18位) | **required**
card_number | 银行卡号(12～19位) 仅在type参数为bankcard的时候必需要传此参数 | **required**
phone_number | 手机号(11位) 仅在type参数为bankcard的时候可以选择是否传此参数，暂不支持178开头的手机号 | **optional**

###fanhui

请求成功，返回result_code字段为返回码，详情参照API文档附录的认证接口result_code说明；message中是错误描述信息，仅在成功时返回success;paid表示本次调用接口认证是否产生费用，paid为true则需要付费，false不产生费用。






