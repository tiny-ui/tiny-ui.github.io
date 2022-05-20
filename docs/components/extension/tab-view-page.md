---
layout: default
title: TabViewPage
nav_order: 6
parent: 扩展
grand_parent: 组件
---

# TabViewPage

## 说明
TabView 和 ViewPage 联动布局组件

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
        TinyDOM.createElement("TabPageView", {
            style: {
                width: "100%",
                height: "100%",
            },
        },
            TinyDOM.createElement("tabView", {
                style: {
                    backgroundColor: "pick",
                    width: "100%",
                },
                data: ["吃饭", "睡觉", "洗澡澡"]
            }),
            TinyDOM.createElement("pageView", {
                style: {
                    width: "100%",
                    height: "100%",
                },
            },
                TinyDOM.createElement("column", {
                    id: "page1",
                    style: {
                        backgroundColor: "red",
                        width: "100%",
                        height: "100%",
                        alignItems: "center",
                    }
                }),
                TinyDOM.createElement("column", {
                    id: "page1",
                    style: {
                        backgroundColor: "blue",
                        width: "100%",
                        height: "100%",
                        alignItems: "center",
                    }
                }),
                TinyDOM.createElement("column", {
                    id: "page1",
                    style: {
                        backgroundColor: "gray",
                        width: "100%",
                        height: "100%",
                        alignItems: "center",
                    }
                })
            )
        )
    );
}
TinyUI.render(demo());
```

## 参数
