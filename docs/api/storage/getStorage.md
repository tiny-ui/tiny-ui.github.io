---
layout: default
title: get
nav_order: 2
parent: 存储
grand_parent: API

---

# get
## 说明
根据传入的key值，获取对应持久化存储值

## 使用
```javascript
let result = TinyAPI.storage.get(key);
```

## 示例
```javascript
let result = TinyAPI.storage.get("arg");

console.log("this is value:" + result);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| key | String | - | 是 | 键名 | v0.3.0 |

### result参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| result | String / Integer / Boolean | - | 是 | 方法返回结果 | v0.3.0 |
