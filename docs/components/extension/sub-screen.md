---
layout: default
title: SubScreen
nav_order: 4
parent: 扩展
grand_parent: 组件
---

# SubScreen

## 说明

支持子组件在副屏显示

## 示例

```javascript
var app = () => {
    return TinyDOM.createElement("subScreen", {
            id: "subScreen",
            independent: true,
        }, TinyDOM.createElement("text", {}, "hello sunmi 1111111"))
}
TinyUI.render(app());
```

## 参数

|     属性     |   类型    |  默认值  | 取值范围 |        说明        |
|:----------:|:-------:|:-----:|:----:|:----------------:|
| independent | boolean | false |      | 主屏页面返回桌面后，副屏仍然显示 |

## 提示
SubScreen 的子组件支持Flex布局