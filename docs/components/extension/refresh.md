---
layout: default
title: Refresh
nav_order: 4
parent: 扩展
grand_parent: 组件
---

# refresh

## 说明

支持下拉刷新和上拉加载控件

## 示例

```javascript
function app() {
    return TinyDOM.createElement("refresh", {
        refreshEnable: true,
        loadMoreEnable: true,
        refreshListener: (id) => {
            
        },
        loadMoreListener: (id) => {
            
        }
    }, TinyDOM.createElement("column", {
        style: {
            width: "100%",
            height: "100%",
            backgroundColor: "red"
        }
    }))
}

TinyUI.render(app())
```

## 参数

| 属性名  |    类型    | 默认值  |     说明     |  示例  |
|:----:|:--------:|:----:|:----------:|:----:|
| refreshEnable  | boolean  | true | 是否开启下拉刷新能力 |   |
| loadMoreEnable  | boolean  | true | 是否开启上拉加载能力 |   |
|        refreshListener         | function |      |   下拉刷新回调   |   |
|            loadMoreListener                    | function |      |   上拉加载回调   |   |