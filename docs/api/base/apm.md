---
layout: default
title: log report
nav_order: 3
parent: 基础
grand_parent: API
---

# log

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
   {:toc}

# recycle
## 说明
在一定的周期内，循环日志上报

## 示例
```javascript
TinyAPI.log.recycle({
   tag: "max_log",
   error: true,
   msg: "该功能不可用",
   params: {
       ... // 自定义
   }
});
```

## 入参

| 属性名    | 类型      | 属性说明   | 必填  | 默认值   | 取值范围 |
|:-------|:--------|:-------|:----|:------|:-----|
| tag    | string  | 日志标签   | 是   |       |      |
| error  | boolean | 是否错误   | 否   | false |      |
| msg    | string  | 上报日志信息 | 否   |       |      |
| params | object  | 上报对象信息 | 否   |       |      |

{:toc}

# realTime
## 说明
实时日志上报

## 示例
```javascript
TinyAPI.log.realTime({
   tag: "max_log",
   error: true,
   msg: "该功能不可用",
   params: {
       ... // 自定义
   }
});
```

## 入参

| 属性名    | 类型      | 属性说明   | 必填  | 默认值   | 取值范围 |
|:-------|:--------|:-------|:----|:------|:-----|
| tag    | string  | 日志标签   | 是   |       |      |
| error  | boolean | 是否错误   | 否   | false |      |
| msg    | string  | 上报日志信息 | 否   |       |      |
| params | object  | 上报对象信息 | 否   |       |      |

{:toc}

# persistence
## 说明
持久化日志存储在本地，不上报

## 示例
```javascript
TinyAPI.log.persistence({
   tag: "max_log",
   error: true,
   msg: "该功能不可用",
   params: {
       ... // 自定义
   }
});
```

## 入参

| 属性名    | 类型      | 属性说明   | 必填  | 默认值   | 取值范围 |
|:-------|:--------|:-------|:----|:------|:-----|
| tag    | string  | 日志标签   | 是   |       |      |
| error  | boolean | 是否错误   | 否   | false |      |
| msg    | string  | 上报日志信息 | 否   |       |      |
| params | object  | 上报对象信息 | 否   |       |      |

{:toc}