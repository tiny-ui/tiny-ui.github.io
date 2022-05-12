---
layout: default
title: Icon
nav_order: 2
parent: 基础
grand_parent: 组件
has_children: true
---

# Icon

## 说明
icon 组件是一个可以显示图标的组件。

## 示例
```javascript
TinyDOM.createElement('icon', {
    name: 'ico_add',
    size: 50,
    color: 'red'
});
```

## 参数
以下为 props 属性说明，支持通用 style 和事件属性

| 属性 | 类型     | 默认值 | 必填 | 说明             | 最低版本支持   |
|:----|:-------|:------|:-----|:---------------|:---------|
| name | string | - | - | icon 名称，必须存在 font 文件中 | v0.3.0 |
| size | number | - | - | icon 大小 | v0.3.0 |
| color | string | - | - | icon 颜色 | v0.3.0 |
