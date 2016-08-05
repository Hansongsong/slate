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

##查询 Token 对象
可根据 `token id` 查询某条 `token` 对象中的 `card` 信息。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
<dt>{TOKEN_ID}:  | Token 对象 id | **required**



