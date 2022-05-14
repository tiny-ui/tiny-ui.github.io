---
layout: default
title: Banner
nav_order: 1
parent: 扩展
grand_parent: 组件
---

# Banner

## 说明
轮播图

## 使用
```javascript
function createDom() {
    return TinyDOM.createElement("banner", {
            style: {
                width: "100%",
                height: "30%",
            },
        },
        TinyDOM.createElement("column", {
            style: {
                backgroundColor: "red"
            }
        }),
        TinyDOM.createElement("column", {
            style: {
                backgroundColor: "green"
            }
        }),
        TinyDOM.createElement("column", {
            style: {
                backgroundColor: "yellow"
            }
        }),
    );
}

let dom = createDom()
TinyUI.render(dom);
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| autoplay | boolean   |   true   |    | 设置是否自动滑动轮播图         | 
| direction | string   |   horizontal   |  "vertical","horizontal"  | 轮播图滑动方向         |
| onIndexChange | function   |      |   | banner page 改变监听         |
| indicatorProps | object   |    详见 indicatorProps 示例  |    |          |
