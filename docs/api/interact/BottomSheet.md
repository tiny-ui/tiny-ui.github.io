---
layout: default
title: BottomSheet
nav_order: 6
parent: 交互
grand_parent: API

---

# BottomSheet

## 说明

一个完全自定义的底部弹出浮层，内容完全由使用者定义

## 使用

```javascript
//content: 通用弹窗样式，返回组件
//showListener: 弹窗展示后的回调
//dismissListener: 弹窗消失后的回调
//isCancelable: 是否能通过手势或者蒙层关闭弹窗
//isCanceledOnTouchOutside: 是否能通过点击蒙层关闭弹窗
let bottomSheetDialog = TinyAPI.interact.createBottomSheet({
    content: () => {},
    showListener: () => {},
    dismissListener: () => {},
    isCancelable: true,
    isCanceledOnTouchOutside: true
})

// 展示 bottomSheet
bottomSheetDialog.show()
// 隐藏 bottomSheet
bottomSheetDialog.hide()
```

## 示例

```javascript
let bottomSheetDialog = TinyAPI.interact.createBottomSheet({
    content: () => {
        return 	TinyDOM.createElement(
            "text",
            {},
            "这是一个自定义弹窗")
    },
    showListener: () => {
        console.log("弹窗已展示")
    },
    dismissListener: () => {
        console.log("弹窗已隐藏")
    },
    isCancelable: false,
    isCanceledOnTouchOutside: true
})

bottomSheetDialog.show()

setTimeout(() => {
    bottomSheetDialog.hide()
}, 3000)

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

content 对应的方法必须要返回组件，否则端侧这边会报错  
之后会支持参数配置的单独方法，并且把 Dialog 的 js 部分封装成 Class