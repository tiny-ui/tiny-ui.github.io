---
layout: default
title: requestIdleCallback
nav_order: 5
parent: 平台
grand_parent: 扩展
---

# requestIdleCallback
## 说明
App 空闲时期被调用

## 使用
```javascript
requestIdleCallback(func);
```

## 示例
```javascript
requestIdleCallback(log);

function log(){
    console.log("print msg");
}
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| func | Function | - | 是 | 执行事件 | v0.3.0 |
| delayTime | Integer | - | 是 | 延时时间（ms） | v0.3.0 |
