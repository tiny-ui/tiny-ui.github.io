---
layout: default
title: 剪贴板
nav_order: 1
parent: 设备
grand_parent: API
---

# 剪贴板

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

# setPrimaryClip

## 说明
往Android系统剪切板中加入文字或者颜文字。多次设置剪切板的内容只会保存最后一次设置的结果

## 使用
```javascript
TinyAPI.device.setPrimaryClip("text", success, fail)
```

## 示例
```javascript
TinyAPI.device.setPrimaryClip("text", () => {

}, (res) => {
    console.log(res.errMsg)
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| text | String / Integer / Double | - | 是 | 要添加到剪切板的内容 | v0.3.0 |
| success | Function | - | 否 | 方法调用成功回调函数 | v0.3.0 |
| fail | Function | - | 否 | 方法调用失败回调函数 | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| errMsg | String | - | - | 详细失败原因 | v0.3.0 |

{:toc}

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

{:toc}

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