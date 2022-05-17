---
layout: default
title: Toast
nav_order: 4
parent: 交互
grand_parent: API

---

# Toast

## 说明

调用以及展示 Android 原生的 Toast 弹窗

## 使用

```javascript
//content: Toast 要展示的文案
//duration: "long", "short"
//duration: 传入其他值或者不传，默认为 short
TinyAPI.interact.showToast("content", "long")

//content: Toast 要展示的文案
TinyAPI.interact.showToast("content")
```

## 示例

```javascript
TinyAPI.interact.showToast("需要展示的内容", "long")

//TinyAPI.interact.showToast("content")

```

## 参数


| 属性 | 类型 | 默认值 | 必填  | 说明                                             | 最低版本支持 |
|:----|:----|:----|:----|:-----------------------------------------------|:-----------|
| content | string | -   | 否   | Toast 要展示的文案                                   | v0.3.0 |
| duration | string | "short"    | 否   | Toast 展示的持续时间  "long"：较长的持续时间  "short"：较短的持续时间 | v0.3.0 |

## tips

Toast 展示后会根据 duration 参数经过一段时间后自动隐藏。不需要手动控制 Toast 的隐藏