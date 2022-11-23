---
layout: default
title: timestamp
nav_order: 8
parent: 扩展
grand_parent: API
---

# time

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

# now
## 说明
获取当前时间戳 / 获取当前时间格式为yyyyMMdd HHmmss的时间 / 按照特定格式格式化当前时间

## 示例
```javascript
// 获取当前时间对象
const now = TinyAPI.time.now()
// 获取当前时间字符串 默认格式 yyyyMMdd HHmmss 返回值: 20221108 183335
console.log(now.string())
// 获取当前时间毫秒值字符串 返回值:"1667903615128"
console.log(now.unixMilli())
// 按照特定格式格式化当前时间 返回值:"2022-11-08"
console.log(now.format("yyyy-MM-dd"))
```

## 出参

| 属性名 | 类型     | 属性说明 | 必填  | 默认值   | 取值范围           |
|:----|:-------|:-----|:----|:------|:---------------|
| now | object | 时间结果 |     |       |    |

## `now`参数

| 属性名     | 类型       | 属性说明   | 必填  | 默认值     | 取值范围                 |
|:--------|:---------|:-------|:----|:--------|:---------------------|
| string  | function | 当前时间字符串 默认格式 yyyyMMdd HHmmss    |     |  |  |
| unixMilli | function | 当前时间毫秒值字符串 |     |  |  |
| format | function | 按照特定格式格式化当前时间 |     |  |  |

{:toc}

# format
## 说明
按照特定格式格式化特定时间

## 示例
```javascript
const time = TinyAPI.time.format("yyyy-MM-dd",1667902544768);
console.log(time);
// 返回值:"2022-11-08"
```

## 入参

| 属性名     | 类型     | 属性说明    | 必填  | 默认值 | 取值范围           |
|:--------|:-------|:--------|:----|:----|:---------------|
| pattern | string | 转换的时间格式 | 是   | -   |    |
| num     | number | 特定时间    | 是   | -   |    |

{:toc}

# parse
## 说明
按照特定格式，转换特定时间字符串

##示例
```javascript
const time = TinyAPI.time.parse("yyyy-MM-dd","2022-11-08");
console.log(time);
// 返回值:"1667836800000"
```

## 入参

| 属性名     | 类型     | 属性说明    | 必填  | 默认值 | 取值范围           |
|:--------|:-------|:--------|:----|:----|:---------------|
| pattern | string | 转换的时间格式 | 是   | -   |    |
| str     | string | 时间字符串        | 是   | -   |    |