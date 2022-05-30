---

layout: default 
title: sunmiPay
nav_order: 5 
parent: 扩展 
grand_parent: API

---

# SUNMI Pay

## 说明

 商米收银台Api

## qrCodePay

唤起商米收银台扫码支付

```javascript
TinyAPI.sunmi.qrCodePay({
    amount: 1,
    callSuccess: function (result) {
        console.error(result)
    },
    callFail: function (result) {
        console.log(result)
    }
});
```

## smilePay

唤起商米收银台人脸支付

```javascript
TinyAPI.sunmi.smilePay({
    amount: 1,
    callSuccess: function (result) {
        console.error(result)
    },
    callFail: function (result) {
        console.log(result)
    }
});
```

## payCode

接入方自行实现付款码扫码,将扫码所得字符串传入,唤起收银台进行收款.

```javascript
 TinyAPI.sunmi.payCode({
    amount: 1,
    payCode: "287708974200770165"
});
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 |
|:----|:----|:------|:-----|:----|
|amount|number(int)|无|✅|收款金额,单位 分|
|callFail|func|无|✅|调用支付API失败回调 code == -1:收银台安装状态异常;code == -2:收银台连接超时;code == -3:收银台连接异常;code == -4:收银台返回结果为空;code == -5:收银台连接中断|
|callSuccess|func|无|✅|调用支付API成功回调|
|orderId|string|无|❎|Saas系统的支付订单号(字符串)，用于标识当笔交易的支付订单号，交易处理结果中会带回 2.业务订单号与支付订单号的关系：一个业务订单号可以对应多个支付订单号，比如用户买了一件商品后会产生一个业务订单号和一个消费支付订单号，用户将此商品退款后又会产生一个退款的支付订单号。 3.如果Saas业务系统中业务订单号与支付订单号是一对一的关系或者没有支付订单号的情况那么两个订单号都填写业务订单号即可。 4.推荐不要超过32位|
|businessId|string|无|❎|1.Saas系统的业务订单号(字符串,不包含特殊字符)，用于标识当笔交易属于哪一笔业务订单，交易处理结果中会带回。2.业务订单号与支付订单号的关系：一个业务订单号可以对应多个支付订单号，比如用户买了一件商品后会产生一个业务订单号和一个消费支付订单号，用户将此商品退款后又会产生一个退款的支付订单号。3.如果Saas业务系统中业务订单号与支付订单号是一对一的关系或者没有支付订单号的情况那么两个订单号都填写业务订单号即可。4.最多50个字符长度|
|orderInfo|string|无|❎|商品名称或者其他商品信息。|
|pollingType|string|无|❎|轮询，收银台发起交易后，如果云端返回的交易结果状态为中间状态(支付中)，由收银台自动轮询做交易查询直至查询到交易的最终结果(成功或失败或超时)，收银台轮询时间最长为120s； not_polling: 不轮询，收银台发起交易后，直接将云端交易结果返回给调用方，如果返回中间状态的交易结果，应由调用方去查询交易的最终结果； 注意: 1.默认是polling模式 2.当交易返回码为D01、D07、F01、F02、Q02、Q04、Q07、Q11、Q14、S01、S02、S03(具体意义见附录B)的交易需要设计一个状态不明的订单状态并保存此订单等待后续追溯，可以在交易结果页放置一个查询按钮，由用户点击后发起查询 3. 不传值默认是polling模式，参数值传错则返回参数错误。|
|voiceBroadcast|boolean|无|❎|true:播报语音；false:不播放语音 注意: 1.扫码交易前金额播报、扫码交易结果播报，刷脸交易没有金额和交易结果语音播报2.默认以收银台设置的开关为准3.此参数对金融设备无效|
|printTicket|boolean|无|❎|为true时打印；为false时不打印；默认打印(兼容老字段)|
|printIdType|string|无|❎|订单类型:“mis”:商米收银台流水号；“order”:Saas软件订单号；“platform”：商户(第三方)订单号(银联扫码不支持)，不传值默认打印商米收银台流水号，参数值传错则返回参数错误|
|remarks|string|无|❎|打印小票上的备注(200个字符以内 仅限于扫码&扫脸)|

## 调用支付API回调参数

| 属性 | 类型 | 说明 |
|:----|:----|:----|
|success|bool| 是否调用成功 |
|data|string| 收银台返回数据json格式 |
|code|number(int)| 支付api 调用失败错误码 |

## 收银台返回数据

| 属性 | 类型 | 说明 |
|:----|:----|:----|
|resultCode|string| T00：成功非T00：失败, |
|resultMsg|string| 返回码描述 |
| appType | string | 00:银行卡应用01:聚合扫码支付应用02:银行卡+银联扫码支付应用51：刷脸支付 |
| transType | string | 交易类型 00－消费 |
| misId | string | 收银台流水号,用于标识当笔交易的订单号，交易处理结果中会带回。|
| orderId | string | Saas系统支付订单号. |
| businessId | string | Saas系统业务订单号. |
| platformId | string | 商户(第三方平台)订单号(微信、支付宝客户端显示的订单号，银行卡交易则返回系统参考号) |
| platform | string | 支付方式 wxpay：微信支付 alipay：支付宝支付 unionpay：银联钱包支付card：银行卡支付 |
| amount | number(int) | 交易金额 单位为分，1元表示为100L |
| amount1 | number(int) | 实付金额 单位为分，1元表示为100L |
| amount2 | number(int) | 优惠金额 单位为分，1元表示为100L |
| amount3 | number(int) | 商家优惠金额 单位为分，1元表示为100L |
| transDate | string | 交易日期 格式“MMdd” |
| transTime | string | 交易时间 格式“HHmmss” |
| voucherNum | string | 凭证号 撤销、查询、打印使用 |
| batchNum | string | 批次号 |
| referenceNum | string | 系统参考号 部分业务退货使用 |
| cardNum | string | 卡号 脱敏处理规则：除前六位和后四位之外其余位变*号处理。 |
| issuer | string | 发卡行 |
| acquirer | string | 收单行     |
| operatorId | string | 操作员号    |
| cardType | string | 卡类型 |
| accountType | string | 账户类型 “OA”：扫码”CC”：贷记卡 “DC”：借记卡 “SCC”：准贷记卡”EC”：电子现金 “MAG”：磁条卡 “VC”：Visa卡 “MC”：MasterCard 万事达卡 “AE”：美国运通卡 “JCB”：JCB卡是源自日本的世界通用国际信用”RPC”：RuPay(India)印度卡 |
| model | string | 机型 POS外设型号 |
| version | string | 版本 POS应用版本 |
| terminalId | string | 终端号 |
| merchantId | string | 商户号 |

## 收银台状态码定义

[附录B](https://docs.sunmi.com/general-function-modules/%e5%95%86%e7%b1%b3%e6%94%af%e4%bb%98/%e5%95%86%e7%b1%b3%e6%94%af%e4%bb%98%e7%bb%88%e7%ab%af%e5%af%b9%e6%8e%a5%e6%96%87%e6%a1%a3/%e9%99%84%e5%bd%95b/)

[附录C](https://docs.sunmi.com/general-function-modules/%e5%95%86%e7%b1%b3%e6%94%af%e4%bb%98/%e5%95%86%e7%b1%b3%e6%94%af%e4%bb%98%e7%bb%88%e7%ab%af%e5%af%b9%e6%8e%a5%e6%96%87%e6%a1%a3/%e9%99%84%e5%bd%95c/)