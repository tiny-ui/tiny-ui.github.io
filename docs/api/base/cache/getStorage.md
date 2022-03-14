---
layout: default
title: getStorage
nav_order: 2
parent: 缓存
grand_parent: API

---

# getStorage
## 说明
根据传入的key值，获取对应缓存值

## 使用
```javascript
let result = TinyAPI.cache.getStorage(key);
```

## 示例
```javascript
let result = TinyAPI.cahce.getStorage("arg");

console.log("this is value:" + result);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| key | String | - | 是 | 键名 | v0.3.0 |

### result参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| result | String / Integer / Boolean | - | 是 | 方法返回结果 | v0.3.0 |
