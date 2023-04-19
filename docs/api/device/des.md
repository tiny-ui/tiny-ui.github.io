---
layout: default
title: DES
nav_order: 12
parent: 设备
grand_parent: API
---

# DES

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

# encryptDES
## 说明
使用默认iv加密DES

## 示例
```javascript
var result = TinyAPI.device.des("sunmi test", "sdg12422")
console.log(result) // jcbrUoYCsFKoiB+y0l1tiA==
```

## 入参

| 属性名      | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:---------|:-------|:--------|:----|:----------------------------|:-----|
| text     | string | 需要加密字符串 | 是   |  |      |
| key      | string | 加密密钥    | 是   |  |      |

## 出参

| 属性名    | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------|:----|:----------------------------|:-----|
| result | string | 加密完成字符串 |     |  |      |

{:toc}

# encryptDESIV
## 说明
使用自定义iv加密DES

## 示例
```javascript
var result = TinyAPI.device.desIV("sunmi test", "sdg12422", "88886666")
console.log(result) // jcbrUoYCsFKoiB+y0l1tiA==
```

## 入参

| 属性名  | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-----|:-------|:--------|:----|:----------------------------|:-----|
| text | string | 需要加密字符串 | 是   |  |      |
| key  | string | 加密密钥    | 是   |  |      |
| iv   | string | 加密iv    | 是   |  |      |

## 出参

| 属性名    | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------|:----|:----------------------------|:-----|
| result | string | 加密完成字符串 |     |  |      |

{:toc}

# decryptDES
## 说明
使用默认iv解密DES

## 示例
```javascript
var result = TinyAPI.device.decryptDES("jcbrUoYCsFKoiB+y0l1tiA==", "sdg12422")
console.log(result) // sunmi test
```

## 入参

| 属性名  | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-----|:-------|:--------|:----|:----------------------------|:-----|
| text | string | 需要解密字符串 | 是   |  |      |
| key  | string | 加密密钥    | 是   |  |      |

## 出参

| 属性名    | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------|:----|:----------------------------|:-----|
| result | string | 解密完成字符串 |     |  |      |

{:toc}

# decryptDESIV
## 说明
使用自定义iv解密DES

## 示例
```javascript
var result = TinyAPI.device.decryptDESIV("jcbrUoYCsFKoiB+y0l1tiA==", "sdg12422", "88886666")
console.log(result) // sunmi test
```

## 入参

| 属性名  | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-----|:-------|:--------|:----|:----------------------------|:-----|
| text | string | 需要解密字符串 | 是   |  |      |
| key  | string | 加密密钥    | 是   |  |      |
| iv   | string | 解密iv    | 是   |  |      |

## 出参

| 属性名    | 类型     | 属性说明    | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------|:----|:----------------------------|:-----|
| result | string | 解密完成字符串 |     |  |      |