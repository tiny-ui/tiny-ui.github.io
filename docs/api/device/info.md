---
layout: default
title: device info
nav_order: 3
parent: 设备
grand_parent: API
---

# device info

## 说明
获取当前设备信息

## 使用
```javascript
let result = TinyAPI.device.info();
```

## 示例
```javascript
let result = TinyAPI.device.info();

console.log(result);
```
---
result示例
{: .text-red-000 }
```text
platform: Android, 
appVersion: 0.0.1, 
appName: Elephant API测试, 
appPackageName: com.sunmi.elephant.yzk, 
brand: Android MuMu, 
osVersion: 23, 
screenWidth: 1170, 
screenHeight: 1872
```

## result参数

| 属性 | 类型      | 默认值 | 必填 | 说明                | 最低版本支持 |
|:----|:--------|:------|:-----|:------------------|:-----------|
| platform | String  | - | - | 当前运行平台类型（Android） | v0.3.0 |
| appVersion | String  | - | - | 当前应用版本号           | v0.3.0 |
| appName | String  | - | - | 当前应用名称            | v0.3.0 |
| appPackageName | String  | - | - | 当前应用包名            | v0.3.0 |
| brand | String  | - | - | 当前设备品牌型号          | v0.3.0 |
| osVersion | Integer | - | - | 当前设备系统版本号         | v0.3.0 |
| screenWidth | Integer | - | - | 当前设备屏幕宽度/px       | v0.3.0 |
| screenHeight | Integer | - | - | 当前设备屏幕高度/px       | v0.3.0 |