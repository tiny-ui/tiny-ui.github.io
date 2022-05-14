---
layout: default
title: Button
nav_order: 2
parent: 基础
grand_parent: 组件
---

# Button

## 说明
按钮控件

## 示例
```javascript
TinyUI.render(TinyDOM.createElement(
    "column", {
    style: {
        backgroundColor:"black",
        width: "100%",
        height: "100%"
    }
},
    TinyDOM.createElement("button", {
        style: {
            width: "100%",
            height:"6%",
        },
    },"hello word")
));
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| text | string   |      |    | 文本内容         |
| color | string   |      | 'rad', '#ffffff', 'rgb(255,255,255)'   | 文本颜色         |
| fontWeight | string   | 'normal'     | 'normal', 'bold'   | 字体的粗细程度         |
| fontSize | number   |      |    | 字体的大小         |
| textAlign | string   | left     | 'left', 'top', 'right', 'bottom', 'center', 'centerVertical', 'centerHorizontal'   | 行内内容的对齐方式         |
| maxLines | number   |      |    | 行数限制         |
| strikeTrue | boolean   |   false   |    | 中划线         |
| letterSpacing | number   |      | 字间距（标准字体大小的倍数，单位是em）   | 字体的大小         |
| lineSpacing | number   |    1  | 是   | 行间距         |
