---
layout: default
title: getParams
nav_order: 4
parent: 路由
grand_parent: API

---

# getParams
## 说明
获取跳转新页面时，A页面传递到B页面上的参数

## 使用
```javascript
let result = TinyAPI.router.getParams();
```

## 示例
```javascript
// 跳转新页面（所有选项）
let result = TinyAPI.router.getParams();
console.log(JSON.stringify(result));
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| result | String / Integer / Boolean / Object | - | - | 返回跳转路由时传递的params | v0.3.0 |
