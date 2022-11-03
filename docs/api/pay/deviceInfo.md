---
layout: default
title: info
nav_order: 1
parent: 刷脸支付
grand_parent: API

---

# deviceInfo
## 说明
使用支付宝刷脸SDK，获取运行该应用的设备信息

## 示例
```javascript
TinyAPI.pay.deviceInfo({
    merchantId: "Test", // 这里填入正确的ID
    partnerId: "",
    appId: "151524i39", // 这里填入正确的ID
    deviceNum: "",
    callback: (res, map) => {
        console.log(res, map);
    }
});
```

## 参数

| 属性名        | 类型       | 属性说明                                            | 必填  | 默认值 | 取值范围                                                         |
|:-----------|:---------|:------------------------------------------------|:----|:----|:-------------------------------------------------------------|
| merchantId | string   | 签约商家的 PID。以 2088 开头                             | 是   |     |                                                              |
| partnerId  | string   | 服务商的 PID。对于自用型商家，填写签约商家的 PID，和 merchantId 保持一致。 | 否   |     |                                                              |
| appId      | string   | 支付宝分配给开发者的应用 ID，和当面付请求的 appid 保持一致。             | 是   |     |  |
| deviceNum  | string   | 商户机具终端编号，和当面付请求的 terminal_id 保持一致。              | 否   |     |                                                              |
| callback   | function | 成功回调                                            | 是   |     |                                                              |

