---
layout: default
title: 通用样式
parent: 组件
nav_order: 1
---

| 属性 | 默认值 | 类型/可选值 | 取值范围 | 说明| 最低版本支持   |是否支持 |
|:----|:-------|:------|:-----|:---------------|:---------|---------|
| maxWidth |  | number | - | 组件最大宽度| v0.3.0 |✅|
| minWidth |  | number | - | 最小宽度 | v0.3.0 |✅|
| width | auto | number | - | 组件宽度 | v0.3.0 |✅|
| height | auto | number | - | 组件高度 | v0.3.0 |✅|
| maxHeight |  | number | - | 最大高度| v0.3.0 |✅|
| minHeight |  | number | - | 最小高度| v0.3.0 |✅|
| margin | 0 | number | - | 元素外间距| v0.3.0 |✅|
| marginTop | 0 | number | - | 元素顶部外间距| v0.3.0 |✅|
| marginRight | 0 | number | - | 元素右侧外间距| v0.3.0 |✅|
| marginLeft | 0 | number | - | 元素左侧外间距| v0.3.0 |✅|
| marginBottom | 0 | number | - | 元素底部外间距| v0.3.0 |✅|
| padding |  | number | - | 元素内间距 | v0.3.0 |✅|
| paddingTop |  | number | - | 元素顶部内间距| v0.3.0 |✅|
| paddingLeft |  | number | - | 元素左侧内间距| v0.3.0 |✅|
| paddingRight |  | number | - | 元素右侧内间距| v0.3.0 |✅|
| paddingBottom |  | number | - |元素底部内间距| v0.3.0 |✅|
| backgroundImage |  | string | - | 网络图片 | v0.3.0 |✅|
| backgroundColor |  | string(hex 、rgb、色值名称) | - | 元素背景颜色| v0.3.0 |✅|
| borderStyle |  | string | 'solid', dashed', 'dotted'| 四个边的边框类型| v0.3.0 |✅|
| borderLeftStyle |  | string | 'solid', dashed', 'dotted' | 左边框类型| v0.3.0 |✅|
| borderTopStyle |  | string | 'solid', dashed', 'dotted' | 顶部边框类型| v0.3.0 |✅|
| borderRightStyle |  | string | 'solid', dashed', 'dotted' | 右边框类型| v0.3.0 |✅|
| borderBottomStyle |  | string | 'solid', dashed', 'dotted' | 底边框类型| v0.3.0 |✅|
| borderColor |  | string | 'red'|'#ffffff', 'rgb(255,255,255)'| 边框颜色| v0.3.0 |✅|
| borderLeftColor |  | string | 'red'|'#ffffff', 'rgb(255,255,255)' | 左边框颜色| v0.3.0 |✅|
| borderTopColor |  | string | 'red'|'#ffffff', 'rgb(255,255,255)' | 顶部边框颜色| v0.3.0 |✅|
| borderRightColor |  | string | 'red'|'#ffffff', 'rgb(255,255,255)' | 右侧边框颜色| v0.3.0 |✅|
| borderBottomColor |  | string | 'red'|'#ffffff', 'rgb(255,255,255)' | 底部边框颜色| v0.3.0 |✅|
| borderWidth |  | number | - | 边框宽度| v0.3.0 |✅|
| borderLeftWidth |  | number | - | 左侧边框宽度| v0.3.0 |✅|
| borderTopWidth |  | number | - | 顶部边框宽度| v0.3.0 |✅|
| borderRightWidth |  | number | - | 右侧边框宽度| v0.3.0 |✅|
| borderBottomWidth |  | number | - | 底部边框宽度| v0.3.0 |✅|
| borderRadius |  | number | - | 边框圆角角度| v0.3.0 |✅|
| borderTopLeftRadius |  | number | - | 左上角 边框圆角角度| v0.3.0 |✅|
| borderTopRightRadius |  | number | - | 右上角 边框圆角角度| v0.3.0 |✅|
| borderBottomLeftRadius |  | number | - | 左下角 边框圆角角度| v0.3.0 |✅|
| borderBottomRightRadius |  | number | - | 右下角 边框圆角角度| v0.3.0 |✅|
| disable |  | boolean | - | 是否响应交互| v0.3.0 |✅|
| visibility |  | string | - | 是否显示| v0.3.0 |✅|


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
