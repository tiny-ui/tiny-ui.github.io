---
layout: default
title: getBySP
nav_order: 5
parent: 存储
grand_parent: API

---

# getBySP
## 说明
指定对应的库名，根据传入的key值，获取对应持久化存储值

## 使用
```javascript
let result = TinyAPI.storage.getBySP(spName, key);
```

## 示例
```javascript
let result = TinyAPI.storage.getBySP("newP", "arg");

console.log("this is value:" + result);
```

## 参数

| 属性名      | 类型     | 属性说明 | 必填  | 默认值 | 取值范围                 |
|:----|:-------|:-----|:-----|:----|:-----------|
| key | string | 库名   | 是 | -   |  |
| key | string | 键名   | 是 | -   |  |

### result参数

| 属性名      | 类型                        | 属性说明    | 必填  | 默认值 | 取值范围                 |
|:----|:--------------------------|:------|:----|:----|:-----------|
| result | string / number / boolean | - | 方法返回结果    | -   |  |
