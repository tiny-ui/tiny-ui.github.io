---
layout: default
title: cancelIdleCallback
nav_order: 6
parent: 平台
grand_parent: 扩展
---

# cancelIdleCallback
## 说明
取消添加的空闲时执行事件

## 使用
```javascript
cancelIdleCallback(event);
```

## 示例
```typescript
// 设置一个空闲时事件
let event = requestIdleCallback(() => {
    console.log("time out event");
});

// 清除该空闲时事件
cancelIdleCallback(event);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| event | Object | - | 是 | 取消空闲执行事件 | v0.3.0 |
