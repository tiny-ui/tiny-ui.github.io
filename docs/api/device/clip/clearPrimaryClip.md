---
layout: default
title: clearPrimaryClip
nav_order: 3
parent: 剪贴板
grand_parent: 设备
---

# clearPrimaryClip
## 说明
清空Android系统剪切板中的内容

## 使用
```javascript
TinyAPI.device.clearPrimaryClip(success, fail)
```

## 示例
```javascript
TinyAPI.device.clearPrimaryClip(() => {

}, (fail) => {
    console.log(fail)
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| success | Function | - | 否 | 方法调用成功回调函数 | v0.3.0 |
| fail | Function | - | 否 | 方法调用失败回调函数 | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| errMsg | String | - | - | 详细失败原因 | v0.3.0 |
