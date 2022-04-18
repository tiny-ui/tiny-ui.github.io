---
layout: default
title: console
nav_order: 2
parent: 扩展
grand_parent: API
---

# console

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

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

提示：
```javascript
console.log('1' + obj);// 会输出 `1[object Object]`，而不是 `1{ obj 内容 }}`

// 方式1. 可以使用 JSON.stringify 来输出对象
console.log('1' + JSON.stringify(obj));

// 方式2. 建议使用以下方式
console.log('1', obj);
```
