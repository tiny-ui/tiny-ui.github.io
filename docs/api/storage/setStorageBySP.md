---
layout: default
title: setBySP
nav_order: 6
parent: 存储
grand_parent: API

---

# setBySP
## 说明
指定对应的库名，根据传入的key值和value值，保存在持久化存储中。（存在于整个app生命周期中，即关闭 -> 重新打开app后，存储依然存在）

## 使用
```javascript
TinyAPI.storage.setBySP(spName, key, value);
```

## 示例
```javascript
TinyAPI.storage.setBySP("newP", "arg", "products data");
```

## 参数

| 属性名    | 类型                        | 属性说明 | 必填  | 默认值 | 取值范围                 |
|:-------|:--------------------------|:-----|:-----|:----|:-----------|
| spName | string                    | 库名   | 是 | -   |  |
| key    | string                    | 键名   | 是 | -   |  |
| value  | string / number / boolean | 保存到存储中到数据   | 是 | -   |  |
