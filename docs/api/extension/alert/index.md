---
layout: default
title: alert
nav_order: 3
parent: 扩展
grand_parent: API
---

# alert

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

## 说明
`alert`方法提供了简单的 Android 层弹窗提示，可以从全局对象中访问到

## 使用
```javascript
//参数为 string 类型的文本
alert(text);
```

## 示例
```typescript
alert("login")
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| text | String | - | 是 | 弹窗显示文本 | v0.3.0 |