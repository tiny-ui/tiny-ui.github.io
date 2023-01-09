---
layout: default
title: clearBySP
nav_order: 8
parent: 存储
grand_parent: API

---

# clearBySP
## 说明
指定对应的库名，清空所有持久化存储

## 使用
```javascript
TinyAPI.storage.clearBySP(spName);
```

## 示例
```javascript
TinyAPI.storage.clearBySP("newP");
```

## 参数

| 属性名    | 类型                        | 属性说明 | 必填  | 默认值 | 取值范围                 |
|:-------|:--------------------------|:-----|:-----|:----|:-----------|
| spName | string                    | 库名   | 是 | -   |  |