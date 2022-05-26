---
layout: default
title: unregister
nav_order: 2
parent: 事件
grand_parent: API
---

# unregister
## 说明
取消注册当前页面监听事件

## 示例
```javascript
TinyAPI.event.unregister("back");   // 取消注册back下所有事件监听

var fn = function (res) {
    console.log("back func");
}
TinyAPI.event.unregister("back", fn);   // 取消注册back下fn的事件监听
```

## 参数

| 属性名  | 类型       | 属性说明 | 必填  | 默认值     | 取值范围                 |
|:-----|:---------|:-----|:----|:--------|:---------------------|
| name | string   | 事件名称 | 是   |  |  |
| func | function | 监听事件 | 否   |     |           |

### NOTICE
如果页面销毁时，没有取消注册在当前页面已注册事件，会在error出现提示 `"quickJSContext hashcode = 12523124154 not unregister"` 