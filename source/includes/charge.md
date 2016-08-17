#Charges支付

``` curl
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` php
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` java
com.pingplusplus.model.Charge JSON: {
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` ruby
#&lt;Pingpp::Charge id=ch_Hm5uTSifDOuTy9iLeLPSurrD&gt; JSON: {
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` nodejs
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` python
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` go
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` csharp
{
  "id": "ch_Hm5uTSifDOuTy9iLeLPSurrD",
  "object": "charge",
  "created": 1410778843,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410782443,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_Hm5uTSifDOuTy9iLeLPSurrD/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409151900430000000",
      "mode": "01"
    }
  },
  "description": null
}
```


一些 Ping++ 对象支持加入用户指定的 `metadata` 参数。你可以使用键值对的形式来构建自己的 `metadata`，例如 metadata[color] = red，你可以在每一个 `charge` 对象中加入订单的一些详情，如颜色、型号等属性，在查询时获得更多信息。每一个对象的 `metadata` 最多可以拥有 10 个键值对，数据总长度在 1000 个 Unicode 字符以内。

### 1参数
参数 | 类型 | 描述
---- | ---- | ----
id | **string** | 支付对象 id ，由 Ping++ 生成，27 位长度字符串。
object | **string** | 值为 charge。
created | **timestamp** | 支付创建的时间，用 Unix 时间戳表示。
livemode | **boolean** | 支付是否处于 live 模式。
paid | **boolean** | 是否已付款。
refunded | **boolean** | 是否存在退款信息，无论退款是否成功。
app | **string** | 支付使用的 `app` 对象的 `id`。expandable 可展开。
channel | **string** | 支付使用的第三方支付渠道，详情参考[取值范围](#channel)。
order_no | **string** | 商户订单号，适配每个渠道对此参数的要求，必须在商户系统内唯一。(alipay: 1-64 位， wx: 1-32 位，bfb: 1-20 位，upacp: 8-40 位，yeepay_wap:1-50 位，jdpay_wap:1-30 位，cnp_u:8-20 位，cnp_f:8-20 位，推荐使用 8-20 位，要求数字或字母，不允许特殊字符)。
client_ip | **ip address** | 发起支付请求终端的 ip 地址，格式为 IPV4 整型，如 127.0.0.1。
amount | **integer and > 0** | 订单总金额，单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如订单总金额为 1 元，此处请填 100）。
amount_settle | **integer** | 清算金额，单位为对应币种的最小货币单位，例如：人民币为分。
currency | **currency** | 三位 ISO 货币代码，人民币为 `cny`。
subject | **string** | 商品的标题，该参数最长为 32 个 Unicode 字符，银联全渠道（upacp/upacp_wap）限制在 32 个字节。
body | **string** | 商品的描述信息，该参数最长为 128 个 Unicode 字符，yeepay_wap 对于该参数长度限制为 100 个 Unicode 字符。
extra | **object** | 特定渠道发起交易时需要的额外参数以及部分渠道支付成功返回的额外参数，详细参考[extra参数说明]()。
time_paid | **timestamp** | 订单支付完成时间，用 Unix 时间戳表示。
time_expire | **timestamp** | 订单失效时间，用 Unix 时间戳表示。时间范围在订单创建后的 1 分钟到 15 天，默认为 1 天，创建时间以 Ping++ 服务器时间为准。 微信对该参数的有效值限制为 2 小时内；银联对该参数的有效值限制为 1 小时内。
time_settle | **timestamp** | 订单清算时间，用 Unix 时间戳表示。（仅针对个人开发者）
transaction_no | **string** | 支付渠道返回的交易流水号。
refunds | **list** | 退款详情列表，详见 refund 退款对象。
amount_refunded | **integer and > 0** | 已退款总金额，单位为对应币种的最小货币单位，例如：人民币为分。
failure_code | **string** | 订单的错误码，[详见 Errors 错误处理机制](https://www.pingxx.com/document/api#api-errors)中的错误码描述。
failure_msg | **string** | 订单的错误消息的描述。
metadata | **metadata hash** | [参考 Metadata 元数据。](https://www.pingxx.com/document/api#api-metadata)
credential | **object** | 支付凭证，用于客户端发起支付。
description | **string** | 订单附加说明，最多 255 个 Unicode 字符。

### channel 参数说明

参数 | 对应渠道 
---- | ---- 
alipay | 支付宝手机支付
alipay_wap | 支付宝手机网页支付
alipay_pc_direct | 支付宝 PC 网页支付
alipay_qr | 支付宝扫码支付
bfb | 百度钱包移动快捷支付
bfb_wap | 百度钱包手机网页支付
upacp | 银联全渠道支付（2015 年 1 月 1 日后的银联新商户使用。若有疑问，请与 Ping++ 或者相关的收单行联系）
upacp_wap | 银联全渠道手机网页支付（2015 年 1 月 1 日后的银联新商户使用。若有疑问，请与 Ping++ 或者相关的收单行联系）
upacp_pc | 银联 PC 网页支付
cp_b2b | 银联企业网银支付
wx | 微信支付
wx_pub | 微信公众号支付
wx_pub_qr | 微信公众号扫码支付
wx_wap | 微信WAP支付
yeepay_wap | 易宝手机网页支付
jdpay_wap | 京东手机网页支付
cnp_u | 应用内快捷支付（银联）
cnp_f | 应用内快捷支付（外卡）
applepay_upacp | Apple Pay
fqlpay_wap | 分期乐支付
qgbc_wap | 量化派支付
cmb_wallet | 招行一网通

<h4>extra参数说明:</h4>
1.这个是Charges支付对应的表格:
<table border="1">
    <tr>
        <th>渠道</th>
        <th>参数</th>
        <th>是否可选</th>
        <th>说明</th>
    </tr>
    <tr>
        <td rowspan="4" valign="middle">alipay(支付宝手机支付)</td>
        <th>extern_token</th>
        <th>optional</th>
        <th>开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串.</th>
    </tr>
    <tr>
        <th>rn_check</th>
        <th>optional</th>
        <th>是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验</th>
    </tr>
    <tr>
        <th>buyer_account</th>
        <th>返回参数</th>
        <th>支付完成将额外返回付款用户的支付宝账号</th>
    </tr>
    <tr><th colspan="3">备注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。</th></tr>
</table>

2.这个是创建Charge对象对应的表格
<table border="1">
    <tr>
        <th>渠道</th>
        <th>参数</th>
        <th>描述</th>
        <th>是否必须</th>
    </tr>
    <tr>
        <td rowspan="4" valign="middle">alipay(支付宝手机支付)</td>
        <th>extern_token</th>
        <th>开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串。</th>
        <th>optional</th>
    </tr>
    <tr>
        <th>rn_check</th>
        <th>是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验</th>
        <th>optional</th>
    </tr>
    <tr>
        <th>buyer_account</th>
        <th>支付完成将额外返回付款用户的支付宝账号</th>
        <th>返回参数</th>
    </tr>
    <tr><th colspan="3">注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。</th></tr>
</table>
### extra参数说明 好像只能这么写 下面就暂时不写表格了
渠道 | 参数 | 说明 
---- | ---- | ----
alipay(支付宝手机支付) | extern_token[string] | 开放平台返回的包含账户信息的 token（授权令牌，商户在一定时间内对支付宝某些服务的访问权限）。通过授权登录后获取的 alipay_open_id，作为该参数的 value，登录授权账户即会为支付账户，32 位字符串，optional；
alipay(支付宝手机支付) | rn_check[string] | 是否发起实名校验，T 代表发起实名校验；F 代表不发起实名校验；optional；
alipay(支付宝手机支付) | buyer_account | 支付完成将额外返回付款用户的支付宝账号。
alipay_wap (支付宝手机网页支付)。
参数 success_url[string] 为支付成功的回调地址，required；
参数 cancel_url[string] 为支付取消的回调地址，optional；
参数 new_version[boolean] 2016 年 6 月 16 日之前登录 Ping++ 管理平台填写支付宝手机网站的渠道参数的旧接口商户，需要更新接口时设置此参数值为true，6月16号后接入的新接口商户不需要设置该参数，optional；
支付完成将额外返回付款用户的支付宝账号 buyer_account。
alipay_pc_direct:
(支付宝 PC 网页支付)。
参数 success_url[string] 为支付成功的回调地址，required；
参数 enable_anti_phishing_key[boolean]为是否开启防钓鱼网站的验证参数（如果已申请开通防钓鱼时间戳验证，则此字段必填），optional；
参数 exter_invoke_ip[string] 为客户端 IP ，用户在创建交易时，该用户当前所使用机器的IP（如果商户申请后台开通防钓鱼IP地址检查选项，此字段必填，校验用），optional；
wx:
(微信支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
wx_pub:
(微信
公众号支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
参数 open_id[string] 为用户在商户 appid 下的唯一标识，required；
支付完成将额外返回付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
upacp_wap:
(银联全渠道 
手机网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
upacp_pc:
(银联 PC 网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
bfb_wap:
(百度钱包 
手机网页支付)。
参数 result_url[string] 为支付完成的回调地址，required；
参数 bfb_login[boolean] 为是否需要登录百度钱包来进行支付，required；
wx_pub_qr:
(微信公众号
扫码支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
参数 product_id[string] 为商品 ID，1-32 位字符串。此 id 为二维码中包含的商品 ID，商户自行维护，required；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；
yeepay_wap:
(易宝
手机网页支付)。
参数 product_category[string] 为商品类别码，详见商品类型码表，required；
参数 identity_id[string] 为用户标识,商户生成的用户账号唯一标识，最长 50 位字符串，required；
参数 identity_type[int] 为用户标识类型，详见用户标识类型码表，required；
参数 terminal_type[int] 为终端类型，对应取值 0:IMEI, 1:MAC, 2:UUID, 3:other，required；
参数 terminal_id[string] 为终端 ID，required；
参数 user_ua[string] 为用户使用的移动终端的 UserAgent 信息，required；
参数 result_url[string] 为前台通知地址，required。
jdpay_wap:
(京东
手机网页支付)。
参数 success_url[string] 为支付成功页面跳转路径，required；
参数 fail_url[string] 为支付失败页面跳转路径，required；
参数 token[string] 为用户交易令牌，用于识别用户信息，支付成功后会调用 success_url 返回给商户。商户可以记录这个 token 值，当用户再次支付的时候传入该 token，用户无需再次输入银行卡信息，直接输入短信验证码进行支付。32 位字符串，optional；
cnp_u:
应用内快捷支付（银联）
参数 source[string] 为 Token 对象 id，required；
参数 sms_code[id][string] 为 SMS Code 对象 id，当为银联卡时必填，required；
参数 sms_code[code][string] 为短信验证码，当为银联卡时必填。，required；
cnp_f:
应用内快捷支付（外卡）
参数 source[string] Token 对象 id，required；
fqlpay_wap:
(分期乐支付)
参数 c_merch_id [string]子商户编号，需要提交该订单商户的所属子商户编号，required；
参数 return_url [string]前端回调地址，交易完成跳转的链接，不能带自定义参数，optional；
qgbc_wap:
(量化派支付)
参数 phone [string]手机号码，required；
参数 term [integer]分期参数，0 代表不分期，1 代表分 3 期，2 代表分 6 期，3 代表分 9 期，4 代表分 12 期，optional；
参数 return_url [string]交易完成跳转的地址，optional；
参数 activate_url [string]账户激活中状态跳转链接，optional；
参数 has_header [boolean]是否显示量化派页面顶部 header，即是否显示 H5 顶部标题栏，默认 true 显示，optional；
cmb_wallet:
(招行一网通)
参数 result_url[string] 为支付完成的前端回调地址，required；
参数 p_no[string] 为客户协议号，不超过 30 位的纯数字字符串，required；
参数 seq[string] 为协议开通请求流水号，不超过 20 位的纯数字字符串，请保证系统内唯一，required；
参数 m_uid[string] 为协议用户 ID，不超过 20 位的纯数字字符串，required；
参数 mobile[string] 为协议手机号，11 位数字，required；
注:p_no, seq, m_uid, mobile 这几个参数决定是否签约，传同样的参数，就不会重新签约；所以，同一个用户，最好用同一套参数，否则签约次数超限，就无法正常使用，且目前没有提供解约接口。
wx_wap:
(微信WAP支付)。
参数 limit_pay[string] 为指定支付方式，指定不能使用信用卡支付可设置为no_credit，optional；
支付完成将额外返回付款用户的 open_id 和付款银行类型 bank_type 。
参数 goods_tag[string] 为商品标记，代金券或立减优惠功能的参数，optional；

##创建 Charge 对象

发起一次支付请求时需要创建一个新的 `charge` 对象，获取一个可用的支付凭证用于客户端向第三方渠道发起支付请求。如果使用测试模式的 API Key，则不会发生真实交易。当支付成功后，Ping++ 会发送 Webhooks 通知。

###can数  channel 和 extra参数部分 和上面一样 
参数 | 描述 | 是否必须
---- | ---- | ----
order_no |  商户订单号，适配每个渠道对此参数的要求，必须在商户系统内唯一。(alipay: 1-64 位， wx: 1-32 位，bfb: 1-20 位，upacp: 8-40 位，yeepay_wap:1-50 位，jdpay_wap:1-30 位，cnp_u:8-20 位，cnp_f:8-20 位，推荐使用 8-20 位，要求数字或字母，不允许特殊字符)。 | **required**
app[id] |  支付使用的 `app` 对象的 `id`。| **required**
channel |  支付使用的第三方支付渠道，取值范围。| **required**
amount |  订单总金额, 单位为对应币种的最小货币单位，例如：<b style="color: #f15467;">人民币为分</b>（如订单总金额为 1 元，此处请填 100）。| **required**
client_ip |  发起支付请求终端的 IP 地址，格式为 IPV4，如: 127.0.0.1。|**required**
currency |  三位 ISO 货币代码，目前仅支持人民币 `cny`。| **required**
subject |  商品的标题，该参数最长为 32 个 Unicode 字符，银联全渠道（upacp/upacp_wap）限制在 32 个字节。| **required**
body | **required** 商品的描述信息，该参数最长为 128 个 Unicode 字符，yeepay_wap 对于该参数长度限制为 100 个 Unicode 字符。
extra | 特定渠道发起交易时需要的额外参数以及部分渠道支付成功返回的额外参数。| **optional**
time_expire |  订单失效时间，用 Unix 时间戳表示。时间范围在订单创建后的 1 分钟到 15 天，默认为 1 天，创建时间以 Ping++ 服务器时间为准。 微信对该参数的有效值限制为 2 小时内；银联对该参数的有效值限制为 1 小时内。 | **optional**
metadata | [参考 Metadata 元数据](https://www.pingxx.com/document/api#api-metadata)。| **optional**
description | 订单附加说明，最多 255 个 Unicode 字符。| **optional**

###返回参shu 
鉴于支付渠道对 order_no 的合法性要求，为了保证支付请求的正确处理，请务必保证对于同一支付渠道下，不同支付产品间 order_no 的唯一性。例如：已在微信公众号下使用的 order_no 则无法在微信支付以及微信公众号扫码下重复使用，该规则同样适用于其他同类渠道。如果发生错误，则会返回错误码和错误详情，[详见 Errors 错误处理机制](#api-errors)。

##查询 Charge  对象//点击二级标题有的没反应 或不对应
``` curl
  POST https://api.pingxx.com/v1/charges
