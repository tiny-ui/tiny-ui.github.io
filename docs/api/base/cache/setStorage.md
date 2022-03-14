---
layout: default
title: setStorage
nav_order: 1
parent: 缓存
grand_parent: API

---

# setStorage
## 说明
根据传入的key值和value值，保存在缓存中。（存在于整个应用生命周期中，即关闭 -> 重新打开应用后，缓存依然存在）

## 使用
```javascript
TinyAPI.cache.setStorage(key, value);
```

## 示例
```javascript
TinyAPI.cahce.setStorage("arg", "test123")
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| key | String | - | 是 | 键名 | v0.3.0 |
| value | String / Integer / Boolean | - | 是 | 保存到缓存中到数据 | v0.3.0 |
