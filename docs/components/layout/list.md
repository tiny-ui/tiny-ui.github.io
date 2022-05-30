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
            renderItem: (id, index) => { // id为item父布局的id，index为目前所在的item的位置
                return TinyDOM.createElement("text", {}, "hello sunmi position: " + index)
            },
            itemCount: 100
        })
    );
}

TinyUI.render(list());
```

## 参数

| 属性 | 类型       | 默认值 | 取值范围 | 说明                                |
| ---- |----------| ------ | ---- |-----------------------------------|
| renderItem | function |      |    | 列表渲染方法                            |
| itemCount | number   |      |    | 列表item数量                          |