```
``` php
  \Pingpp\Charge::create();
```
``` java
  Charge.create();
```
``` ruby
  Pingpp::Charge.create()
```
``` nodejs
  pingpp.charges.create();
```
``` python
  pingpp.Charge.create()
```
``` go
  ch,err := charge.New(&ChargeParams)
```
``` csharp
  create(Dictionary&lt;String, Object&gt; param)
```
``` curl
  curl https://api.pingxx.com/v1/charges \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC: \
  -d order_no=123456789 \
  -d amount=100 \
  -d app[id]=app_1Gqj58ynP0mHeX1q \
  -d channel=upacp \
  -d currency=cny \
  -d client_ip=127.0.0.1 \
  -d subject="Your Subject" \
  -d body="Your Body"
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  \Pingpp\Charge::create(array(
    'order_no'  =&gt; '123456789',
    'amount'    =&gt; '100',
    'app'       =&gt; array('id' =&gt; 'app_1Gqj58ynP0mHeX1q'),
    'channel'   =&gt; 'upacp',
    'currency'  =&gt; 'cny',
    'client_ip' =&gt; '127.0.0.1',
    'subject'   =&gt; 'Your Subject',
    'body'      =&gt; 'Your Body'
  ));
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Map&lt;String, Object&gt; chargeParams = new HashMap&lt;String, Object&gt;();
  chargeParams.put("order_no",  "123456789");
  chargeParams.put("amount", 100);
  Map&lt;String, String&gt; app = new HashMap&lt;String, String&gt;();
  app.put("id", "app_1Gqj58ynP0mHeX1q");
  chargeParams.put("app", app);
  chargeParams.put("channel",  "upacp");
  chargeParams.put("currency", "cny");
  chargeParams.put("client_ip",  "127.0.0.1");
  chargeParams.put("subject",  "Your Subject");
  chargeParams.put("body",  "Your Body");

  Charge.create(chargeParams);
