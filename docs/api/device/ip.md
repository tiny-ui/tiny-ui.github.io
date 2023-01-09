---
layout: default
title: ip
nav_order: 9
parent: 设备
grand_parent: API
---

# IP

## 说明
获取设备IP外网地址

## 示例
```javascript
var result = TinyAPI.device.ip();

// result = 10.118.56.15
```

## 出参

| 属性名    | 类型     | 属性说明 | 必填  | 默认值    | 取值范围                   |
|:-------|:-------|:-----|:----|:-------|:-----------------------|
| result | string | ip地址 |     |  |  |