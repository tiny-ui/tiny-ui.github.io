---
layout: default
title: getUri
nav_order: 3
parent: 导航
grand_parent: API

---

# getUri
## 说明
获取当前显示页面的路径

## 使用
```javascript
let path = TinyAPI.navigation.getUri();
```

## 示例
```javascript
// 跳转新页面（所有选项）
let path = TinyAPI.navigation.getUri();
console.log(path);
```
---
result示例
{: .text-red-000 }
```text
assets://com.sunmi.demo/pages/router.js
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明                  | 最低版本支持 |
|:----|:----|:------|:-----|:--------------------|:-----------|
| path | String | - | - | 当前js文件路径（只能在当前页面获取） | v0.3.0 |