```
``` ruby
  require "pingpp"
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.create(
    :subject  =&gt; "Your Subject",
    :body     =&gt; "Your Body",
    :amount   =&gt; 100,
    :order_no =&gt; "123456789",
    :channel  =&gt; "upacp",
    :currency =&gt; "cny",
    :client_ip=&gt; '127.0.0.1',
    :app =&gt; {'id' =&gt; "app_1Gqj58ynP0mHeX1q"}
  )
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.create({
    subject: "Your Subject",
    body: "Your Body",
    amount: 100,
    order_no: "123456789",
    channel: "upacp",
    currency: "cny",
    client_ip: "127.0.0.1",
    app: {id: "app_1Gqj58ynP0mHeX1q"}
  }, function(err, charge) {
    // 异步调用
  });
```
``` python
  ch = pingpp.Charge.create(
    order_no='1234567890',
    amount=100,
    app=dict(id='app_1Gqj58ynP0mHeX1q'),
    channel='upacp',
    currency='cny',
    client_ip='127.0.0.1',
    subject='Your Subject',
    body='Your Body',
  )
```
``` go
  params := &ChargeParams{
    Order_no:  "123456789",
    App:       pingpp.App{Id: "app_1Gqj58ynP0mHeX1q"},
    Channel:   "upacp",
    Amount:    100,
    Currency:  "cny",
    Client_ip: "127.0.0.1",
    Subject:   "Your Subject",
    Body:      "Your Body",
  }
  //获得的第一个参数即是 Charge 对象
  ch, err := charge.New(params)
