---
layout: default
title: verify
nav_order: 2
parent: 刷脸支付
grand_parent: API

---

# verify
## 说明
使用支付宝刷脸SDK，根据获取到到zim id去唤起刷脸界面

## 示例
```javascript
TinyAPI.pay.verify({
    zimId: "Test", // 这里填入正确的ID
    protocol: "",
    mode: "151524i39", // 这里填入正确的ID
    number: "",
    callback: (res) => {
        console.log(res);
    }
});
```

## 参数

| 属性名        | 类型       | 属性说明                                  | 必填  | 默认值 | 取值范围                                                         |
|:-----------|:---------|:--------------------------------------|:----|:----|:-------------------------------------------------------------|
| zimId | string   | 人脸初始化接口返回的 zimId, 其中包含了唤起人脸验证的关键参数。   | 是   |     |                                                              |
| protocol  | object   | 通过上一个服务端接口获取到到zim_init_client_data信息体 | 是   |     |                                                              |
| mode      | number   | 用于指定选择刷脸模式。值为 int 类型。0：主屏幕显示（默认值）；1：双面屏机具，副屏幕显示   | 否   | 0，1 |  |
| number  | string   | 用于会员刷脸付方案。填入用户登录会员系统的手机号。    | 否   |     |                                                              |
| callback   | function | 成功回调                                  | 是   |     |                                                              |

