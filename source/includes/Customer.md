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

##查询 Customer 对象列表
返回之前创建过的 `Customer` 对象的一个列表，列表是按创建时间进行排序，总是将最新的`Customer` 对象显示在最前。
###canshu
参数 | 描述 | 是否必须
---- | ---- | ----
limit | 限制每页可以返回多少对象，范围为 1-100 项，默认是 10 项。| **optional**
created | 对象的创建时间，用 Unix 时间戳表示。| **timestamp**

































