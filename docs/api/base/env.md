---
layout: default
title: env
nav_order: 1
parent: 基础
grand_parent: API
---

# env
## 说明
获取手机设备的环境变量数据

## 使用
```javascript
let result = TinyAPI.base.env();
```

## 示例
```javascript
let result = TinyAPI.base.env();

console.log(result); // debug, release
```

## 参数

| 属性 | 类型     | 默认值 | 必填 | 说明             | 最低版本支持   |
|:----|:-------|:------|:-----|:---------------|:---------|
| result | String | - | - | 方法返回结果(debug | release) | v0.3.0 |