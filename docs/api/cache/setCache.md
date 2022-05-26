---
layout: default
title: set
nav_order: 1
parent: 缓存
grand_parent: API

---

# set
## 说明
根据传入的key值和value值，保存在缓存中。（app关闭后即清空）

## 示例
```javascript
TinyAPI.cache.set("arg", "test123")
```

## 入参

| 属性 | 类型                         | 属性说明  | 必填 | 默认值       | 取值范围   |
|:----|:---------------------------|:------|:-----|:----------|:-------|
| key | string                     | 键名    | 是 |         |  |
| value | string / integer / boolean | 保存到缓存中到数据      | 是 |  |  |
