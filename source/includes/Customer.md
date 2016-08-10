#Customer 顾客

创建 Customer 对象用于存储用户信息。若在创建 `Customer` 时传入 `token id `则可以进行绑卡。**注意**：暂时不允许通过外卡创建

###canshu

参数 | 描述 | 类型
---- | ---- | ----
id | Customer 对象 id | **string** 
object | 值为 Customer | **string**
created | Customer 对象创建的时间，用 Unix 时间戳表示 | **timestamp** 
livemode| 支付是否处于 live 模式 | **boolean** 
app | App 对象的 id，expandable | **string**
name | 持卡人姓名 | **string**
email  | 地址| **stringemail**
currency | 三位货币代码 | **string**
description  | 描述信息 | **string**
metadata  | Metadata | **hash**
sources | 资源列表 | **list**
default_source | 默认资源对象的 id，expandable | **string**

``` curl
{
    "id": "cus_yvn1m5SCG4eLCy",
    "object": "customer",
    "created": 1444390718,
    "livemode": true,
    "app": "app_1Gqj58ynP0mHeX1q",
    "name": "张三",
    "email": null,
    "currency": null,
    "description": null,
    "metadata": null,
    "sources": {
        "object": "list",
        "url": "/v1/customers/cus_yvn1m5SCG4eLCy/sources",
        "has_more": false,
        "data": [
            {
                "id": "card_ubDu1GTmznz1P4OKCKqH8qzP",
                "object": "card",
                "created": 1444388292,
                "last4": "8703",
                "funding": "debit",
                "brand": "UnionPay",
                "bank": "boc",
                "customer": "cus_yvn1m5SCG4eLCy"
            }
        ]
    },
    "default_source": "card_ubDu1GTmznz1P4OKCKqH8qzP"
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


##创建 Customer 对象
创建一个用户同时附带一张卡片，即绑卡。
绑卡时需要传入 `token id` ，default_source 为该卡片 注：暂时不允许通过外卡创建。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
app | App 对象 id | **required**
source | Token 对象 id | **required**
sms_code[id] | SMS Code 对象 id | **required**
sms_code[code] | 短信验证码 | **required**
description | 描述信息 | **optional**
email | 顾客的 email | **optional**
metadata | Metadata | **optional**
###fanhui
返回一个 Customer 对象。

``` curl
  POST https://api.pingxx.com/v1/customers
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
    curl https://api.pingxx.com/v1/customers \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO: \
    -d '{
    "app": "app_1Gqj58ynP0mHeX1q",
    "source": "tok_BHTPMJCtIJ8HaqXBDr4ILeLJ",
    "sms_code":{
    "code" : "123456",
    "id" : "sms_BHTPMJCpGc8qiKvva3OgBV2V"
    }
}'
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
    "id": "cus_yvn1m5SCG4eLCy",
    "object": "customer",
    "created": 1444390718,
    "livemode": true,
    "app": "app_1Gqj58ynP0mHeX1q",
    "name": "张三",
    "email": null,
    "currency": null,
    "description": null,
    "metadata": null,
    "sources": {
        "object": "list",
        "url": "/v1/customers/cus_yvn1m5SCG4eLCy/sources",
        "has_more": false,
        "data": [
            {
                "id": "card_ubDu1GTmznz1P4OKCKqH8qzP",
                "object": "card",
                "created": 1444388292,
                "last4": "8703",
                "funding": "debit",
                "brand": "UnionPay",
                "bank": "boc",
                "customer": "cus_yvn1m5SCG4eLCy"
            }
        ]
    },
    "default_source": "card_ubDu1GTmznz1P4OKCKqH8qzP"
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


##更新 Customer 对象
该接口支持更新已经绑定的 `Customer` 的信息。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象的 id | **required**
description | 描述信息 | **optional**
email | 顾客的 Email | **optional**
metadata | Metadata | **optional**
default_source | 选择默认资源对象的 id，只能从已绑定资源中选择，不能设置为 null | **optional**


``` curl
  PUT https://api.pingxx.com/v1/customers/{CUS_ID}
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
    curl -X PUT https://api.pingxx.com/v1/customers/cus_iHGeb9T8Ki5CeT \
    -u sk_live_vjfr92jj3q925KuPO82iP8KO: \
    -d app＝app_1Gqj58ynP0mHeX1q \
    -d metadata[testkey]=test
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
    "id": "cus_iHGeb9T8Ki5CeT",
    "object": "customer",
    "created": 1441698046,
    "livemode": true,
    "app": "app_1Gqj58ynP0mHeX1q",
    "name":"张三",
    "email": null,
    "currency": null,
    "description": null,
    "metadata": {
        "testkey": "test"
    },
    "sources": {
        "object": "list",
        "url": "/v1/customers/cus_iHGeb9T8Ki5CeT/sources",
        "has_more": false,
        "data": [
            {
                "id": "card_5CazT8rPqDOGOqz5aPjzrvbH",
                "object": "card",
                "created": 1441698040,
                "last4": "1261",
                "funding": "debit",
                "brand": "UnionPay",
                "bank": "cmb",
                "customer": "cus_iHGeb9T8Ki5CeT"
            }
        ]
    },
    "default_source": "card_5CazT8rPqDOGOqz5aPjzrvbH"
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


##删除 Customer 对象
调用删除接口，传入 `Customer id ` 可以使对应的信息无法访问。
注：绑定的资源信息不会被删除，但是无法访问
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
<dt>{CUS_ID}: | 要删除的 Customer 对象的 id | **required**

##查询 Customer 对象
通过 `Customer` 对象的 `id` 查询一个已经创建的 `Customer` 对象的详细信息。

###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
{CUS_ID}:  | Customer 对象 id。| **required**

``` curl
    DELETE https://api.pingxx.com/v1/customers
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
    curl -X DELETE https://api.pingxx.com/v1/cstomers/cus_K88iDSXX94eTmX \
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
    "deleted": true,
    "id": "cus_K88iDSXX94eTmX"
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


##查询 Customer 对象列表
返回之前创建过的 `Customer` 对象的一个列表，列表是按创建时间进行排序，总是将最新的`Customer` 对象显示在最前。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示。| **timestamp**

``` curl
    GET https://api.pingxx.com/v1/customers
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
    curl https://api.pingxx.com/v1/customers/?limit=3 \
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
    "url": "/v1/customers",
    "has_more": false,
    "data": [
        {
            "id": "cus_eHi1mD1iPS08Li",
            "object": "customer",
            "created": 1441796275,
            "livemode": true,
            "app": "app_1Gqj58ynP0mHeX1q",
            "name":"张三",
            "email": null,
            "currency": null,
            "description": null,
            "metadata": {
            },
            "sources": {
                "object": "list",
                "url": "/v1/customers/cus_eHi1mD1iPS08Li/sources",
                "has_more": false,
                "data": [
                ]
            },
            "default_source": null
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



































