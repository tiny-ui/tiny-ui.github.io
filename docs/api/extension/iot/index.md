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
   },
    response: () => {
       console.log("time out")
    }
});

console.log(result); // -1, 0, ...
```

## 入参

| 属性名        | 类型       | 属性说明            | 必填  | 默认值                         | 取值范围 |
|:-----------|:---------|:----------------|:----|:----------------------------|:-----|
| connect    | function | 联接成功回调          | 否   |  |      |
| disconnect | function | 联接失败回调          | 否   |  |      |
| response   | function | 联接超时回调（超时5秒会回调） | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明        | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:------------|:----|:----------------------------|:-----|
| result | number | 物服务初始化结果状态码 |     |  |      |

{:toc}

# getService
## 说明
获取指定类型的服务，类型在物模型中定义

## 示例
```javascript
var result = TinyAPI.iot.getService("printer");

// result:
// {
//      msg: null,
//      data:
// [
//    {
//       "deviceId":"VB03211P26005",
//       "deviceType": "",
//       "isAuth":false,
//       "serviceId":"thermal_printer",
//       "serviceType":"printer"
//       "model":""
//       "deviceName":""
//    }
// ]
// }
```

## 入参

| 属性名  | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-----|:---------|:-----------------------|:----|:----------------------------|:-----|
| type | string   | 服务类型，类似`printer`，`scanner` | 否   |  |      |

## 出参

| 属性名  | 类型     | 属性说明 | 必填  | 默认值                         | 取值范围 |
|:-----|:-------|:-----|:----|:----------------------------|:-----|
| msg  | string | 错误信息 |     |  |      |
| data | arrays | 服务数组 |     |  |      |

## `data`参数

| 属性名         | 类型      | 属性说明 | 必填  | 默认值                         | 取值范围 |
|:------------|:--------|:-----|:----|:----------------------------|:-----|
| deviceId    | string  | 设备id |     |  |      |
| deviceType  | string  | 设备类型 |     |  |      |
| isAuth      | boolean | 是否校验 |     |  |      |
| serviceId   | string  | 服务id |     |  |      |
| serviceType | string  | 服务类型 |     |  |      |
| model       | string  |      |     |  |      |
| deviceName  | string  | 设备名称 |     |  |      |

{:toc}

# getDevice
## 说明
获取指定设备的服务，类型在设备模型中定义

## 示例
```javascript
var result = TinyAPI.iot.getDevice();

