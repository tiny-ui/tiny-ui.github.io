---
layout: default
title: Loading
nav_order: 2
parent: 交互
grand_parent: API

---

# Loading

## 说明

基于安卓原生样式的Loading弹窗

## 使用

```javascript
//showListener: 弹窗展示后的回调
//dismissListener: 弹窗消失后的回调
//isCancelable: 是否能通过蒙层关闭弹窗
let loading = TinyAPI.interact.createLoading({
    showListener: () => {},
    dismissListener: () => {},
    isCancelable: true,
})

//展示弹窗
loading.show()
//隐藏弹窗
loading.hide()
```

## 示例

```javascript
let loading = TinyAPI.interact.createLoading({
    showListener: () => {
        console.log("暂时弹窗")
    },
    dismissListener: () => {
        console.log("隐藏弹窗")
    },
    isCancelable: true,
})

loading.show()

setTimeout(() => {
    loading.hide()
})

```

## 参数

| 属性 | 类型 | 默认值  | 必填  | 说明 | 最低版本支持 |
|:----|:----|:-----|:----|:----|:-----------|
| content | function | -    | 否   | 通用弹窗样式，返回组件 | v0.3.0 |
| showListener | function | -    | 否   | 弹窗展示后的回调 | v0.3.0 |
| dismissListener | function | -    | 否   | 弹窗消失后的回调 | v0.3.0 |
| isCancelable | boolean | true | 否   | 点击蒙层能否关闭按钮 | v0.3.0 |
| isCanceledOnTouchOutside | boolean | true | 否   | 是否能通过点击蒙层关闭弹窗 | v0.3.0 |

## tips

Loading 弹窗不会自动消失，必须要开发者手动进行调用。  
目前样式是基于安卓原生的，可能后期 UI 加入会进行改动  
之后会支持参数配置的单独方法，并且把 Loading 的 js 部分封装成 Class  