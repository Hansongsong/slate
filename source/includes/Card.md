#Card卡片

卡片对象，依附于 Customer 对象的资源列表。相同的卡片信息 + 同一个 App 对应唯一的 Card Number。

###canshu
参数 | 描述| 类型
---- | ---- | ----
id | Card 对象 id | **string**
object | 值为 card | **string**
created | 卡片第一次的创建时间 | **timestamp**
last4: | 卡号末 4 位  | **string**
funding | 卡片借贷记类型 "credit" 信用卡，"debit" 储蓄卡，"unknown" 未知 | **string**
brand | 卡品牌，值为 "UnionPay", "Visa", "MasterCard", "JCB" 其中一种 | **string**
bank | 发卡行，如 "icbc" 工商银行，具体[银行列表见附录](#nocard_bank_id)。外卡此参数为 null | **string**
customer | 依附的 Customer 对象的 id | **string**

``` curl
{
    "id": "card_C8mzP08COqb5vjP0OGXnHanH",
    "object": "card",
    "created": 1441699192,
    "last4": "1261",
    "funding": "debit",
    "brand": "UnionPay",
    "bank": "cmb",
    "customer": "cus_eHi1mD1iPS08Li"
}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```


##创建 Card 对象
在 Customer 对象的资源列表上添加一个新的卡片，之后就可以选卡支付，即绑卡。  
注：暂时不允许通过外卡创建。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象 id | **required**
source | Token 对象 id | **required**
sms_code[id] | SMS Code 对象 id| **required**
sms_code[code] | 短信验证码| **required**

###返回1
返回一个 Card 对象。

``` curl
  POST https://api.pingxx.com/v1/customers/{CUS_ID}/sources
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
    curl https://api.pingxx.com/v1/customers/cus_eHi1mD1iPS08Li/sources \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO: \
     -d '{
    "source": "tok_BHTPMJCtIJ8HaqXBDr4ILeLJ",
    "sms_code":{
    "code" : "123456",
    "id" : "sms_BHTPMJCpGc8qiKvva3OgBV2V"
    }
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
{
    "id": "card_C8mzP08COqb5vjP0OGXnHanH",
    "object": "card",
    "created": 1441699192,
    "last4": "1261",
    "funding": "debit",
    "brand": "UnionPay",
    "bank": "cmb",
    "customer": "cus_eHi1mD1iPS08Li"
}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```

##删除 Card 对象
取消与 Customer 对象的关联。删除的如果是该所属 Customer 对象的 default_source, 则 default_source 为最近一张绑定的资源 id 如果删除后资源列表为空，则 default_source 值为 null

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象 id | **required**
{CARD_ID}:  | 要删除的 Card 对象 id | **required**

``` curl
  POST https://api.pingxx.com/v1/customers/{CUS_ID}/sources
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
    curl https://api.pingxx.com/v1/customers/cus_eHi1mD1iPS08Li/sources \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO: \
     -d '{
    "source": "tok_BHTPMJCtIJ8HaqXBDr4ILeLJ",
    "sms_code":{
    "code" : "123456",
    "id" : "sms_BHTPMJCpGc8qiKvva3OgBV2V"
    }
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
{
    "id": "card_C8mzP08COqb5vjP0OGXnHanH",
    "object": "card",
    "created": 1441699192,
    "last4": "1261",
    "funding": "debit",
    "brand": "UnionPay",
    "bank": "cmb",
    "customer": "cus_eHi1mD1iPS08Li"
}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```

##查询 Card 对象
通过 `Card` 对象的 `id` 查询一个已经创建的 `Card` 对象的详细信息。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象 id | **required**
{CARD_ID}:  | Card 对象 id | **required**

``` curl
  GET https://api.pingxx.com/v1/customers/{CUS_ID}/sources/{CARD_ID}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
    curl https://api.pingxx.com/v1/customers/cus_eHi1mD1iPS08Li/sources/card_C8mzP08COqb5vjP0OGXnHanH \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO:
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
{
    "id": "card_C8mzP08COqb5vjP0OGXnHanH",
    "object": "card",
    "created": 1441699192,
    "last4": "1261",
    "funding": "debit",
    "brand": "UnionPay",
    "bank": "cmb",
    "customer": "cus_eHi1mD1iPS08Li"
}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```


##查询 Card 对象列表
可以查询某 `Customer` 对象中关联的所有 `Card` 对象列表。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象 id | **required**
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
starting_after | 在分页时使用的指针，决定了列表的第一项从何处开始。假设你的一次请求返回列表的最后一项的 id 是 obj_end，你可以使用 starting_after=obj_end 去获取下一页。| **optional**
ending_before | 在分页时使用的指针，决定了列表的最末项在何处结束。假设你的一次请求返回列表的最后一项的 id 是 obj_start，你可以使用 ending_before=obj_start 去获取上一页。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示，参考[created参数说明]()。| **optional**

###created参数说明
参数 | 描述 | 是否必须
---- | ---- | ----
created[gt] | 大于 `Customer` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[gte] | 大于或等于 `Customer` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lt] | 小于 `Customer` 对象的创建时间，用 Unix 时间戳表示。| **optional**
created[lte] | 小于或等于 `Customer` 对象的创建时间，用 Unix 时间戳表示。| **optional**

``` curl
  GET https://api.pingxx.com/v1/customers/{CUS_ID}/sources
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
    curl https://api.pingxx.com/v1/customers/cus_eHi1mD1iPS08Li/sources/?limit=3 \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO:
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
``` curl
{
    "object": "list",
    "url": "/v1/customers/cus_eHi1mD1iPS08Li/sources",
    "has_more": false,
    "data": [
        {
            "id": "card_C8mzP08COqb5vjP0OGXnHanH",
            "object": "card",
            "created": 1441699192,
            "last4": "1261",
            "funding": "debit",
            "brand": "UnionPay",
            "bank": "cmb",
            "customer": "cus_eHi1mD1iPS08Li"
        },
        {...},
        {...}
    ]
}
```
``` php
```
``` java
```
``` ruby
```
``` nodejs
```
``` python
```
``` go
```
``` csharp
```
















