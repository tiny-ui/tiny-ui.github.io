---
layout: default
title: Calendar
nav_order: 2
parent: 扩展
grand_parent: 组件
---

# Calendar

## 说明
日历视图,支持单选,多选,范围选择

## 示例
```javascript
function demo() {
    return TinyDOM.createElement("calendar", {
        showModule: "months",
        selectionColor: "pink",
        otherDates: {
            otherMonths: true,
            outOfRange: true,
            decoratedDisabled: true,
            selectDaysOutsideMonth: true,
        },
        selectionMode: "rangeOfDates",
        topBarVisible: true,
        minDate: "20210501",
        maxDate: "20230531",
        selectedDate: ["20220501"],
        showWeekDays: true,
        firstDay: "friday",
        pagingEnabled: true,
        dateTextStyle: {
            checkedColor: "red",
            pressedColor: "green",
            disableColor: "blue",
            defaultColor: "orange",
            size: 30,
        },
        weekDayTextStyle: {
            color:"red",
            size: 30,
        },
        headerTextStyle: {
            color:"red",
            size: 30,
        },
        onTitleClick:function (){
            TinyAPI.interact.showToast("点击标题");
        },
        onDateChanged:function (data){
            TinyAPI.interact.showToast("onDateChanged: "+data);
        },
        onDateLongClick:function (data){
            TinyAPI.interact.showToast("onDateLongClick: "+data)
        },
        onRangeSelected:function (data){
            console.log("onRangeSelected: "+data)
        },

        onMonthChanged:function (data){
            TinyAPI.interact.showToast("onMonthChanged: "+data)
        },
    });;
}
TinyUI.render(demo());
```

## Attribute 

|属性|类型|属性说明|是否必填|默认值|取值范围|
|:----|:----|:-----|:----|:----|:---|
|showModule|string|显示模式,周模式或者月模式|❎|"months"|"months","weeks"|
|selectionColor|string|选中的光标颜色|❎| |详见TinyUI支持颜色格式|
|otherDates|object|本月外其他日期显示|❎| | 详见otherDates 参数说明 |
|selectionMode|string|选择模式|❎|"singleDate"|"noSelection","singleDate","multipleDates","rangeOfDates"|
|topBarVisible|bool|是否显示title栏|❎|true||
|minDate|string|最小可选日期"|❎||示例:"20220520"|
|maxDate|string|最大可选日期|❎||示例:"20220520"|
|selectedDate|array|选中日期|❎||示例:["20220520","20220520"]|
|showWeekDays|bool|"显示顶部星期栏"|❎|true||
|firstDay|string|星期栏第一个星期名|❎|"sunday"|"monday","tuesday","wednesday","thursday","friday","saturday"|
|pagingEnabled|bool|是否允许滑动日历|❎|true||
|dateTextStyle|object|日期文本属性设置|❎||详见 dateTextStyle 参数|
|weekDayTextStyle|object|星期文本属性设置|❎||详见 weekDayTextStyle 参数|
|headerTextStyle|object|标题文本属性设置|❎||详见 headerTextStyle 参数|
|onTitleClick|func|标题点击事件|❎|||
|onDateChanged|func|选中数据改变回调|❎|||
|onDateLongClick|func|日期长按回调|❎|||
|onRangeSelected|func|选中范围改变回调|❎|||
|onMonthChanged|func|切换月份回调|❎|||



## otherDates 参数

|属性|类型|属性说明|是否必填|默认值|取值范围|
|:----|:----|:-----|:----|:----|:---|
|otherMonths|bool|显示前几个月和连续几个月的日期|❎|true||
|outOfRange|bool|显示超出最小-最大范围的日期。除非启用 otherMonths，否则这只会显示当月的天数。|❎|false||
|decoratedDisabled|bool|显示使用装饰器单独禁用的日期,这将仅显示当前月份以及最小和最大日期范围内的日期。|❎|true||
|selectDaysOutsideMonth|bool|允许用户单击未超出范围的其他月份的日期。 转到下一个或 如果单击当前月份之外的一天，则为上个月。 日子还需要 启用被选中|❎|true||


## dateTextStyle 参数

|属性|类型|属性说明|是否必填|
|:----|:----|:-----|:----|
|checkedColor|string|被选中时的颜色|❎|
|pressedColor|string|按下时的颜色|❎|
|disableColor|string|被禁用状态下的文字颜色|❎|
|defaultColor|string|无状态时的颜色|❎|
|size|number(int)|字体大小|❎|

## weekDayTextStyle 参数

|属性|类型|属性说明|是否必填|
|:----|:----|:-----|:----|
|color|string|颜色|❎|
|size|number(int)|字体大小|❎|

## headerTextStyle 参数

|属性|类型|属性说明|是否必填|
|:----|:----|:-----|:----|
|color|string|颜色|❎|
|size|number(int)|字体大小|❎|
