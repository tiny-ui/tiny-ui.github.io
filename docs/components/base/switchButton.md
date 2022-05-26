---
layout: default
title: SwitchButton
nav_order: 6
parent: 基础
grand_parent: 组件
---

# switchButton

## 说明
    多选按钮是一个有两种状态的按钮，可以选中或取消选中。

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("column", {
            style: {
                width: "100%",
                height: "100%",
            }
        },
        TinyDOM.createElement("switchButton", {}, "Hello word!")
    );
}
TinyUI.render(demo());
```

## Attribute

| 属性 | 类型 | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| checked | boolean | false |    | 选中状态 | 
| defaultChecked | boolean | false | | 选中状态默认值 |
| text | string | |  | 文本显示 |
| disabled | boolean   |    false  |    | 禁用响应用户操作         |
| onChange | function   |      |    | 事件监听         | |
| colors | object   | |    | 详见 colors 说明        | |
| checkedText | string | | | | 选中时的文本|
| uncheckedText| string | | | | 未选中时的文本|

## colors

| 属性 | 类型 | 说明 |
| ---- | -------- | ------ |
|checkedColor|string|选中颜色|
|normalColor|string|未选中颜色|
|checkedTrackColor|string|选中时的滑轨颜色|
|normalColorTrackColor|string|未选中时的滑轨颜色|