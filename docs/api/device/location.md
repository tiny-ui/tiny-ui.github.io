---
layout: default
title: location
nav_order: 6
parent: 设备
grand_parent: API
---

# location

## 说明
获取当前设备经纬度

## 示例
```javascript
TinyAPI.device.info((res) => {console.log(res)});
// { latitude: 37.421998333333335, longitude: -122.084 }
```

## 入参

| 属性名      | 类型       | 属性说明    | 必填  | 默认值     | 取值范围                 |
|:---------|:---------|:--------|:----|:--------|:---------------------|
| callback | function | 当前经纬度回调 | 是   |  |  |