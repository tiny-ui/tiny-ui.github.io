---
layout: default
title: TabView
nav_order: 4
parent: 扩展
grand_parent: 组件
---

# TabView

## 说明
Tab 容器

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("column", {
        style: {
            backgroundColor:"green",
            width: "100%",
            height: "100%",
            alignItems: "center",
        }
    },
        TinyDOM.createElement("tabView", {
            style: {
                backgroundColor:"pick",
                width: "100%",
            },
            data:["吃饭","睡觉","洗澡澡"]
        },)
    );
}
TinyUI.render(demo());
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| data | array   |      |    | tab 标题数据         | 
| selected | number   |      |    | 选中指定位置         |
| indicatorFullWidth | boolean   |      |   | 底部指示器是否占整个tab全宽         |
| textColor | object   |      |  {normalColor:"red", selectedColor:"black"}  | tab title 选中状态颜色,以及未选中状态的颜色         |
