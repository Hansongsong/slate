#附录11
##易宝支付1
###附录一 易宝支付附表1

####表一 易宝支付商品类型码表1

商品类别码 | 作用域 | 商品类别码 | 描述
---- | ---- | ---- | ----
1 |虚拟产品 | 3	|公共事业缴费
4	|手机充值	|6	|公益事业
7	|实物电商	|8	|彩票业务
10	|行政教育	|11	|线下服务业
13	|微信实物电商	|14	|微信虚拟电商
15	|保险行业	|16	|基金行业
17	|电子票务	|18	|金融投资
19	|大额支付	|20	|其他
21	|旅游机票	|22	|畅付 D

####表二 用户标识类型码表1

代码 |含义|备注
---| ---|---
0	|IMEI	|国际移动设备身份码的缩写，国际移动装备辨识码，
是由 |15 |位数字组成的"电子串号"，它与每台手机一一对应
1	|MAC 地址	|MAC(Media Access Control)地址，或称为 MAC 位址、硬件位址，用来定义网络设备的位置。在 OSI模型中，第三层网络层负责IP 地址，第二层数据链路层则负责 MAC 位址。因此一个主机会有一个 IP 地址，而每个网络位置会有一个专属于它的 MAC 位址。
2	|用户 ID	 |用户编号
3	|用户 Email	
4	|用户手机号	
5	|用户身份证号	
6	|用户纸质订单协议号	

##应用内快捷支付1
###附录二 应用内快捷支付附表1
####表一 银行编码1

bank 参数 |	银行名称
----|----
test	|测试银行 (测试环境下国内卡)
test-foreign	|Test Foreign Brand (测试环境下外卡)
icbc	|工商银行
abc	|农业银行
ccb	|建设银行
bcm	|交通银行
boc	|中国银行
cmb	|招商银行
bob	|北京银行
dlcb	|大连银行
cgb	|广发银行
gzcb	|广州银行
hxb	|华夏银行
jlbk|	吉林银行
spdb|	浦发银行
bosh|	上海银行
pab	|平安银行
sjbc|	盛京银行
cib	|兴业银行
czb	|浙商银行
ceb	|光大银行
cmbc|	民生银行
psbc|	中国邮储
cncb|	中信银行
####表二 测试模式 - 银联借记卡 1

参数	|值
---- | ----
card_number	|6258333366661000
brand	|UnionPay
funding	|debit
bank	|test
name	|张三
cred_type	|ID
cred_number	|310115201510101236
phone_number	|13045678901

####表三 测试模式 - 银联借记卡 2

参数	|值
---- | ----
card_number	|6258333366662000
brand	|UnionPay
funding	|debit
bank	|test
name	|张三
cred_type	|ID
cred_number	|310115201510101236
phone_number	|13045678901

####表四 测试模式 - 银联借记卡 3

参数	|值
---- | ----
card_number	|6234555566663000
brand	|UnionPay
funding	|debit
bank	|test
name	|李四
cred_type	|ID
cred_number	|310115201510104568
phone_number	|13045678902

####表五 测试模式 - 银联借记卡 4

参数	|值
---- | ----
card_number	|6234555566664000
brand	|UnionPay
funding	|debit
bank	|test
name	|李四
cred_type	|ID
cred_number	|310115201510104568
phone_number	|13045678902

####表六 测试模式 - 外卡信用卡

参数	|值
card_number|	4111111111111200
brand	|Visa
funding	|credit
bank	|test-foreign
exp_month|	12
exp_year|	2016
cvc	|300

####表七 测试模式 - 外卡借记卡1

参数	|值
---- | ----
card_number	|4222222222222200
brand	|Visa
funding	|debit
bank	|test-foreign
exp_month	|12
exp_year	|2016
cvc	|400

##认证接口1
###附录三 认证接口1
####表一 result_code 说明1

返回码	|返回信息
---- | ----
0	|成功
3200	|无效的商户号
3204	|无效的sessionId
3300	|商户号未找到
3303	|商户号与服务访问账号不匹配
3420	|请求参数不合法
3431	|身份证信息不匹配
3432	|身份证信息匹配失败
3433	|身份验证活体照片非法
3434	|身份验证上传登记照失败
3435	|身份验证照片比对失败
3441	|银行卡信息认证失败
3442	|银行卡信息认证请求异常
3443	|银行卡信息认证请求超时
3451	|银行卡信息认证校验失败
3452	|银行卡信息认证校验异常

##报关接口1
###附录四 报关接口1
####表一 微信海关编号说明1

海关编号	|参数意义
---- | ----
GUANGZHOU	|广州海关
HANGZHOU	|杭州海关
NINGBO	|宁波海关
SHANGHAI	|上海海关
ZHENGZHOU_BS	|郑州海关(保税物流中心)
ZHENGZHOU_ZH	|郑州海关(综合保税区)
CHONGQING	|重庆海关

####表二 支付宝海关编号说明1

海关编号	|参数意义
---- | ----
HANGZHOU	|杭州海关
ZHENGZHOU	|郑州海关
GUANGZHOU	|广州海关
CHONGQING	|重庆海关
NINGBO	|宁波海关
SHENZHEN	|深圳海关
HENAN	|河南海关
SHANGHAI	|上海海关
XIAN	|西安海关
FUJIAN	|福建海关
TIANJIN	|天津海关
NANSHAGJ	|南沙国检
ZONGSHU	|海关总署











