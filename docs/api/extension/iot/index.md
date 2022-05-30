---
layout: default
title: iot
nav_order: 6
parent: 扩展
grand_parent: API
---

# iot

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

# init
## 说明
联接平台初始化，绑定物服务

## 示例
```javascript
let result = TinyAPI.iot.init({
   connect: () => {
       console.log("connectd")
   },
   disconnect: () => {
       console.log("disconnect")
   }
});

console.log(result); // true, false
```

## 入参

| 属性名        | 类型       | 属性说明   | 必填  | 默认值                         | 取值范围 |
|:-----------|:---------|:-------|:----|:----------------------------|:-----|
| connect    | function | 联接成功回调 | 否   |  |      |
| disconnect | function | 联接失败回调 | 否   |  |      |

## 出参

| 属性名    | 类型      | 属性说明          | 必填  | 默认值                         | 取值范围 |
|:-------|:--------|:--------------|:----|:----------------------------|:-----|
| result | boolean | 判断设备系统中是否有物服务 |     |  |      |

{:toc}

# getService
## 说明
获取指定类型的服务，类型在物模型中定义

## 示例
```javascript
var result = TinyAPI.iot.getService({
    type: "printer",
    fail: (error) => {
        console.log(error)
    }
});

// [
//    {
//       "deviceId":"VB03211P26005",
//       "isAuth":false,
//       "serviceId":"thermal_printer",
//       "serviceType":"printer"
//    }
// ]
```

## 入参

| 属性名  | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-----|:---------|:-----------------------|:----|:----------------------------|:-----|
| type | string   | 服务类型，类似`printer`，`scanner` | 否   |  |      |
| fail | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型       | 属性说明 | 必填  | 默认值                         | 取值范围 |
|:-------|:---------|:-----|:----|:----------------------------|:-----|
| result | arrays   | 服务数组 |     |  |      |

## `result`参数

| 属性名         | 类型      | 属性说明 | 必填  | 默认值                         | 取值范围 |
|:------------|:--------|:-----|:----|:----------------------------|:-----|
| deviceId    | string  | 设备id |     |  |      |
| isAuth      | boolean | 是否校验 |     |  |      |
| serviceId   | string  | 服务id |     |  |      |
| serviceType | string  | 服务类型 |     |  |      |

{:toc}

# registerServiceChange
## 说明
监听系统中的指定类型服务变化

## 示例
```javascript
TinyAPI.iot.registerServiceChange({
    type: "printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名     | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:--------|:---------|:-----------------------|:----|:----------------------------|:-----|
| type    | string   | 服务类型，类似`printer`，`scanner` | 是   |  |      |
| add     | function | 服务添加回调                 | 否   |  |      |
| offline | function | 服务下线回调                 | 否   |  |      |
| fail    | function | 调用失败回调                 | 否   |  |      |

{:toc}

# registerServiceEvent
## 说明
监听指定服务的物模型中定义的`Event`发生，`deviceId` + `serviceId` 确定唯一服务

## 示例
```javascript
TinyAPI.iot.registerServiceEvent({
    deviceId: "VB03211P26005",
    serviceId: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名       | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----------|:---------|:-----------------------|:----|:----------------------------|:-----|
| deviceId  | string   | `ThingService`中的`deviceId` | 是   |  |      |
| serviceId | string   | `ThingService`中的`serviceId`                 | 是   |  |      |
| event     | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail      | function | 调用失败回调                 | 否   |  |      |

{:toc}

# registerServiceProperty
## 说明
监听某个服务的物模型中定义的`property`变化，`deviceId` + `serviceId` 确定唯一服务

## 示例
```javascript
TinyAPI.iot.registerServiceProperty({
    deviceId: "VB03211P26005",
    serviceId: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名       | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----------|:---------|:-----------------------|:----|:----------------------------|:-----|
| deviceId  | string   | `ThingService`中的`deviceId` | 是   |  |      |
| serviceId | string   | `ThingService`中的`serviceId`                 | 是   |  |      |
| event     | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail      | function | 调用失败回调                 | 否   |  |      |

{:toc}

# executeCommand
## 说明
对指定服务执行物模型中定义的`command`。`serviceInfo`中的`deviceId`和`serviceId`必须。否则会出现找不到服务的情况

## 示例
```javascript
TinyAPI.iot.executeCommand({
    thing: "VB03211P26005",
    params: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});

// thing:
// {
//    "deviceId":"VB03211P26005",
//         "isAuth":false,
//         "serviceId":"thermal_printer",
//         "serviceType":"printer"
// }
// params:
// {
//    "command":"print",
//         "params":{
//    "line":[
//       "{\"align\":1,\"anticolor\":1,\"bold\":1,\"size\":28,\"text\":\"SUNMI TEST PRINTER!!!\",\"textspace\":0,\"type\":1,\"underline\":0,\"command\":\"print_text\"}"
//    ]
// }
// }
```

## 入参

| 属性名      | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:---------|:---------|:-----------------------|:----|:----------------------------|:-----|
| thing    | object   | 通过SDK获取的`service info` | 是   |  |      |
| params   | string   | 物模型描述的 `command` 参数                 | 是   |  |      |
| response | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail     | function | 调用失败回调                 | 否   |  |      |

{:toc}

# getProperty
## 说明
获取物模型服务的`property`，`serviceInfo`中的`deviceId`和`serviceId`必传，否则会出现找不到服务的情况

## 示例
```javascript
let result = TinyAPI.iot.getProperty({
    thing: "VB03211P26005",
    params: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名      | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:---------|:---------|:-----------------------|:----|:----------------------------|:-----|
| thing    | object   | 通过SDK获取的`service info` | 是   |  |      |
| params   | string   | 物模型描述的获取属性参数                 | 是   |  |      |
| response | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail     | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:-----------------------|:----|:----------------------------|:-----|
| result | string | 本次调用的唯一标识符，与回调第一个参数对应 |     |  |      |

{:toc}

# setProperty
## 说明
对指定服务设置模型中定义的`property`，`serviceInfo`中的`deviceId`和`serviceId`必传，否则会出现找不到服务的情况

## 示例
```javascript
let result = TinyAPI.iot.setProperty({
    thing: "VB03211P26005",
    params: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名      | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:---------|:---------|:-----------------------|:----|:----------------------------|:-----|
| thing    | object   | 通过SDK获取的`service info` | 是   |  |      |
| params   | string   | 物模型描述的设置属性参数                 | 是   |  |      |
| response | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail     | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:-----------------------|:----|:----------------------------|:-----|
| result | string | 本次调用的唯一标识符，与回调第一个参数对应 |     |  |      |