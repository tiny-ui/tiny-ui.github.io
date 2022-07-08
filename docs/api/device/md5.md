---
layout: default
title: encryptMD5
nav_order: 9
parent: 设备
grand_parent: API
---

# encryptMD5

## 说明
对传入字符串进行MD5加密

## 示例
```javascript
var result = TinyAPI.device.md5("Sunmi Test");

// result = 9CF6887943903086575CAF948E6F095F
```

## 入参

| 属性名  | 类型     | 属性说明       | 必填  | 默认值    | 取值范围                   |
|:-----|:-------|:-----------|:----|:-------|:-----------------------|
| text | string | 需要MD5加密字符串 | 是   |  |  |

## 出参

| 属性名    | 类型     | 属性说明     | 必填  | 默认值    | 取值范围                   |
|:-------|:-------|:---------|:----|:-------|:-----------------------|
| result | string | MD5加密后结果 |     |  |  |