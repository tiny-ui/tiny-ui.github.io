---
layout: default
title: 平台
nav_order: 1
parent: 扩展
grand_parent: API
---

# 扩展

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

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
|:----|:----|:------|:-----|:----|:-----------|
| func | Function | - | 是 | 执行事件 | v0.3.0 |
| delayTime | Integer | - | 是 | 延时时间（ms） | v0.3.0 |

{:toc}

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
|:----|:----|:------|:-----|:----|:-----------|
| event | Object | - | 是 | 指定定时器事件 | v0.3.0 |

{:toc}

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

{:toc}

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
|:----|:----|:------|:-----|:----|:-----------|
| event | Object | - | 是 | 指定循环事件 | v0.3.0 |

{:toc}

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

{:toc}

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

{:toc}

# console

## 说明
`Console`对象提供了 Android 调试日志打印的接口，可以从全局对象中访问到。提供了5个级别的日志输出格式。

## 使用
```javascript
console.log(...args);
console.debug(...args);
// 对应 Android Debug 级别日志

console.info(...args);
// 对应 Android Verbose 级别日志

console.warn(...args);
// 对应 Android Warn 级别日志

console.error(...args);
// 对应 Android Error 级别日志
```

{:toc}

# alert

## 说明
`alert`方法提供了简单的 Android 层弹窗提示，可以从全局对象中访问到

## 使用
```javascript
//参数为 string 类型的文本
alert(text);
```

## 示例
```typescript
// 设置一个定时器事件s
alert("login")
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| text | String | - | 是 | 弹窗显示文本 | v0.3.0 |