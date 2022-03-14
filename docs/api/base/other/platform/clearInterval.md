---
layout: default
title: clearInterval
nav_order: 4
parent: 平台
grand_parent: 扩展
---

# clearInterval
## 说明
清除指定循环事件

## 使用
```javascript
clearInterval(event);
```

## 示例
```typescript
// 设置一个循环事件
let event = setInterval(() => {
    console.log("interval event");
}, 3000);

// 清除循环事件
clearInterval(event);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| event | Object | - | 是 | 指定循环事件 | v0.3.0 |
