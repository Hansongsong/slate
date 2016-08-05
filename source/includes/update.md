#API更新

### 2016-08-03
1. 新增 `alipay_wap` 渠道extra字段 `app_pay` 参数，用于判断是否使用支付宝客户端支付；修改 `cancel_url` 参数说明，当 `app_pay` 为true时，`cancel_url` 字段无效，接入规则参考[API文档](https://www.pingxx.com/document/api#api-charges)。
2. 修改招行一网通extra字段参数说明，`p_no`, `seq`, `m_uid`, `mobile` 这几个参数决定是否签约，传同样的参数，就不会重新签约,具体请参考[API文档](https://www.pingxx.com/document/api#api-charges)。
3. 新增 `jdpay_wap` 渠道extra字段 `order_type` 和 `is_mobile` 参数，接入规则请参考[API文档](https://www.pingxx.com/document/api#api-charges)。

### 2016-07-27

1. 身份证银行卡信息认证接口更新phone_number参数，添加说明：暂不支持178开头的手机号，请参考[API文档](https://www.pingxx.com/document/api#api-identification)。
2. 身份证银行卡信息认证接口添加php，ruby对应SDK请求示例和返回示例，接入规则请参考[API文档](https://www.pingxx.com/document/api#api-i-new)。

### 2016-07-20

1. 新增 **更新 Transfer 对象接口**：接入规则请参考[API文档](https://www.pingxx.com/document/api#api-update-transfer)；
2. 修改 Customer 对象，Card 对象请求参数：添加`sms_code[id]` 和 `sms_code[code]` 参数,修改 Customer 对象 和 Card 对象请求示例，请参考[API文档](https://www.pingxx.com/document/api#api-customer-new)。

### 2016-07-13

1. 新增支付渠道： 微信WAP支付 `wx_wap` ，接入规则请参考 [API 文档](https://www.pingxx.com/document/api#api-charges)；使用该渠道，需更新客户端 SDK ，请参考 [pingpp-js](https://github.com/PingPlusPlus/pingpp-js)；
2. 修改 **身份证银行卡信息认证接口**参数：`app_id` 改成 `app`、`idcard` 改成 `id_card`、`bankcard` 改成 `bank_card`、`user_name` 改成 `id_name`，接入规则请参考 [API 文档](https://www.pingxx.com/document/api#api-identification)；
3. 修改 **报关接口**参数：`app_id` 改成 `app`，接入规则请参考 [API 文档](https://www.pingxx.com/document/api#api-customs)。

### 2016-07-06

1. 新增 **报关接口**，接入规则请参考 [API 文档](https://www.pingxx.com/document/api#api-customs)；
2. 新增 **企业付款（银行卡）接口**，接入规则请参考 [API 文档](https://www.pingxx.com/document/api#api-transfer)。

### 2016-06-30

1. 新增支付渠道： 招行一网通 `cmb_wallet` ，接入规则请参考 [API 文档](https://www.pingxx.com/api#api-charges) ；
2. 新增 **身份证银行卡信息认证接口** ，接口规则请参考 [API 文档](https://www.pingxx.com/document/api#api-identification)。

### 2016-06-22

退款 Refund 对象中增加商户订单号 `charge_order_no` 字段，请求退款之后会在返回的 Refund 中带回付款订单的的商户订单号，详情参考 [API 文档](https://www.pingxx.com/api#api-refunds)。

### 2016-06-16

升级支付宝手机网站（alipay_wap）支付接口，针对已经接入旧接口的用户请在 3 个月内更新成新接口。旧接口的用户更新只需要三步：
- 更新客户端 [H5 SDK](https://github.com/PingPlusPlus/pingpp-js)；
- 在服务端请求中增加额外的请求字段 `new_version` ，详细步骤请参照 [alipay_wap 接口更新说明](https://help.pingxx.com/article/174737)；
- 更新 Ping++ 管理平台上的支付宝手机网站支付的渠道参数，更新成支付宝的 **合作伙伴密钥** 对应的参数，详情参考[帮助中心](https://help.pingxx.com/article/123325)；
- 更新到新接口之后，alipay_wap渠道的同步返回参数也会有相应的变更，具体内容参考 [帮助中心](https://help.pingxx.com/article/132329/)。

### 2016-05-18

红包接口和微信官方接口同步：下线 `extra` 参数中的 `nick_name`、`logo`、`share_url`、`share_content` 和 `share_img ` 字段。兼容旧接口，已接入用户可忽略该变更；未接入用户请参考 [API 文档](https://www.pingxx.com/api#api-envelope) 进行接入。

### 2016-04-27

1. API－微信类接口增加 `goods_tag` 字段；具体使用方法请参见： [API 文档](https://www.pingxx.com/api#api-c-new)；
2. API－支付宝即时到帐可选参数 `anti_phishing_key` 变更为 `enable_anti_phishing_key`，为布尔值，具体使用方法请参见： [API 文档](https://www.pingxx.com/api#api-c-new)；
3. API－修复代理商 App 创建微信企业付款( transfer )时报错信息错误的问题；
4. API－修复红包在测试模式 `transaction_no` 值为 `null` 的问题。


