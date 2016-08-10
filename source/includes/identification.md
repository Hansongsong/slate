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

``` curl
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` php
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` java
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` ruby
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` nodejs
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` python
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` go
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```
``` csharp
{
    "type": "id_card",
    "app": "app_LibTW1n1SOq9Pin1",
    "result_code": 0,
    "message": "SUCCESS",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
```

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

``` curl
  POST https://api.pingxx.com/v1/identification
```
``` php
  POST https://api.pingxx.com/v1/identification
```
``` ruby
  POST https://api.pingxx.com/v1/identification
```
``` curl
curl https://api.pingxx.com/v1/identification \
-H "Pingplusplus-Signature: SIGNATURE" \
-H "Content-Type: application/json" \
-u sk_test_ibbTe5jLGCi5rzfH4OqPW9KC: \
-d '{
    "type": "bank_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000",
        "card_number": "6201111122223333"
    }
}'
```
```php
\Pingpp\Identification::identify(array(
    'type' => 'id_card',
    'app' => $app_id,
    'data' => array(
        'id_name' => '张三', // 姓名
        'id_number' => '310181198910107641' // 身份证号
    )
));
\Pingpp\Identification::identify(array(
    'type' => 'bank_card',
    'app' => $app_id,
    'data' => array(
        'id_name' => '张三', // 姓名
        'id_number' => '310181198910107641', // 身份证号,
        'card_number' => '6201111122223333', // 银行卡号
        'phone_number' => '18623234545' // 银行预留手机号，不支持 178 号段
    )
));
```
```ruby
Pingpp::Identification.identify(
  :type => "id_card",
  :app  => APP_ID,
  :data => {
      :id_name => "张三", # 姓名
      :id_number => "310181198910107641" # 身份证号
  }
)
Pingpp::Identification.identify(
  :type  => "bank_card",
  :app  => APP_ID,
  :data => {
      :id_name => "张三", # 姓名
      :id_number => "310181198910107641", # 身份证号
      :card_number => "6201111122223333", # 银行卡号
      :phone_number => "18623234545" # 银行预留手机号，不支持 178 号段
  }
)
```
``` curl
{
    "type": "bank_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "result_code": 3441,
    "message": "银行卡信息认证失败",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000",
        "card_number": "6201111122223333"
    }
}
```
``` php
{
    "type": "id_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "result_code": 3432,
    "message": "身份证信息匹配失败",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
{
    "type": "bank_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "result_code": 3441,
    "message": "银行卡信息认证失败",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000",
        "card_number": "6201111122223333"
    }
}
```
``` ruby
{
    "type": "id_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "result_code": 3432,
    "message": "身份证信息匹配失败",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000"
    }
}
{
    "type": "bank_card",
    "app": "app_1Gqj58ynP0mHeX1q",
    "result_code": 3441,
    "message": "银行卡信息认证失败",
    "paid":true,
    "data": {
        "id_name": "张三",
        "id_number": "320291198811110000",
        "card_number": "6201111122223333"
    }
}
```






