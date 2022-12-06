---
layout: default
title: CustomDialog
nav_order: 1
parent: 交互
grand_parent: API

---

# CustomDialog

## 说明

一个完全自定义的弹窗，内容完全由使用者定义

## 使用

```javascript
//content: 通用弹窗样式，返回组件
//showListener: 弹窗展示后的回调
//dismissListener: 弹窗消失后的回调
//isCancelable: 点击蒙层能否关闭按钮
//back: 点击物理返回键能否关闭Dialog
let dialog = TinyAPI.interact.createCustomDialog({
    content: () => {},
    showListener: () => {},
    dismissListener: () => {},
    isCancelable,
    back
})
//展示弹窗
dialog.show()
//隐藏弹窗
dialog.hide()
```

## 示例

```javascript
let dialog = TinyAPI.interact.createCustomDialog({
    content: () => {
        return 	TinyDOM.createElement(
            "text",
            {},
            "这是一个自定义弹窗")
    },
    showListener: () => {
        console.log("展示弹窗")
    },
    dismissListener: () => {
        console.log("隐藏弹窗")
    },
    isCancelable: false,
    back: false
})

dialog.show()

setTimeout(() => {
    dialog.hide()
}, 3000)
```

## 参数

| 属性 | 类型 | 默认值  | 必填  | 说明 | 取值范围   |
|:----|:----|:-----|:----|:----|:-------|
| content | function | -    | 否   | 通用弹窗样式，返回组件 |  |
| showListener | function | -    | 否   | 弹窗展示后的回调 |  |
| dismissListener | function | -    | 否   | 弹窗消失后的回调 |  |
| isCancelable | boolean | true | 否   | 点击蒙层能否关闭按钮 |  |
| back            | boolean | false | 否   | 点击物理返回键是否让dialog消失 |        |

## tips

content 对应的方法必须要返回组件，否则端侧这边会报错  
之后会支持对蒙层的自定义
在副屏禁止调用该方法