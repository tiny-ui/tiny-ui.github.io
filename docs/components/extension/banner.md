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
            renderItem: (id, index) => {
                var backgroundColor = "red";
                switch (index) {
                    case 0: backgroundColor = "red" 
                        break
                    case 1: backgroundColor = "green"
                        break
                    case 2: backgroundColor = "yellow"
                        break
                }
                
                return TinyDOM.createElement("column", {
                    style: {
                        width: "100%",
                        height: "100%",
                        backgroundColor: backgroundColor
                    }   
                })
            },
            itemCount: 3
        });
}

let dom = createDom()
TinyUI.render(dom);
```

## 参数

| 属性                      | 类型          | 默认值                  | 取值范围                    | 说明               |
|-------------------------|-------------|----------------------|-------------------------|------------------|
| renderItem              | function    |                      |                         | banner item渲染方法  |
| itemCount               | number      | 0                    | 大于0                     | banner 展示数量      |
| autoplay                | boolean     | true                 |                         | 设置是否自动滑动轮播图      | 
| direction               | string      | horizontal           | "vertical","horizontal" | 轮播图滑动方向          |
| onIndexChange           | function    |                      |                         | banner page 改变监听 |
| indicatorProps          | object      | 详见 indicatorProps 参数 |                         |                  |
| allowTouchMove          | bool        | true                 |                         | 是否允许手动滑动         |
| autoplayInterval        | number(int) | 3000                 |                         | 自动轮播间隔           |
| swipeTo                 | number(int) |                      |                         | 滑动到指定item        |
| defaultCurrentItemIndex | number(int) | 0                    |                         | 默认展示的第一个item     |

## indicatorProps 参数

| 属性 | 类型  | 说明  |
| ---- | -------- | ------ |
| dotColor | string | 指示器未选中状态下显示的颜色 |
| activeDotColor | string | 指示器选中状态下显示的颜色 |
| dotSize | number(int) | 指示器未选中状态下显示的大小 |
| activeDotSize | number(int) | 指示器选中状态下显示的大小 |
| spacing | number(int) | 指示器各item的间距 |

