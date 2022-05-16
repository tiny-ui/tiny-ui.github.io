---
layout: default
title: Popup
nav_order: 4
parent: 交互
grand_parent: API

---

# Popup

## 说明

一个完全自定义的 Popup (弹出窗口)，内容完全由使用者定义。

## 使用

```javascript
//content: Popup 的展示内容
let popup = TinyAPI.interact.createPopup({
    content: () => {},
})

//anchor：Popup 所要固定的控件的id
popup.showAsDropDown("anchor")

//anchor: Popup 所要固定的控件的id
//xOff: 与固定控件的横向偏移量，正数向右，负数向左
//yOff: 与固定控件的纵向偏移量，正数向下，负数向上
popup.showAsDropDown({
    anchorId: "id",
    xOff: 0,
    yOff: 0
})

//隐藏 Popup
popup.hide()
```

## 示例

```javascript
let popup = TinyAPI.interact.createPopup({
    content: () => {
        return TinyDOM.createElement(
            "text",
            {},
            "这是一个自定义 Popup")
    }
})

//popup.showAsDropDown("container")

popup.showAsDropDown({
    anchorId: "container",
    xOff: 0,
    yOff: 0})

setTimeout(() => {
    popup.hide()
}, 3000)

```

## 参数

| 属性 | 类型 | 默认值  | 必填  | 说明          | 最低版本支持 |
|:----|:----|:-----|:----|:------------|:-----------|
| content | function | -    | 否   | popup 的展示内容 | v0.3.0 |

### showAsDropDown

| 属性 | 类型 | 默认值  | 必填  | 说明                    | 最低版本支持 |
|:----|:----|:-----|:----|:----------------------|:-----------|
| anchorId | string | -    | 否   | popup 所要固定的控件的 id     | v0.3.0 |
| xOff | int | -    | 否   | 与固定控件的横向偏移量，正数向右，负数向左 | v0.3.0 |
| yOff | int | -    | 否   | 与固定控件的纵向偏移量，正数向下，负数向上 | v0.3.0 |


## tips

showAsDropDown 方法和 hide 方法一一对应，如果多次调用 showAsDropDown 方法会多次展示 Popup。  
展示方法暂时支持 showAsDropDown，之后 showAtLocation，  
之后以Class的形式封装 Popup。