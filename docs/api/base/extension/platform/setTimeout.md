---
layout: default
title: setTimeout
nav_order: 1
parent: 平台
grand_parent: 扩展
---

# setTimeout
## 说明
添加一个定时器事件

## 使用
```javascript
setTimeout(func, delayTime);
```

## 示例
```javascript
setTimeout(log, 2000);

function log(){
    console.log("print msg");
}
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| func | Function | - | 是 | 执行事件 | v0.3.0 |
| delayTime | Integer | - | 是 | 延时时间（ms） | v0.3.0 |
