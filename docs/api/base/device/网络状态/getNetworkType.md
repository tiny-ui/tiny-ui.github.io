---
layout: default
title: getNetworkType
nav_order: 2
parent: 网络状态
grand_parent: 设备
---

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
| option | Object | - | 否 | 回调方法 | v0.3.0 |

### option参数

| success | Function | - | 否 | 方法调用成功回调函数 | v0.3.0 |
| fail | Function | - | 否 | 方法调用失败回调函数 | v0.3.0 |

### success参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| networkType | String | - | - | 网络类型 | v0.3.0 |

#### networkType有效值

| 属性 | 说明 | 最低版本支持 |
| wifi | wifi网络 | v0.3.0 |
| 2g | 2g网络 | v0.3.0 |
| 3g | 3g网络 | v0.3.0 |
| 4g | 4g网络 | v0.3.0 |
| unknown | 不常见的网络类型(包含5g) | v0.3.0 |
| none | 无网络 | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| error | String | - | - | 失败原因 | v0.3.0 |
