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