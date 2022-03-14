---
layout: default
title: clearTimeout
nav_order: 2
parent: 平台
grand_parent: 扩展
---

# clearTimeout
## 说明
清除指定定时器事件

## 使用
```javascript
clearTimeout(event);
```

## 示例
```typescript
// 设置一个定时器事件s
let event = setTimeout(() => {
    console.log("time out event");
}, 2000);

// 清除该定时器事件
clearTimeout(event);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| event | Object | - | 是 | 指定定时器事件 | v0.3.0 |