```
``` csharp
    Dictionary&lt;String, Object&gt; app = new Dictionary&lt;String, Object&gt;();
    app.Add("id", app_1Gqj58ynP0mHeX1q);
    Dictionary&lt;String,Object&gt; extra = new Dictionary&lt;String,Object&gt;();
    Dictionary&lt;String, Object&gt; params = new Dictionary&lt;String, Object&gt;();
    params.Add("amount", 100);
    params.Add("currency", "cny");
    params.Add("subject", "Your Subject");
    params.Add("body", "Your Body");
    params.Add("order_no", "123456789");
    params.Add("channel", "upacp");
    params.Add("client_ip", "127.0.0.1");
    params.Add("app", app);     
    params.Add("extra", extra);
    try {
        //发起交易请求
        Charge ch = Charge.create(params);
        Console.WriteLine(ch);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```
``` curl
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` php
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` java
com.pingplusplus.model.Charge JSON: {
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` ruby
#&lt;Pingpp::Charge id=ch_L8qn10mLmr1GS8e5OODmHaL4&gt; JSON: {
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "object": "charge",
  "created": 1410834527,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409161028470000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` nodejs
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` python
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` go
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` csharp
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
通过`charge`对象的`id`查询一个已创建的`charge`对象。可以在后台异步通知之前，通过查询接口确认支付状态。

###canshu
参数 | 描述
---- | ----
id | **required** 查询的 `charge` 对象 `id`。

###返回s
返回一个已存在的 `charge` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。



##查询 Charge 对象列表

返回之前创建过 `charge` 对象的一个列表。列表是按创建时间进行排序，总是将最新的 `charge` 对象显示在最前。

参数 | 描述  | 是否必须
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional** 
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_end`，你可以使用 `starting_after` = <code>obj_end </code> 去获取下一页。| **optional** 
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 `id` 是 `obj_start`，你可以使用 `ending_before` = `obj_start` 去获取上一页。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示，详情参考[created参数说明](链接)。| **optional**
app[id] | 支付使用的 `app` 对象的 `id`。| **required** 
channel | 支付使用的支付渠道：alipay, alipay_wap, wx, upacp<sup>*</sup>, upacp_wap<sup>*</sup>, bfb, wx_pub 对应支付宝，支付宝手机网页支付，微信，银联，银联手机网页支付，百度钱包，微信公众账号支付。<br />(*工作室用户使用 upmp、upmp_wap，公司用户使用 upacp、upacp_wap) | **optional** 
paid | 是否已付款。| **optional**
refunded | 是否存在退款信息，无论退款是否成功。| **optional**

###created参数说明
参数 | 描述 | 是否必须
---- | ---- | ----
created[gt] | 大于 charge 对象的创建时间，用 Unix 时间戳表示。| optional
created[gte]| 大于或等于 charge 对象的创建时间，用 Unix 时间戳表示。| optional
created[lt] | 小于 charge 对象的创建时间，用 Unix 时间戳表示。| optional 
created[lte]| 小于或等于 charge 对象的创建时间，用 Unix 时间戳表示。| optional

###返回内容1
返回一个已存在的 `charge` 对象或者一个错误，[详见 Errors 错误处理机制](#api-errors)。

``` curl
  GET https://api.pingxx.com/v1/charges/{CHARGE_ID}
```
``` php
  \Pingpp\Charge::retrieve({CHARGE_ID});
```
``` java
  Charge.retrieve({CHARGE_ID});
```
``` ruby
  Pingpp::Charge.retrieve({CHARGE_ID})
```
``` nodejs
  pingpp.charges.retrieve({CHARGE_ID});
```
``` python
  ch = pingpp.Charge.retrieve('CHARGE_ID')
```
``` go
  ch, err := charge.Get("CHARGE_ID")
```
``` csharp
  retrieve(String id)
```
``` curl
  curl https://api.pingxx.com/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4 \
  -u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC:
```
``` php
  \Pingpp\Pingpp::setApiKey('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');

  \Pingpp\Charge::retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4');
```
``` java
  Pingpp.apiKey = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC";

  Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4");
```
``` ruby
  Pingpp.api_key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  Pingpp::Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4")
```
``` nodejs
  var pingpp = require('pingpp')('sk_test_ibbTe5jLGCi5rzfH4OqPW9KC');
  pingpp.charges.retrieve(
    "ch_L8qn10mLmr1GS8e5OODmHaL4",
    function(err, charge) {
      // 异步调用
    }
  );
```
``` python
  pingpp.api_key = 'sk_test_ibbTe5jLGCi5rzfH4OqPW9KC'
  ch = pingpp.Charge.retrieve('ch_L8qn10mLmr1GS8e5OODmHaL4')
```
``` go
  pingpp.Key = "sk_test_ibbTe5jLGCi5rzfH4OqPW9KC"
  ch, err := charge.Get("ch_L8qn10mLmr1GS8e5OODmHaL4")
```
``` csharp
    try {
        Charge ch = Charge.retrieve("ch_L8qn10mLmr1GS8e5OODmHaL4");
        Console.WriteLine(ch);
    } catch (Exception e) {
        Console.WriteLine(e.Message.ToString());
    }
```

``` curl
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` php
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` java
com.pingplusplus.model.Charge JSON: {
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` ruby
#&lt;Pingpp::Charge id=ch_L8qn10mLmr1GS8e5OODmHaL4&gt; JSON: {
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4",
  "object": "charge",
  "created": 1410834527,
  "livemode": true,
  "paid": false,
  "refunded": false,
  "app": "app_1Gqj58ynP0mHeX1q",
  "channel": "upacp",
  "order_no": "123456789",
  "client_ip": "127.0.0.1",
  "amount": 100,
  "amount_settle": 100,
  "currency": "cny",
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127,
  "time_settle": null,
  "transaction_no": null,
  "refunds": {
    "object": "list",
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds",
    "has_more": false,
    "data": []
  },
  "amount_refunded": 0,
  "failure_code": null,
  "failure_msg": null,
  "metadata": {},
  "credential": {
    "object": "credential",
    "upacp": {
      "tn": "201409161028470000000",
      "mode": "01"
    }
  },
  "description": null
}
```
``` nodejs
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` python
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` go
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```
``` csharp
{
  "id": "ch_L8qn10mLmr1GS8e5OODmHaL4", 
  "object": "charge", 
  "created": 1410834527, 
  "livemode": true, 
  "paid": false, 
  "refunded": false, 
  "app": "app_1Gqj58ynP0mHeX1q", 
  "channel": "upacp",
  "order_no": "123456789", 
  "client_ip": "127.0.0.1", 
  "amount": 100, 
  "amount_settle": 100, 
  "currency": "cny", 
  "subject": "Your Subject",
  "body": "Your Body",
  "extra":{},
  "time_paid": null,
  "time_expire": 1410838127, 
  "time_settle": null, 
  "transaction_no": null, 
  "refunds": {
    "object": "list", 
    "url": "/v1/charges/ch_L8qn10mLmr1GS8e5OODmHaL4/refunds", 
    "has_more": false, 
    "data": [ ]
  }, 
  "amount_refunded": 0, 
  "failure_code": null, 
  "failure_msg": null, 
  "metadata": {}, 
  "credential": {
    "object": "credential", 
    "upacp": {
      "tn": "201409161028470000000", 
      "mode": "01"
    }
  }, 
  "description": null
}
```

