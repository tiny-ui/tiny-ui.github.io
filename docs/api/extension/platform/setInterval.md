---
layout: default
title: setInterval
nav_order: 3
parent: 平台
grand_parent: 扩展
---

# setInterval
## 说明
设置一个循环事件

## 使用
```javascript
setInterval(func, intervalTime);
```

## 示例
```javascript
setInterval(() => {
    console.log("interval event");
}, 3000);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| func | Function | - | 是 | 执行事件 | v0.3.0 |
| intervalTime | Integer | - | 是 | 循环时间（ms） | v0.3.0 |
