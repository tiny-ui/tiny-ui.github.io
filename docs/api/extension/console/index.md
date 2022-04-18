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
`Console` 对象是浏览器控制台调试的接口，在不同平台上它的工作方式不太一样，`TinyUI` 适配了其中较多使用的五个方法。 
`Console` 可以从全局对象中访问到，提供了5个级别的日志输出格式。

## 使用
```javascript
console.log(...args); // 打印内容的通用方法

console.debug(...args); // 在控制台打印一条 "debug" 级别的消息。

console.info(...args); // 打印说明信息

console.warn(...args); // 打印一个警告信息

console.error(...args); // 打印一条错误信息
```

需要注意的是：
```javascript
console.log('1' + obj);// 会输出 `1[object Object]`，而不是 `1{ obj 内容 }}`

// 方式1. 可以使用 JSON.stringify 来输出对象
console.log('1' + JSON.stringify(obj));

// 方式2. 建议使用以下方式
console.log('1', obj);
```
