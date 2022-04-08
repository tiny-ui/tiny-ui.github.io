---
layout: default
title: remove
nav_order: 3
parent: 存储
grand_parent: API

---

# remove
## 说明
根据传入的key值，移除对应缓存值

## 使用
```javascript
TinyAPI.storage.remove(key);
```

## 示例
```javascript
TinyAPI.storage.remove("arg");
```
    
## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| key | String | - | 是 | 键名 | v0.3.0 |
