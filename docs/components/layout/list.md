---
layout: default
title: List
nav_order: 3
parent: 布局
grand_parent: 组件
---

# List

## 说明
可以让您轻松高效地显示大量数据。您提供数据并定义每个列表项的外观，而 list 会根据需要动态创建元素,list 会回收这些单个的元素。当列表项滚动出屏幕时，list 不会销毁其视图。相反，list 会对屏幕上滚动的新列表项重用该视图。这种重用可以显著提高性能，改善应用响应能力并降低功耗

## 示例
基础列表使用

```javascript
// 创建item视图框架
function onCreateView(itemType) {
    return TinyDOM.createElement("column", {
        style: {
            height: 200,
            width: "100%",
        }
    }, TinyDOM.createElement("text", {
        style: {
            height: 200,
            width: "100%",
        },
        // 这个id十分关键
        id: "tv_text",
    }));
}

// 给 onCreateView 函数创建好的视图框架赋值
function onBindView(data, position, itemType, element) {
    // 通过viewholder 给id为tv_text的控件的text属性赋值.
    element.getElementById("tv_text").setAttribute("text", data);
    if(position%2==0){
        element.getElementById("tv_text").setStyle("backgroundColor", "green");
    }else{
        element.getElementById("tv_text").setStyle("backgroundColor","red");
    }
}

function list() {
    return TinyDOM.createElement("column", {
        style: {
            width: "100%",
            height: "100%",
            alignItems: "center",
        }
    },
        TinyDOM.createElement("list", {
            style: {
                width: "100%",
                height: "100%",
            },
            data: ["1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3", "1", "2", "3"],
            onCreateView: onCreateView,
            onBindView: onBindView,
        })
    );
}

TinyUI.render(list());
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| data | array   |      |    | list渲染业务数据数组.         | 
| orientation | string   |  'vertical'    | 'vertical', 'horizontal' | 设置布局方向 |
| onRefresh | function   |     |   | 触发下拉刷新时调用.         |
| onLoadMore | function   |      |    | 触发上拉加载时调用.         |
| itemType | function   |      |   | 根据传入的index数据获取index对应的item类型,并返回.    |
| onCreateView | function   |      |    | 创建item视图框架         |
| onBindView | function   |     |    | 给onCreateView 创建好的视图框架填充数据         |
