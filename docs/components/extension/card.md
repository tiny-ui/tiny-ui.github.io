---
layout: default
title: Card
nav_order: 2
parent: 扩展
grand_parent: 组件
---

# Card

## 说明
水平容器视图，内部可以放入其他子视图。

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("column", {
        style: {
            backgroundColor: "green",
            width: "100%",
            height: "100%",
            alignItems: "center",
        }
    },
        TinyDOM.createElement("card", {
            style: {
                marginTop: "10%",
                width: "50%",
                height: "50%",
            },
                
        })
    );
}
TinyUI.render(demo());
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| elevation | number   |      |    | 阴影范围         | 
| cornerRadius | number   |      |    | 四角圆角         |
