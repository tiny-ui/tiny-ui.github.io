---
layout: default
title: scan
nav_order: 8
parent: 设备
grand_parent: API
---

# scan

## 说明
开启扫码页面，只支持商米设备

## 示例
```javascript
TinyAPI.device.scan(
    {
        callback: (key, value) => {
            console.log(key + value);
        }
    }
    );

// key = QR-Code val = http://weixin.qq.com/r/5Cmiuq3EdPALrenZ93z2
```

## 入参

| 属性名    | 类型     | 属性说明 | 必填  | 默认值                                                      | 取值范围   |
|:-------|:-------|:-----|:----|:---------------------------------------------------------|:-------|
| option | object | 输入对象 | 否   |  |  |

## `option`参数

| 属性名         | 类型       | 属性说明                         | 必填  | 默认值    | 取值范围                   |
|:------------|:---------|:-----------------------------|:----|:-------|:-----------------------|
| ppi         | number   | 当前分辨率                        | 否   | 0X0003 | 0X0001, 0X0002, 0X0003 |
| sound       | boolean  | 扫描完成声音提示                     | 否   | true   |                        |
| vibrate     | boolean  | 扫描完成震动，目前M1硬件支持震动可用该配置，V1不支持 | 否   | false  |                        |
| moreCode    | boolean  | 识别画面中多个二维码                   | 否   | false  |                        |
| setting     | boolean  | 是否显示右上角设置按钮                  | 否   | true   |                        |
| album       | boolean  | 是否显示从相册选择图片按钮                | 否   | true   |                        |
| inverse     | boolean  | 允许识读反色二维码                    | 否   | true   |                        |
| ean8        | boolean  | 允许识读EAN-8码                   | 否   | true   |                        |
| upce        | boolean  | 允许识读UPC-E码                   | 否   | true   |                        |
| isbn10      | boolean  | 允许识读ISBN-10 (from EAN-13)码   | 否   | true   |                        |
| code11      | boolean  | 允许识读CODE-11码                 | 否   | false  |                        |
| upca        | boolean  | 允许识读UPC-A码                   | 否   | true   |                        |
| ean13       | boolean  | 允许识读AN-13码                   | 否   | true   |                        |
| isbn13      | boolean  | 允许识读ISBN-13 (from EAN-13)码   | 否   | true   |                        |
| interleaved | boolean  | 允许识读Interleaved 2 of 5码      | 否   | false  |                        |
| code128     | boolean  | 允许识读ECode 128码               | 否   | true   |                        |
| codabar     | boolean  | 允许识读Codabar码                 | 否   | true   |                        |
| code39      | boolean  | 允许识读Code 39码                 | 否   | true   |                        |
| code93      | boolean  | 允许识读Code 93码                 | 否   | true   |                        |
| databar     | boolean  | 允许识读DataBar (RSS-14)码        | 否   | true   |                        |
| exp         | boolean  | 允许识读DataBar Expanded码        | 否   | true   |                        |
| microPDF417 | boolean  | 允许识读Micro PDF417码            | 否   | true   |                        |
| microQR     | boolean  | 允许识读Micro QR Code码           | 否   | true   |                        |
| hanxin      | boolean  | 允许识读Hanxin Code码             | 否   | true   |                        |
| light       | boolean  | 是否显示闪光灯                      | 否   | true   |                        |
| mode        | boolean  | 是否是循环模式                      | 否   | false  |                        |
| qrCode      | boolean  | 允许识读QR码                      | 否   | true   |                        |
| isPDF417    | boolean  | 允许识读PDF417码                  | 否   | true   |                        |
| matrix      | boolean  | 允许识读DataMatrix码              | 否   | true   |                        |
| aztec       | boolean  | 允许识读AZTEC码                   | 否   | true   |                        |
| callback    | function | 扫码结果回调                       | 否   |    |                        |

## `callback`入参

| 属性名 | 类型     | 属性说明 | 必填  | 默认值    | 取值范围                   |
|:----|:-------|:-----|:----|:-------|:-----------------------|
| key | string | 扫码类型 |     |  |  |
| val | string | 扫码结果 |     |  |  |