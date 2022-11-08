---
layout: default
title: sn
nav_order: 7
parent: 扩展
grand_parent: API
---

# sn
## 说明
获取当前设备sn号

## 示例
```javascript
TinyAPI.sunmi.getSerialNumber({
    result: function (res){
        console.log(res.sunmi-sn);
        console.log(res.success)
    }
});
```

## 入参

| 属性名      | 类型       | 属性说明   | 必填  | 默认值    | 取值范围           |
|:---------|:---------|:-------|:----|:-------|:---------------|
| result   | function | 调用结果回调 | 是   | -      |    |

## `result`入参

| 属性名      | 类型      | 属性说明   | 必填  | 默认值     | 取值范围                 |
|:---------|:--------|:-------|:----|:--------|:---------------------|
| sunmi-sn | string  | sn号    |     |  |  |
| success  | boolean | 是否获取成功 |     |  |  |