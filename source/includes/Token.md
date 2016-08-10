#Token 令牌

顾客购买时在客户端输入完整卡片信息后 Ping++ Client SDK 会主动调用 `token` 接口请求生成一个支付 `token`，在请求 `charge` 时 Ping++ Client SDK 会传入这个参数， `token` 生成后用于支付的有效期是 15 分钟，15 分钟之后不能支付但仍可以绑卡。**注意**：支付时客户端不需要请求该`token` 接口，以下仅为格式显示，如需要查询 `token` 内的详细卡信息时可以调用以`token`  查询接口。

###canshu
参数 | 描述 | 类型
---- | ---- | ----
id | Token 对象 id | **string** 
object | 值为 token | **string** 
created | Token 创建的时间，用 Unix 时间戳表示 | **timestamp** 
livemode | 支付是否处于 live 模式 | **boolean** 
used | 是否已使用于付款| **boolean** 
time_used | 使用于付款的时间| **timestamp** 
type | 对应的资源类型，值为 card| **stringtoken** 
card | Card 对象| **hash** 
sms_code | SMS Code 对象。外卡时，该对象内容为空 | **hash** 


``` curl
	#### 银联卡
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` php
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` java
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` ruby
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` nodejs
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` python
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` go
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```
``` csharp
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
        "code": null
    }
}
```

``` curl
	#### 外卡
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` php
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` java
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` ruby
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` nodejs
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` python
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` go
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```
``` csharp
{
    "id": "tok_Pav9qLDunDOSKivXDCjTOKa5",
    "object": "token",
    "created": 1441793037,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_14uv9KTm14yHP8u5S0SWjfX9",
        "object": "card",
        "created": 1441769298,
        "last4": "0019",
        "funding": "credit",
        "brand": "MasterCard",
        "bank": null,
        "customer": null
    },
    "sms_code": {
        
    }
}
```


##查询 Token 对象
可根据 `token id` 查询某条 `token` 对象中的 `card` 信息。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
<dt>{TOKEN_ID}:  | Token 对象 id | **required**

``` curl
  GET https://api.pingxx.com/v1/tokens/{TOKEN_ID}
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
    curl https://api.pingxx.com/v1/tokens/tok_Ca1GS4Ha9aL01i5ubHHC8CaP\
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
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` php
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` java
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` ruby
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` nodejs
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` python
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` go
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```
``` csharp
{
    "id": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP",
    "object": "token",
    "created": 1441792948,
    "livemode": true,
    "used": false,
    "time_used": null,
    "type": "card",
    "card": {
        "id": "card_C8mzP08COqb5vjP0OGXnHanH",
        "object": "card",
        "created": 1441699192,
        "last4": "1261",
        "funding": "debit",
        "brand": "UnionPay",
        "bank": "cmb",
        "customer": null
    },
    "sms_code": {
        "id": "sms_WvbLC4aH0ifPnz90OCnDyvHO",
        "object": "sms_code",
        "created": 1441792949,
        "validated": false,
        "source": "tok_Ca1GS4Ha9aL01i5ubHHC8CaP"
    }
}
```





