---
layout: default
title: getPrimaryClip
nav_order: 2
parent: 剪贴板
grand_parent: 设备
---

# getPrimaryClip
## 说明
获取Android系统剪切板中的内容，包含文字和颜文字

## 使用
```javascript
TinyAPI.device.getPrimaryClip(success, fail)
```

## 示例
```javascript
TinyAPI.device.getPrimaryClip((res) => {
    console.log(res) 
}, (res) => {
    console.log(res.errMsg)
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| success | Function | - | 是 | 方法调用成功回调函数 | v0.3.0 |
| fail | Function | - | 否 | 方法调用失败回调函数 | v0.3.0 |

### success参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| res | String | - | - | 剪贴板内容| v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| errMsg | String | - | - | 详细失败原因 | v0.3.0 |
