---
layout: default
title: get
nav_order: 2
parent: 缓存
grand_parent: API

---

# get
## 说明
根据传入的key值，获取对应缓存值

## 示例
```javascript
let result = TinyAPI.cache.get("arg");

console.log("this is value:" + result);
```

## 入参

| 属性名 | 类型     | 属性说明 | 必填  | 默认值     | 取值范围                 |
|:----|:-------|:-----|:----|:--------|:---------------------|
| key | string | 键名   | 是   |  |  |

### `result`参数

| 属性 | 类型                         | 属性说明 | 必填  | 默认值    | 取值范围   |
|:----|:---------------------------|:-----|:----|:-------|:-------|
| result | string / integer / boolean | 方法返回结果     |     |  |  |
