---
layout: default
title: getParams
nav_order: 4
parent: 导航
grand_parent: API

---

# getParams
## 说明
获取跳转新页面时，A页面传递到B页面上的参数

## 使用
```javascript
let result = TinyAPI.navigation.getParams();
```

## 示例
```javascript
// 跳转新页面（所有选项）
let result = TinyAPI.navigation.getParams();
console.log(result);
```

## 参数

| 属性 | 类型                                  | 默认值 | 必填 | 说明                          | 最低版本支持 |
|:----|:------------------------------------|:------|:-----|:----------------------------|:-----------|
| result | string / integer / boolean / object | - | - | 返回跳转路由时传递的params(只能在当前页面获取) | v0.3.0 |
