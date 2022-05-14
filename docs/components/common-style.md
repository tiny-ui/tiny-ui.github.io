---
layout: default
title: 通用样式
parent: 组件
nav_order: 1
---

# 通用样式

以下属性在 `style` 属性中设置

| 属性 | 默认值 | 类型 | 取值范围 | 说明| 
|:----|:-------|:------|:-----|:---------------|
| maxWidth |  | number |  | 组件最大宽度 |
| minWidth |  | number |  | 最小宽度 |
| width | auto | number |  | 组件宽度 |
| height | auto | number |  | 组件高度 |
| maxHeight |  | number |  | 最大高度| 
| minHeight |  | number |  | 最小高度| 
| margin | 0 | number |  | 元素外间距| 
| marginTop | 0 | number |  | 元素顶部外间距|
| marginRight | 0 | number |  | 元素右侧外间距|
| marginLeft | 0 | number |  | 元素左侧外间距| 
| marginBottom | 0 | number |  | 元素底部外间距|
| padding |  | number |  | 元素内间距 | 
| paddingTop |  | number |  | 元素顶部内间距| 
| paddingLeft |  | number |  | 元素左侧内间距|
| paddingRight |  | number |  | 元素右侧内间距|
| paddingBottom |  | number |  |元素底部内间距|
| backgroundImage |  | string |  | 网络图片 |
| backgroundColor |  | string(hex 、rgb、色值名称) |  | 元素背景颜色|
| borderStyle |  | string | 'solid', dashed', 'dotted'| 四个边的边框类型|
| borderLeftStyle |  | string | 'solid', dashed', 'dotted' | 左边框类型|
| borderTopStyle |  | string | 'solid', dashed', 'dotted' | 顶部边框类型|
| borderRightStyle |  | string | 'solid', dashed', 'dotted' | 右边框类型| 
| borderBottomStyle |  | string | 'solid', dashed', 'dotted' | 底边框类型|
| borderColor |  | string | 'red', '#ffffff', 'rgb(255,255,255)'| 边框颜色 | 
| borderLeftColor |  | string | 'red', '#ffffff', 'rgb(255,255,255)' | 左边框颜色|
| borderTopColor |  | string | 'red', '#ffffff', 'rgb(255,255,255)' | 顶部边框颜色| 
| borderRightColor |  | string | 'red', '#ffffff', 'rgb(255,255,255)' | 右侧边框颜色|
| borderBottomColor |  | string | 'red', '#ffffff', 'rgb(255,255,255)' | 底部边框颜色|
| borderWidth |  | number |  | 边框宽度| 
| borderLeftWidth |  | number |  | 左侧边框宽度|
| borderTopWidth |  | number |  | 顶部边框宽度| 
| borderRightWidth |  | number |  | 右侧边框宽度| 
| borderBottomWidth |  | number |  | 底部边框宽度| 
| borderRadius |  | number |  | 边框圆角角度| 
| borderTopLeftRadius |  | number |  | 左上角 边框圆角角度| 
| borderTopRightRadius |  | number |  | 右上角 边框圆角角度|
| borderBottomLeftRadius |  | number |  | 左下角 边框圆角角度|
| borderBottomRightRadius |  | number |  | 右下角 边框圆角角度|
| disable |  | boolean |  | 是否响应交互| 
| visibility |  | string |  | 是否显示|


透明度设置示例
```javascript
TinyDOM.createElement("column", {
        id: "container",
        style: {
            width: "200",
            height: "200",
            backgroundColor: "red",
            opacity:"0.1",
        }
    })
```
