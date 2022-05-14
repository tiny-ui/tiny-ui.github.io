---
layout: default
title: RadioButton
nav_order: 6
parent: 基础
grand_parent: 组件
---

# RadioButton

## 说明
单选按钮是一个有两种状态的按钮，可以选中或取消选中。当单选按钮未选中时，用户可以按下或单击它来选中它。

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("column", {
            style: {
                width: "100%",
                height: "100%",
            }
        },
        TinyDOM.createElement("radioButton", {}, "Hello word!")
    );
}
TinyUI.render(demo());
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| checked | boolean   |   false   |    | 选中状态         | 
| defaultChecked | boolean   |   false   |    | 选中状态默认值         |
| text | string   |      | 'normal', 'bold'   | 文本显示         |
| disabled | boolean   |    false  |    | 禁用响应用户操作         |
| onChange | function   |      |    | 事件监听         | |
