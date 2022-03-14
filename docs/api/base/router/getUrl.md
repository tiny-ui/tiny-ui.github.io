---
layout: default
title: getUrl
nav_order: 3
parent: 路由
grand_parent: API

---

# getUrl
## 说明
获取当前显示页面的路径

## 使用
```javascript
let path = TinyAPI.router.getUrl();
```

## 示例
```javascript
// 跳转新页面（所有选项）
let path = TinyAPI.router.getUrl();
console.log(path);
```
---
result示例
{: .text-red-000 }
```text
page://com.sunmi.demo/pages/router.js
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| path | String | - | - | 方法返回结果 | v0.3.0 |
