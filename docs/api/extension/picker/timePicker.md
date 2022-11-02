---
layout: default
title: time picker
nav_order: 5
parent: 扩展
grand_parent: API
---

# TimePicker
## 说明

展示选择器弹窗视图.

## 基本使用

```javascript
let showTimePicker = TinyAPI.picker.showTimePicker({
    type: {
        year: true,
        moon: true,
        day: true,
        hour: true,
        minute: true,
        second: true,
    },
    bgColor:"red",
    titleBgColor:"red",
    date:{
        start:"2018-06-17 05:43:00",
        end:"2019-06-17 05:43:00",
        select:"2018-06-17 05:43:00",
    } ,
    // 取消 picker 弹窗回调
    onCancel: function () {
        TinyAPI.interact.showToast("onCancel");
    },
    // 确认选中回调
    onConfirm: function (date) {
        TinyAPI.interact.showToast(date)
    },
    // 选中回调
    onSelect: function (date) {
        TinyAPI.interact.showToast(date)
    },
    // picker 弹窗关闭回调
    onClose: function () {
        TinyAPI.interact.showToast("onClose")
    },
    closeOnMaskClick:false,
    confirmText : "confirmText",
    cancelText : "confirmText",
    dividerType:"warp",
    dividerColor:"black",
    textColorCenter:"green",
    textColorOut:"white",
    titleColor:"green",
    submitColor:"blue",
    cancelColor:"blue",
    subCalSize:10,
    titleSize:10,
    contentSize:12,
    lineSpacingMultiplier:2.1,
    title: "title",
});
    console.log(showTimePicker)
    showTimePicker.setSelectDate("2018-06-17 05:43:00");
    setTimeout(function (){
        showTimePicker.close();
    },3000)
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 |
|:----|:----|:------|:-----|:----|
|type|object|无|❎|详见type参数|
|bgColor|string|无|❎|滚轮背景色|
|titleBgColor|string||❎|标题栏背景色|
|date|object||❎|详见date参数|
|closeOnMaskClick|bool|true|❎|是否允许点击浮层关闭picker|
|confirmText|string|无|❎|确认按钮文案|
|cancelText|string|无|❎|取消按钮文案|
|dividerType|string|无|❎|取消按钮文案|
|dividerColor|string|无|❎|分隔线颜色|
|textColorCenter|string|无|❎|选中项文字颜色设置|
|textColorOut|string|无|❎|未选中项文字颜色设置|
|titleColor|string|无|❎|标题文字颜色设置|
|cancelColor|string|无|❎|取消按钮颜色设置|
|submitColor|string|无|❎|确认文字颜色设置|
|titleSize|number(整数)|无|❎|标题文字大小设置|
|subCalSize|number(整数)|无|❎|确定、取消按钮大小设置|
|contentSize|number(整数)|无|❎|滚轮文字大小设置|
|lineSpacingMultiplier|number(double)|无|❎|滚轮间距设置（1.2-2.0倍，此为文字高度的间距倍数）|
|title|array|无|❎|标题文案|
|onConfirm|func|无|❎|确认选中回调|
|onSelect|func|无|❎|选中回调|
|onCancel|func|无|❎|取消按钮回调|
|onClose|func|无|❎|picker关闭回调|

## type 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 |
|:----|:----|:------|:-----|:----|
|year|bool|无|❎|是否显示年列|
|month|bool|无|❎|是否显示月列|
|day|bool|无|❎|是否显示日列|
|hour|bool|无|❎|是否显示小时列|
|minute|bool|无|❎|是否显示分钟列|
|second|bool|无|❎|是否显示秒列|

## date 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 |
|:----|:----|:------|:-----|:----|
|start|string|无|❎|最小时间|
|end|string|无|❎|最大时间|
|select|string|无|❎|默认选中时间|

## controller 属性

| 属性 | 类型 | 默认值 |  说明 |
|:----|:----|:------|:----|
|close|func| |关闭picker|
|setSelectDate|func| |设置各列选中位置|



