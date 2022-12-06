---
layout: default 
title: Dialog 
nav_order: 5
parent: 交互 
grand_parent: API

---

# Dialog

## 说明

通用弹窗的打开和关闭

## 使用

```javascript
//返回 dialog 实例

//title: 标题
//content: 内容
//confirm: 确认按钮文案
//cancel: 取消按钮文案
//confirmCallback: 确认按钮回调
//cancelCallback: 取消按钮回调
//showListener: 弹窗展示后的监听事件
//dismissListener: 弹窗消失后的监听事件
//isCancelable: 点击蒙层能否关闭按钮
//back：点击物理返回键能否关闭Dialog
let dialog = TinyAPI.interact.createDialog({
    title: "标题",
    content: "内容",
    confirm: "确认按钮文案",
    cancel: "取消按钮文案",
    confirmCallback: () => {},
    cancelCallback: () => {},
    showListener: () => {},
    dismissListener: () => {},
    isCancelable,
    back
})

//显示弹窗
dialog.show()
//关闭弹窗
dialog.hide()
```

## 示例

```javascript
let dialog = TinyAPI.interact.createDialog({
    title: "警告",
    content: "这是一个危险的弹窗",
    confirm: "确认",
    cancel: "取消",
    confirmCallback: () => {
    },
    cancelCallback: () => {
    },
    showListener: () => {
    },
    dismissListener: () => {
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

| 属性              | 类型 | 默认值   | 必填  | 说明                 | 取值范围   |
|:----------------|:----|:------|:----|:-------------------|:-------|
| title           | string | -     | 否   | 标题                 |  |
| content         | string | -     | 否   | 内容                 |  |
| confirm         | string | -     | 否   | 确认按钮文案             |  |
| cancel          | string | -     | 否   | 取消按钮文案             |  |
| confirmCallback | function | -     | 否   | 确认按钮回调             |  |
| cancelCallback  | function | -     | 否   | 取消按钮回调             |  |
| showListener    | function | -     | 否   | 弹窗展示后的监听事件         |  |
| dismissListener | function | -     | 否   | 弹窗消失后的监听事件         |  |
| isCancelable    | boolean | true  | 否   | 点击蒙层能否关闭按钮         |  |
| back            | boolean | false | 否   | 点击物理返回键是否让dialog消失 |  |

## tips

弹窗样式参考安卓原生样式，不同安卓版本弹窗样式可能不同。  
之后会支持对 title 部分的自定义 View 之后会支持对蒙层的自定义 之后会支持参数配置的单独方法，并且把 Dialog 的 js 部分封装成 Class
在副屏禁止调用该方法