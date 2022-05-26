---
layout: default
title: Checkbox
nav_order: 5
parent: 基础
grand_parent: 组件
---

# Checkbox

## 说明
复选框是一种特定类型的双状态按钮，可以选中或取消选中。

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("column", {
            style: {
                width: "100%",
                height: "100%",
            },
        },
        TinyDOM.createElement("checkBox", {},"option 1"),
        TinyDOM.createElement("checkBox", {},"option 2"),
        TinyDOM.createElement("checkBox", {},"option 3")
    );
}

let dom = demo()
TinyUI.render(dom);
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| checked | boolean   |   false   |    | 选中状态         | 
| defaultChecked | boolean   |   false   |    | 选中状态默认值         |
| text | string   |      | 'normal', 'bold'   | 文本显示         |
| disabled | boolean   |    false  |    | 禁用响应用户操作         |
| onChange | function   |      |    | 事件监听         | |
| colors | object   |      |    | 详见 colors 说明        | |

## colors
| 属性 | 类型 | 说明  |
| ---- | -------- | ------ |
|checkedColor|string|选中颜色|
|normalColor|string|未选中颜色|