---
layout: default
title: row
nav_order: 4
parent: 布局
grand_parent: 组件
has_children: true
---
# row

## 描述

基于flex 横向布局的容器组件，内部可以放入其他子组件。

## 使用方法

```javascript
TinyDOM.createElement(
    "row", {},
    TinyDOM.createElement(
        "text", {}, "hello tiny ui"))
```

## 样式

|      属性名       |      类型       |    默认值     |                   说明                    |                                       示例                                       |
|:--------------:|:-------------:|:----------:|:---------------------------------------:|:------------------------------------------------------------------------------:|
| justifyContent |    string     | flex-start |              主轴方向上的子控件排列方式              | 'flex-start'，'flex-end'，'center'，'space-between'，'space-around'，'space-evenly' |
|    flexWrap    |    string     |  no-wrap   | 指定子组件单行显示还是多行显示。如果允许换行，这个属性允许你控制行的堆叠方向。 |                         'nowrap'，'wrap'，'wrap-reverse'                         |
|   alignItems   |    string     |  stretch   |             交叉轴方向上的子控件的对齐方式             |             'flex-start'，'flex-end'，'center'，'baseline'，'stretch'              |
|  alignContent  |    string     |  stretch   |         多主轴情况下，交叉轴方向上的子控件的排列方式          |    flex-start'，'flex-end'，'center'，'space-between'，'space-around'，'stretch'    |
|    flexGrow    |    number     |     0      |             子控件占有父容器剩余空间的权重             |                                                                                |
|   flexShrink   |    number     |     1      |            父容器空间不足时，子控件的收缩权重            |                                                                                |
|   flexBasis    | number、string |    auto    |          子控件在进行拉伸和收缩计算前的基础尺寸           |                                                                                |
|   alignSelf    |    string     |    auto    |              子控件在交叉轴上的对齐方式              |             'flex-start','flex-end','center','baseline','stretch'              |
|    overFlow    |    string     |  visible   |             子控件超出父容器部分是否显示              |                               'hidden','visible'                               |
|    position    |    string     |  relative  |       布局方式，分相对布局和绝对布局，相对布局即flex布局       |                             'relative','absolute'                              |

## 示例

```javascript
TinyDom.createElement("row", {
    id: "row",
    style: {
        justifyContent: 'flex-start',
        flexWrap: 'no-wrap',
        alignItem: 'stretch',
        alignContent: 'stretch',
        flexGrow: 0,
        flexShrink: 1,
        flexBasis: 'auto',
        alignSelf: 'auto',
        overflow: 'visible',
        position: 'relative'
    }   
});

```

## 提示
TinyUI的flex布局基于YogaLayout，默认样式和YogaLayout网站中的PlayGround保持一致，如果对自己布局有异议的话可以参考
https://yogalayout.com/playground