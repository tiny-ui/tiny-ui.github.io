---
layout: default
title: set
nav_order: 1
parent: 存储
grand_parent: API

---

# set
## 说明
根据传入的key值和value值，保存在持久化存储中。（存在于整个app生命周期中，即关闭 -> 重新打开app后，存储依然存在）

## 使用
```javascript
TinyAPI.storage.set(key, value);
```

## 示例
```javascript
TinyAPI.storage.set("arg", "test123")
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明        | 最低版本支持 |
|:----|:----|:------|:-----|:----------|:-----------|
| key | String | - | 是 | 键名        | v0.3.0 |
| value | String / Integer / Boolean | - | 是 | 保存到存储中到数据 | v0.3.0 |