// result:
// {
//      msg: null,
//      data:
// [
//    {
//       "deviceId":"KM16225C43382",
//       "deviceType": "",
//       "isAuth":true,
//       "isLocal":true,
//       "model":"",
//       "deviceName":"K2_MINI",
//       "serviceList": [
//          {"deviceId":null,
//           "deviceName":null,
//           "deviceType":null,
//           "isAuth":false,
//           "model":null,
//           "serviceId":"thermal_printer",
//           "serviceType":"printer"},
//          {"deviceId":null,
//           "deviceName":null,
//           "deviceType":null,
//           "isAuth":false,
//           "model":null,
//           "serviceId":"sunmi_statuslamp",
//           "serviceType":"statuslamp"},
//          {"deviceId":null,
//           "deviceName":null,
//           "deviceType":null,
//           "isAuth":false,
//           "model":null,
//           "serviceId":"sunmi_scanner",
//           "serviceType":"scanner"},
//          {"deviceId":null,
//           "deviceName":null,
//           "deviceType":null,
//           "isAuth":false,
//           "model":null,
//           "serviceId":"sunmi_idmifardcard",
//           "serviceType":"id_mifare_card"}
//       ]
//    }
// ]
// }
```

## 入参

| 属性名      | 类型       | 属性说明                | 必填  | 默认值                         | 取值范围 |
|:---------|:---------|:--------------------|:----|:----------------------------|:-----|
| deviceId | string   | 设备id，如果不传则返回所有的设备服务 | 否   |  |      |

## 出参

| 属性名  | 类型     | 属性说明 | 必填  | 默认值                         | 取值范围 |
|:-----|:-------|:-----|:----|:----------------------------|:-----|
| msg  | string | 错误信息 |     |  |      |
| data | arrays | 服务数组 |     |  |      |

## `data`参数

| 属性名         | 类型      | 属性说明   | 必填  | 默认值                         | 取值范围 |
|:------------|:--------|:-------|:----|:----------------------------|:-----|
| deviceId    | string  | 设备id   |     |  |      |
| deviceType  | string  | 设备类型   |     |  |      |
| isAuth      | boolean | 是否校验   |     |  |      |
| isLocal     | boolean | 是否本机   |     |  |      |
| serviceList | List    | 包含的物服务 |     |  |      |
| model       | string  |        |     |  |      |
| deviceName  | string  | 设备名称   |     |  |      |

{:toc}

# registerServiceChange
## 说明
监听系统中的指定类型服务变化

## 示例
```javascript
let result = TinyAPI.iot.registerServiceChange({
    type: "printer",
    add: (res) => {
        console.log(res);
// res:
//    {
//       "deviceId":"VB03211P26005",
//       "isAuth":false,
//       "serviceId":"thermal_printer",
//       "serviceType":"printer"
//    }
    },
    offline: (s1, s2) => {

    },
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

## `add`入参

| 属性名 | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------------------|:----|:----------------------------|:-----|
| deviceId    | string  | 设备id |     |  |      |
| isAuth      | boolean | 是否校验 |     |  |      |
| serviceId   | string  | 服务id |     |  |      |
| serviceType | string  | 服务类型 |     |  |      |

## `offline`入参

| 属性名 | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------------------|:----|:----------------------------|:-----|
| s1  | string |  |     |  |      |
| s2  | string |  |     |  |      |

## 出参

| 属性名    | 类型     | 属性说明        | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:------------|:----|:----------------------------|:-----|
| result | number | 注册服务变化结果状态码 |     |  |      |

{:toc}

# unregisterServiceChange
## 说明
取消监听指定类型服务服务变化

## 示例
```javascript
let result = TinyAPI.iot.unregisterServiceChange({
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
| fail    | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明          | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------------|:----|:----------------------------|:-----|
| result | number | 取消注册服务变化结果状态码 |     |  |      |

{:toc}

# registerServiceEvent
## 说明
监听指定服务的物模型中定义的`Event`发生，`deviceId` + `serviceId` 确定唯一服务（同一个serviceId注册的event在整个app中只能存在一个）

## 示例
```javascript
let result = TinyAPI.iot.registerServiceEvent({
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

## `event`入参

| 属性名 | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------------------|:----|:----------------------------|:-----|
| s   | string |  |     |  |      |
| s1  | string |  |     |  |      |
| s2  | string |  |     |  |      |

## 出参

| 属性名    | 类型     | 属性说明        | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:------------|:----|:----------------------------|:-----|
| result | number | 注册服务监听结果状态码 |     |  |      |

{:toc}

# registerServiceEventByListener
## 说明
监听指定服务的物模型中定义的`Event`发生，`deviceId` + `serviceId` 确定唯一服务（同一个serviceId注册的event在整个app中可以存在多个）

## 示例
```javascript
let result = TinyAPI.iot.registerServiceEventByListener({
    deviceId: "VB03211P26005",
    serviceId: "thermal_printer",
    serviceType: "printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名         | 类型       | 属性说明                          | 必填  | 默认值                         | 取值范围 |
|:------------|:---------|:------------------------------|:----|:----------------------------|:-----|
| deviceId    | string   | `ThingService`中的`deviceId`    | 是   |  |      |
| serviceId   | string   | `ThingService`中的`serviceId`   | 是   |  |      |
| serviceType | string   | `ThingService`中的`serviceType` | 是   |  |      |
| event       | function | `IServiceEventListener` 监听回调  | 否   |  |      |
| fail        | function | 调用失败回调                        | 否   |  |      |

## `event`入参

| 属性名 | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------------------|:----|:----------------------------|:-----|
| s   | string |  |     |  |      |
| s1  | string |  |     |  |      |
| s2  | string |  |     |  |      |

## 出参

| 属性名    | 类型     | 属性说明        | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:------------|:----|:----------------------------|:-----|
| result | number | 注册服务监听结果状态码 |     |  |      |

{:toc}

# unregisterServiceEvent
## 说明
取消监听指定物服务的`event`

## 示例
```javascript
let result = TinyAPI.iot.unregisterServiceEvent({
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
| fail      | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明          | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------------|:----|:----------------------------|:-----|
| result | number | 取消注册服务监听结果状态码 |     |  |      |

{:toc}

# unregisterServiceEventByListener
## 说明
取消监听指定物服务的`eventByListener`

## 示例
```javascript
let result = TinyAPI.iot.unregisterServiceEventByListener({
    deviceId: "VB03211P26005",
    serviceId: "thermal_printer",
    serviceType: "printer",
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名         | 类型       | 属性说明                          | 必填  | 默认值                         | 取值范围 |
|:------------|:---------|:------------------------------|:----|:----------------------------|:-----|
| deviceId    | string   | `ThingService`中的`deviceId`    | 是   |  |      |
| serviceId   | string   | `ThingService`中的`serviceId`   | 是   |  |      |
| serviceType | string   | `ThingService`中的`serviceType` | 是   |  |      |
| fail        | function | 调用失败回调                        | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明          | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------------|:----|:----------------------------|:-----|
| result | number | 取消注册服务监听结果状态码 |     |  |      |

{:toc}

# registerServiceProperty
## 说明
监听指定服务的物模型中定义的`property`变化，`deviceId` + `serviceId` 确定唯一服务

## 示例
```javascript
let result = TinyAPI.iot.registerServiceProperty({
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

## `event`入参

| 属性名 | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------------------|:----|:----------------------------|:-----|
| s   | string |  |     |  |      |
| s1  | string |  |     |  |      |
| s2  | string |  |     |  |      |

## 出参

| 属性名    | 类型     | 属性说明                | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:--------------------|:----|:----------------------------|:-----|
| result | number | 注册服务`property`结果状态码 |     |  |      |

{:toc}

# unregisterServiceProperty
## 说明
取消监听指定服务的`property`变化

## 示例
```javascript
let result = TinyAPI.iot.unregisterServiceProperty({
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
| fail      | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明                  | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:----------------------|:----|:----------------------------|:-----|
| result | number | 取消注册服务`property`结果状态码 |     |  |      |

{:toc}

# execute
## 说明
通用执行

## 示例
```javascript
let result = TinyAPI.iot.execute({
    thing: thing,
    type: "command",
    action: "execute",
    params: params,
    response: (s, map) => {
        console.log(s, JSON.stringify(map))
    },
    fail: (error) => {
        console.log(error)
    }
});
```

## 入参

| 属性名      | 类型       | 属性说明                         | 必填  | 默认值                         | 取值范围                                                                                            |
|:---------|:---------|:-----------------------------|:----|:----------------------------|:------------------------------------------------------------------------------------------------|
| thing    | object   | 通过SDK获取的`service info`       | 是   |  |                                                                                                 |
| type     | string   | action类型                     | 是   |  | command, commands, property                                                                     |
| action   | string   | type对应类型                     | 是   |  | command->execute(执行command); commands->async/sync(串行/并行指令集); property->get/set(对应property获取和设置) |
| params   | string   | 物模型描述的设置属性参数                 | 是   |  |                                                                                                 |
| response | function | `IServiceEventListener` 监听回调 | 否   |  |                                                                                                 |
| fail     | function | 调用失败回调                       | 否   |  |                                                                                                 |

## 出参

| 属性名    | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:-----------------------|:----|:----------------------------|:-----|
| result | string | 本次调用的唯一标识符，与回调第一个参数对应 | 是   |  |      |

## `response`入参

| 属性名 | 类型     | 属性说明       | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------|:----|:----------------------------|:-----|
| s   | string | 本次调用的唯一标识符 |     |  |      |
| map | obj    | 调用结果       |     |  |      |

{:toc}

# executeCommand
## 说明
对指定服务执行物模型中定义的`command`。`serviceInfo`中的`deviceId`和`serviceId`必须。否则会出现找不到服务的情况

## 示例
```javascript
let result = TinyAPI.iot.executeCommand({
    thing: thing,
    params: params,
    response: (s, map) => {
        console.log(s, JSON.stringify(map))
    },
    fail: (error) => {
        console.log(error)
    }
});

var thing =
{
   "deviceId":"VB03211P26005",
        "isAuth":false,
        "serviceId":"thermal_printer",
        "serviceType":"printer"
}
var params =
    "{\"command\":\"print_texts\",\"params\":{\"type\":6,\"columns\":[{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"名称\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"单价\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"单位\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"总价\",\"textspace\":0,\"type\":1,\"underline\":0}]}}";

//  s:
//  11379289203296cff-b16f-4d2c-a4dd-a3c9af6cd2e4
//  map:
//  { action_type: command, deviceID: PB08203460291, action: execute, serviceID: thermal_printer, response: {"code":200,"data":{"code":"printer_0000","command":"print","msg":"打印成功"},"..." }
```

## 入参

| 属性名      | 类型       | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:---------|:---------|:-----------------------|:----|:----------------------------|:-----|
| thing    | object   | 通过SDK获取的`service info` | 是   |  |      |
| params   | string   | 物模型描述的 `command` 参数                 | 是   |  |      |
| response | function | `IServiceEventListener` 监听回调                 | 否   |  |      |
| fail     | function | 调用失败回调                 | 否   |  |      |

## 出参

| 属性名    | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:-----------------------|:----|:----------------------------|:-----|
| result | string | 本次调用的唯一标识符，与回调第一个参数对应 | 是   |  |      |

## `response`入参

| 属性名 | 类型     | 属性说明       | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------|:----|:----------------------------|:-----|
| s   | string | 本次调用的唯一标识符 |     |  |      |
| map | obj    | 调用结果       |     |  |      |

{:toc}

# executeCommands
## 说明
无序执行多个`command`

## 示例
```javascript
let result = TinyAPI.iot.executeCommands({
    thing: thing,
    params: params,
    sync: true,
    response: (s, map) => {
        console.log(s, JSON.stringify(map))
    },
    fail: (error) => {
        console.log(error)
    }
});

var thing =
{
        "deviceId":"VB03211P26005",
        "isAuth":false,
        "serviceId":"thermal_printer",
        "serviceType":"printer"
}
var params =
    "[{\"command\":\"print_qrcode\",\"params\":{\"size\":10,\"type\":3,\"code\":\"皇马是冠军---\u003e法兰克福也是---\u003e罗马也是\",\"el\":3,\"align\":1}},{\"command\":\"print_text\",\"params\":{\"bold\":0,\"anticolor\":0,\"align\":0,\"size\":18,\"text\":\"simple text-------------end\",\"underline\":0,\"type\":1,\"textspace\":1}},{\"command\":\"print_texts\",\"params\":{\"type\":6,\"columns\":[{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"名称\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"单价\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"单位\",\"textspace\":0,\"type\":1,\"underline\":0},{\"colsWidthArr\":1,\"command\":\"print_text\",\"align\":0,\"anticolor\":0,\"bold\":0,\"size\":24,\"text\":\"总价\",\"textspace\":0,\"type\":1,\"underline\":0}]}}]";

//  s:
//  11379289203296cff-b16f-4d2c-a4dd-a3c9af6cd2e4
//  map:
//  { action_type: command, deviceID: PB08203460291, action: execute, serviceID: thermal_printer, response: {"code":200,"data":{"code":"printer_0000","command":"print","msg":"打印成功"},"..." }
```

## 入参

| 属性名      | 类型       | 属性说明                   | 必填  | 默认值  | 取值范围 |
|:---------|:---------|:-----------------------|:----|:-----|:-----|
| thing    | object   | 通过SDK获取的`service info` | 是   |      |      |
| params   | string   | 物模型描述的 `command` 参数                 | 是   |      |      |
| sync     | boolean  | 是否串行执行                | 否   | true |      |
| response | function | `IServiceEventListener` 监听回调                 | 否   |      |      |
| fail     | function | 调用失败回调                 | 否   |      |      |

## 出参

| 属性名    | 类型     | 属性说明                   | 必填  | 默认值                         | 取值范围 |
|:-------|:-------|:-----------------------|:----|:----------------------------|:-----|
| result | string | 本次调用的唯一标识符，与回调第一个参数对应 | 是   |  |      |

## `response`入参

| 属性名 | 类型     | 属性说明       | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------|:----|:----------------------------|:-----|
| s   | string | 本次调用的唯一标识符 |     |  |      |
| map | obj    | 调用结果       |     |  |      |

{:toc}

# getProperty
## 说明
获取物模型服务的`property`，`serviceInfo`中的`deviceId`和`serviceId`必传，否则会出现找不到服务的情况

## 示例
```javascript
let result = TinyAPI.iot.getProperty({
    thing: thing,
    params: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});

var thing =
    {
        "deviceId":"VB03211P26005",
        "isAuth":false,
        "serviceId":"thermal_printer",
        "serviceType":"printer"
    }
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

## `response`入参

| 属性名 | 类型     | 属性说明       | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------|:----|:----------------------------|:-----|
| s   | string | 本次调用的唯一标识符 |     |  |      |
| map | obj    | 调用结果       |     |  |      |

{:toc}

# setProperty
## 说明
对指定服务设置模型中定义的`property`，`serviceInfo`中的`deviceId`和`serviceId`必传，否则会出现找不到服务的情况

## 示例
```javascript
let result = TinyAPI.iot.setProperty({
    thing: thing,
    params: "thermal_printer",
    fail: (error) => {
        console.log(error)
    }
});

var thing =
    {
        "deviceId":"VB03211P26005",
        "isAuth":false,
        "serviceId":"thermal_printer",
        "serviceType":"printer"
    }
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

## `response`入参

| 属性名 | 类型     | 属性说明       | 必填  | 默认值                         | 取值范围 |
|:----|:-------|:-----------|:----|:----------------------------|:-----|
| s   | string | 本次调用的唯一标识符 |     |  |      |
| map | obj    | 调用结果       |     |  |      |

{:toc}

# 状态码

| 错误码    | 错误描述                                             | 
|:-------|:-------------------------------------------------|
| 200    | 成功                                               |
| -1     | SDK没有初始化                                         |
| -2     | 正在初始化                                            |
| -1000  | 获取不到SN，需要READ_PHONE_STATE权限                      |
| -1001  | 有权限下，SN仍获取失败，这种情况下需要升级ROM（安卓11设备很早期版本rom可能存在该问题） |
| -2000  | 应用市场不存在，需要设备先安装应用市场后下载SDK才能正常使用                  |
| -2001  | 应用市场下载失败 (ps:无返回具体错误码 需要显示弹框才知道)                 |
| -2002  | 应用市场安装失败 (ps:无返回具体错误码 需要显示弹框才知道)                 |
| -2003  | 应用市场调用超时，调用应用市场能力30秒无返回                          |
| -3000  | 查询信息失败，具体原因见msg                                  |
| -10000 | license未校验                                       |
| -10001 | license失效                                        |
| -10002 | license校验失败                                      |
| -10003 | license参数异常                                      |
| 301    | 服务已调用，但是响应超时                                     |
| 400    | 参数为空或者错误                                         |
| 500    | 没有找到服务，或者服务暂时不可用                                 |
| 501    | 服务已下线，暂时不可用                                      |
| 502    | 当前堆积请求过多，请稍后再请求                                  |
| 510    | 服务未发布                                            |
| -20000 | 参数异常                                             |
| -20001 | 绑定服务失败                                           |

{:toc}

# FAQ
## 一直出现【IOT SDK正在下载，请稍后再试～】吐司怎么办！！！
### （退后，我要开始装x了）
1. 请检查设备是否联网 / 网络状态差。请移步网络状态好的地方；
2. 如果调用IOT能力出现【获取设备信息】的授权弹窗，请点击【授权】/【允许】；
3. 确认设备不是通过非法途径获取的，请把设备SN号给帅气的客服小哥哥查一下；
4. 设备不能开代理或其他拦截网络请求的骚操作；
5. 请前往【设置】->【应用】中找一下，是否有：sunmi物服务、对应的adapter包，并保证正在运行。如果没有这些应用，请联系同样帅气的客服小哥哥；
6. 请卸载后，并重装你的app。或者清除app中的所有缓存。

## 如何在你的业务代码中接收调用IOT能力失败通知？？？
请在代码中使用`catch`写法，调用失败会在`catch`返回错误信息通知
