---
layout: default
title: RadioGroup
nav_order: 4
parent: 布局
grand_parent: 组件
---

# RadioGroup

## 说明
用于为一组单选按钮创建多重排除范围。选中属于单选组的一个单选按钮会取消选中同一组中任何先前选中的单选按钮。

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("radioGroup", {
            style: {
                width: "100%",
                height: "100%",
            }
        },
        TinyDOM.createElement("radioButton", {
        }, "Hello word!"),
        TinyDOM.createElement("radioButton", {
            disabled:true,
            defaultChecked:true
        }, "Hello max!"),
        TinyDOM.createElement("radioButton", {
        }, "Hello TinyUI!")
    );
}

TinyUI.render(demo());
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| orientation | string   |   vertical   | "vertical", "horizontal"   | 选中状态         | 
| onCheckedChangeListener | function   |      |    | 事件监听         |
