---
layout: default 
title: Row 
nav_order: 1 
parent: 布局 
grand_parent: 组件
---

# Row

## 说明

基于 Flex 横向布局的容器组件，内部可以放入其他子组件。

```
提示: TinyUI 布局基于 yoga，可以通过官网提供的 [playground](https://yogalayout.com/playground) 来预览效果。
```

## 使用

```javascript
TinyDOM.createElement("row", {
    id: "row",
    style: {
        flex: 1,
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

## 示例

```javascript
TinyDOM.createElement(
    "row", {},
    TinyDOM.createElement(
        "text", {}, "hello tiny ui"))
```

## 参数

|      属性名       |      类型       |    默认值     |                            说明                            |                                       示例                                       |
|:--------------:|:-------------:|:----------:|:--------------------------------------------------------:|:------------------------------------------------------------------------------:|
|      flex      | number、string |     1      | flex 属性决定元素在主轴上如何填满可用区域。整个区域会根据每个元素设置的 flex 属性值被分割成多个部分。 |                                       无                                        |
| justifyContent |    string     | flex-start |                      主轴方向上的子控件排列方式                       | 'flex-start'，'flex-end'，'center'，'space-between'，'space-around'，'space-evenly' |
|    flexWrap    |    string     |  no-wrap   |         指定子组件单行显示还是多行显示。如果允许换行，这个属性允许你控制行的堆叠方向。          |                         'no-wrap'，'wrap'，'wrap-reverse'                         |
|   alignItems   |    string     |  stretch   |                     交叉轴方向上的子控件的对齐方式                      |             'flex-start'，'flex-end'，'center'，'baseline'，'stretch'              |
|  alignContent  |    string     |  stretch   |                  多主轴情况下，交叉轴方向上的子控件的排列方式                  |    flex-start'，'flex-end'，'center'，'space-between'，'space-around'，'stretch'    |
|    flexGrow    |    number     |     0      |                     子控件占有父容器剩余空间的权重                      |                                       无                                        |
|   flexShrink   |    number     |     1      |                    父容器空间不足时，子控件的收缩权重                     |                                       无                                        |
|   flexBasis    | number、string |    auto    |                   子控件在进行拉伸和收缩计算前的基础尺寸                    |                                       无                                        |
|   alignSelf    |    string     |    auto    |                      子控件在交叉轴上的对齐方式                       |             'flex-start','flex-end','center','baseline','stretch'              |
|    overflow    |    string     |  visible   |                      子控件超出父容器部分是否显示                      |                               'hidden','visible'                               |
|    position    |    string     |  relative  |              布局方式，分相对布局和绝对布局，相对布局即 flex 布局               |                             'relative','absolute'                              |
