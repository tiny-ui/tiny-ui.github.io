---
layout: default
title: send
nav_order: 3
parent: 事件
grand_parent: API
---

# send
## 说明
发送数据给已经注册监听事件

## 示例
```javascript
TinyAPI.event.send(
    "back", {
        data1: "arg",
        data2: 342
    }
);
```

## 参数

| 属性名  | 类型                              | 属性说明    | 必填      | 默认值     | 取值范围       |
|:-----|:--------------------------------|:--------|:--------|:--------|:-----------|
| name | string                          | 事件名称    | 是       |         |            |
| data | object, string, number, boolean | 发送给监听事件的数据 | 是   |     |           |

