---
layout: default
title: InputText
nav_order: 4
parent: 基础
grand_parent: 组件
---

# InputText

## 说明
文本输入组件。

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
    TinyDOM.createElement("inputText", {
        style: {
            backgroundColor:"pink",
            width: "100%",
            height:"6%"
        },
    })
));
```

## 参数

| 属性            | 类型       | 默认值 | 取值范围 | 说明           |
|---------------|----------| ------ | ---- |--------------|
| text          | string   |      |    | 文本内容         |
| color         | string   |      | 'rad', '#ffffff', 'rgb(255,255,255)'   | 文本颜色         |
| fontWeight    | string   | 'normal'     | 'normal', 'bold'   | 字体的粗细程度      |
| fontSize      | number   |      |    | 字体的大小        |
| textAlign     | string   | left     | 'left', 'top', 'right', 'bottom', 'center', 'centerVertical', 'centerHorizontal'   | 行内内容的对齐方式    |
| strikeTrue    | boolean  |   false   |    | 中划线          |
| onChange      | function |      |    | 输入框事件        |
| value         | string   |   false   |    | 输入框内容        |
| maxLength     | number   |      |    | 输入文字最大个数     |
| maxLines      | number   |      |    | 输入文字最大行数     |
| placeholder   | string   |   false   |    | 输入文本为空时显示的文本 |
| letterSpacing | number   |      | 字间距（标准字体大小的倍数，单位是em）   | 字体的大小        |
| lineSpacing   | number   |    1  | 是   | 行间距          |
| inputType     | string   |      | "number","numberPassword","phone","text","textEmailAddress","textPassword","textVisiblePassword"  | 输入文本类型       |
