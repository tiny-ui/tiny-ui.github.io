---
layout: default
title: 网络状态
nav_order: 2
parent: 设备
grand_parent: API
---

# 网络状态

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

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

{:toc}

# getNetworkType
## 说明
获取设备当前所处的网络类型

## 使用
```javascript
TinyAPI.device.getNetworkType(options)
```

## 示例
```javascript
TinyAPI.device.getNetworkType({
    success: (networkType) => {
        console.log(networkType)
    },
    fail: (error) => {
        console.log(error)
    }
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| option | Object | - | 否 | 回调方法 | v0.3.0 |

### option参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| success | Function | - | 否 | 方法调用成功回调函数 | v0.3.0 |
| fail | Function | - | 否 | 方法调用失败回调函数 | v0.3.0 |

### success参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| networkType | String | - | - | 网络类型 | v0.3.0 |

#### networkType有效值

| 属性 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| wifi | wifi网络 | v0.3.0 |
| 2g | 2g网络 | v0.3.0 |
| 3g | 3g网络 | v0.3.0 |
| 4g | 4g网络 | v0.3.0 |
| unknown | 不常见的网络类型(包含5g) | v0.3.0 |
| none | 无网络 | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| error | String | - | - | 失败原因 | v0.3.0 |