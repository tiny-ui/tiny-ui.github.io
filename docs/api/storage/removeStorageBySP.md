---
layout: default
title: removeBySP
nav_order: 7
parent: 存储
grand_parent: API

---

# removeBySP
## 说明
指定对应的库名，根据传入的key值，移除对应持久化存储值

## 使用
```javascript
TinyAPI.storage.removeBySP(spName, key);
```

## 示例
```javascript
TinyAPI.storage.removeBySP("newP", "arg");
```

## 参数

| 属性名    | 类型                        | 属性说明 | 必填  | 默认值 | 取值范围                 |
|:-------|:--------------------------|:-----|:-----|:----|:-----------|
| spName | string                    | 库名   | 是 | -   |  |
| key    | string                    | 键名   | 是 | -   |  |
