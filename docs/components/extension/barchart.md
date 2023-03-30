---
layout: default
title: barchart
nav_order: 1
parent: 扩展
grand_parent: 组件
---

# BarChart

## 说明
柱状图

## 使用
```javascript
function createDom() {
    return TinyDOM.createElement("column", {
        style: {
            width: "100%",
            height: "100%",
        }
    },
    TinyDOM.createElement("barchart",
    {
        dataSource:{
            "desc": {
                "xTitle": "月份",
                "yTitle": "营业额(元)",
                "xKey": "date",
                "yKey": "money"
                },
            "data": [
                {
                    "date": "1月",
                    "money": "10000"
                },
                {
                    "date": "2月",
                    "money": "30000"
                },
                {
                    "date": "3月",
                    "money": "20000"
                },
                {
                    "date": "4月",
                    "money": "25000"
                },
                {
                    "date": "5月",
                    "money": "53000"
                },
                {
                    "date": "6月",
                    "money": "40000"
                },
                {
                    "date": "7月",
                    "money": "50000"
                }
            ]
        },
            style: {
                    width: "100%",
                    height: "500",
            }
        })
    )
}

let dom = createDom()
TinyUI.render(dom);
```

## 参数

| 属性         | 类型         | 是否必填 | 说明                              |
| ---------- | ------------- | ---- | ------------------------------- |
| data       | object        | 是    | 柱状图数据整体                         |
| desc       | object        | 是    | 柱状图数据描述                         |
| xTitle     | string        | 否    | 展示在悬浮弹窗X值之后                     |
| yTitle     | string        | 否    | 展示在悬浮弹窗Y值之后                     |
| xKey       | string        | 是    | data数组中X轴的key值                  |
| yKey       | string        | 是    | data数组中Y轴的key值                  |
| dataSource | list\<object> | 是    | 数据列表,object里面的key必须与xKey、yKey对应 |

