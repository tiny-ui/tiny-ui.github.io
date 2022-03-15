---
layout: default
title: removeStorage
nav_order: 3
parent: 存储
grand_parent: API

---

# removeStorage
## 说明
根据传入的key值，移除对应缓存值

## 使用
```javascript
TinyAPI.cache.removeStorage(key);
```

## 示例
```javascript
TinyAPI.cahce.removeStorage("arg");
```
    
## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| key | String | - | 是 | 键名 | v0.3.0 |
