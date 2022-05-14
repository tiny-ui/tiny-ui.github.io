---
layout: default
title: ViewPage
nav_order: 5
parent: 扩展
grand_parent: 组件
---

# ViewPage

## 说明
可滑动 view 容器

## 示例
```javascript
function pageView() {
    return TinyDOM.createElement("column", {
        style: {
            width: "100%",
            height: "100%",
            alignItems: "center",
        }
    },
        TinyDOM.createElement("pageView", {
            style: {
                width: "100%",
                height: "100%",
            },
        },
        TinyDOM.createElement("column", {
            id:"page1",
            style: {
                backgroundColor:"red",
                width: "100%",
                height: "100%",
                alignItems: "center",
            }
        }),
        TinyDOM.createElement("column", {
            id:"page1",
            style: {
                backgroundColor:"blue",
                width: "100%",
                height: "100%",
                alignItems: "center",
            }
        }),
        TinyDOM.createElement("column", {
            id:"page1",
            style: {
                backgroundColor:"gray",
                width: "100%",
                height: "100%",
                alignItems: "center",
            }
        })    
        )
    );
}
TinyUI.render(pageView());
```

## 参数

