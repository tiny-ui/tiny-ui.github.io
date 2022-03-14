---
layout: default
title: isConnect
nav_order: 1
parent: 网络状态
grand_parent: 设备
---

# isConnect
## 说明
获取当前设备是否联网

## 使用
```javascript
let result = TinyAPI.device.isConnect();
```

## 示例
```javascript
let result = TinyAPI.device.isConnect();

console.log(result); // true, false
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| result | Boolean | - | - | 是否联网：true -> 联网，false -> 无网 | v0.3.0 |
