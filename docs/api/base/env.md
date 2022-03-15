---
layout: default
title: env
nav_order: 1
parent: 基础
grand_parent: API
---

# env
## 说明
获取手机设备的环境变量数据

## 使用
```javascript
let result = TinyAPI.basic.env();
```

## 示例
```javascript
let result = TinyAPI.basic.env();

console.log(result);
console.log(result.appInfo);
console.log(result.systemInfo);
```
---
result示例
{: .text-red-000 }
```json
{
    "platform":"Android",
    "build":"debug",
    "appInfo":{
        "appVersion":"0.0.1",
        "appName":"Elephant API测试",
        "appPackageName":"com.sunmi.elephant.yzk"
    },
    "systemInfo":{
        "brand":"SUNMI P2-B",
        "screenWidth":720,
        "screenHeight":1344,
        "osVersion":25
    }
}
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| result | Object | - | - | 方法返回结果 | v0.3.0 |

### result参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| platform | String | - | - | 运行平台（当前只有Android） | v0.3.0 |
| build | String | - | - | app版本类型：debug / release | v0.3.0 |
| appInfo | Object | - | - | app版本信息 | v0.3.0 |
| systemInfo | Object | - | - | 手机基础信息 | v0.3.0 |

### appInfo参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| appVersion | String | - | - | app版本号 | v0.3.0 |
| appName | String | - | - | app应用名称 | v0.3.0 |
| appPackageName | String | - | - | app应用包名 | v0.3.0 |

### systemInfo参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| brand | String | - | - | 手机品牌 | v0.3.0 |
| screenWidth | Integer | - | - | 手机屏幕宽度 / px | v0.3.0 |
| screenHeight | Integer | - | - | 手机屏幕高度 / px | v0.3.0 |
| osVersion | Integer | - | - | 手机版本号 | v0.3.0 |
