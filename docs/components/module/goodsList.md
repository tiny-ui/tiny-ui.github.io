---
layout: default
title: goodsList
nav_order: 1
parent: 模板
grand_parent: 组件
---

# GoodsList

## 描述

用于商米特定的商品列表

## 示例

```javascript
var app = () => {
    return TinyDOM.createElement("goodsList", {
        style: {},
        data: [{
            src: "https://t7.baidu.com/it/u=1595072465,3644073269&fm=193&f=GIF",
            name: "a",
            spec: "1",
            price: "2988",
            value: 6
        }]
    })
}
``` 

## 参数

| 属性名  |    类型    | 默认值  |    说明     |  示例  |
|:----:|:--------:|:----:|:---------:|:----:|
| data | JSArray  |   | 商品列表数据列表  |   |
|  onValueAdd    | function |   | 点击增加按钮的回调 |   |
|     onValueDeclare           | function |   | 点击减少按钮的回调 |   |
|         onItemClick                     | function |   |  点击商品的回调  |   |

### data结构

| 属性名 |   类型   |  默认值  |   说明    |  示例  |
|:---:|:------:|:-----:|:-------:|:----:|
| src | string |       | 商品图片url |   |
|  name   | string |       |  商品名称   |   |
|    spec     | string |       |  商品详情   |   |
|     price        | string |       |  商品价格   |   |
|      value            |  int   | 大于等于0 |  商品数量   |   |