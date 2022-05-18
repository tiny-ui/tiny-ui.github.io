---
layout: default 
title: picker 
nav_order: 4 
parent: 扩展 
grand_parent: API
---

# picker
## 说明

展示选择器弹窗视图.

## 基本使用

```javascript
let controller = TinyAPI.picker.showPicker({
    //禁用点击蒙层关闭picker
    closeOnMaskClick: false,
    // 设置x轴偏移量,分别给第一列设置10,第二列设置20,第三列设置10
    textXOffset: [10, 20, 10],
    // 设置分割线类型 
    dividerType: "warp",
    // 设置分割线颜色 
    dividerColor: "red",
    // 设置滚轮选中文本颜色 
    textColorCenter: "red",
    // 设置滚轮选未选中文本颜色 
    textColorOut: "white",
    // 设置标题颜色 
    titleColor: "white",
    // 设置取消按钮颜色
    cancelColor: "white",
    // 取消按钮文本
    cancelText: "cancelText",
    // 确认按钮颜色    
    submitColor: "white",
    // 确认按钮文案
    confirmText: "confirmText",
    // 标题文本大小
    titleSize:20,
    // 标题文本
    title: "title",
    // 确认、取消 文本大小
    subCalSize: 40,
    // 滚轮文字大小
    contentSize: 40,
    // 滚轮间距设置（1.2-2.0倍，此为文字高度的间距倍数)
    lineSpacingMultiplier:[2.0,1.0,1.0],
    // 滚轮默认选中位置 设置第一列默认选中第0个,第二列第1个,第三列第0个
    defaultValue:[0,1,0],
    columns: {
        column1: ["北京", "上海", "广州"],
        column2: ["朝阳区", "丰台区", "海淀区"],
        column3: ["朝阳a", "朝阳b", "朝阳c",]
    },
    // 确认回调
    onConfirm: function (column1Index, column2Index, column3Index) {
        //column1Index 第一列选中索引.
        //column2Index 第二列选中索引.
        //column3Index 第三列选中索引.
    },
    // 选中回调
    onSelect: function (column1Index, column2Index, column3Index) {
        //column1Index 第一列选中索引.
        //column2Index 第二列选中索引.
        //column3Index 第三列选中索引.
    },
    // 取消回调
    onCancel: function () {

    },
    // 关闭回调
    onClose: function () {

    },
})

// 第一列默认选中位置
let column1DefaultValue = controller.column1DefaultValue
// 第二列默认选中位置
let column2DefaultValue = controller.column2DefaultValue
// 第三列默认选中位置
let column3DefaultValue = controller.column3DefaultValue

// 北京,丰台区,朝阳 C
// 选中第1列的0个 item,第二列的第1个 item,第三列的第2个item.
controller.setSelect(0, 1, 2);

// 关闭浮层
setTimeout(function () {
    controller.close();
}, 3000)

```


## 滚轮联动

```javascript
let controller = TinyAPI.picker.showPicker({
    //禁用点击蒙层关闭picker
    closeOnMaskClick: false,
    // 设置x轴偏移量,分别给第一列设置10,第二列设置20,第三列设置10
    textXOffset: [10, 20, 10],
    // 设置分割线类型 
    dividerType: "warp",
    // 设置分割线颜色 
    dividerColor: "red",
    // 设置滚轮选中文本颜色 
    textColorCenter: "yellow",
    // 设置滚轮选未选中文本颜色 
    textColorOut: "red",
    // 设置标题颜色 
    titleColor: "red",
    // 设置取消按钮颜色
    cancelColor: "red",
    // 取消按钮文本
    cancelText: "cancelText",
    // 确认按钮颜色    
    submitColor: "red",
    // 确认按钮文案
    confirmText: "confirmText",
    // 标题文本大小
    titleSize:15,
    // 标题文本
    title: "title",
    // 确认、取消 文本大小
    subCalSize: 10,
    // 滚轮文字大小
    contentSize: 10,
    // 滚轮间距设置（1.2-2.0倍，此为文字高度的间距倍数)
    lineSpacingMultiplier:[2.0,1.0,1.0],
    // 滚轮默认选中位置 设置第一列默认选中第0个,第二列第1个,第三列第0个
    defaultValue:[0,1,0],
    // 开启联动
    linkage: true,
    columns:  {
        //注意这里的多维数组
        column1: ["北京", "上海", "广州"],
        column2: [
            ["朝阳区", "丰台区", "海淀区"],
            ["浦东", "杨浦"],
            ["白云", "天河", "越秀"],
        ],
        column3: [
            [
                ["朝阳a", "朝阳b", "朝阳c",],
                ["丰台a", "丰台b", "丰台c"],
                ["海淀a", "海淀b", "海淀c",],
            ],
            [
                ["浦东a", "浦东b", "浦东c", "浦东d",],
                ["杨浦a", "杨浦b", "杨浦c", "杨浦d",],
            ],
            , [
                ["白云a", "白云b", "白云c"],
                ["天河a", "天河b", "天河c"],
                ["越秀a"],
            ],
        ]
    },
    // 确认回调
    onConfirm: function (column1Index, column2Index, column3Index) {
        //column1Index 第一列选中索引.
        //column2Index 第二列选中索引.
        //column3Index 第三列选中索引.
    },
    // 选中回调
    onSelect: function (column1Index, column2Index, column3Index) {
        //column1Index 第一列选中索引.
        //column2Index 第二列选中索引.
        //column3Index 第三列选中索引.
    },
    // 取消回调
    onCancel: function () {

    },
    // 关闭回调
    onClose: function () {

    },
})

// 第一列默认选中位置
let column1DefaultValue = controller.column1DefaultValue
// 第二列默认选中位置
let column2DefaultValue = controller.column2DefaultValue
// 第三列默认选中位置
let column3DefaultValue = controller.column3DefaultValue

// 北京,丰台区,朝阳 C
// 选中第1列的0个 item,第二列的第1个 item,第三列的第2个item.
controller.setSelect(0, 1, 2);

// 关闭浮层
setTimeout(function () {
    controller.close();
}, 3000)

```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
|columns|object|无|✅|列数据(详见demo)|v0.4.0|
|textXOffset|array|无|❎|设置X轴偏移量，形成弧度(详见Demo)|v0.4.0|
|dividerType|string|'fill'|❎|分隔线类型,支持:'fill','warp'|v0.4.0|
|dividerColor|string|无|❎|分隔线颜色|v0.4.0|
|textColorCenter|string|无|❎|选中项文字颜色设置|v0.4.0|
|textColorOut|string|无|❎|未选中项文字颜色设置|v0.4.0|
|titleColor|string|无|❎|标题文字颜色设置|v0.4.0|
|cancelColor|string|无|❎|取消按钮颜色设置|v0.4.0|
|submitColor|string|无|❎|确认文字颜色设置|v0.4.0|
|titleSize|number(整数)|无|❎|标题文字大小设置|v0.4.0|
|subCalSize|number(整数)|无|❎|确定、取消按钮大小设置|v0.4.0|
|contentSize|number(整数)|无|❎|滚轮文字大小设置|v0.4.0|
|lineSpacingMultiplier|double|无|❎|滚轮间距设置（1.2-2.0倍，此为文字高度的间距倍数）|v0.4.0|
|linkage|bool|false|❎|是否开启列表联动|v0.4.0|
|defaultValue|array|无|❎|默认选中位置|v0.4.0|
|closeOnMaskClick|bool|true|❎|是否允许点击浮层关闭picker|v0.4.0|
|confirmText|array|无|❎|确认按钮文案|v0.4.0|
|cancelText|array|无|❎|取消按钮文案|v0.4.0|
|title|array|无|❎|标题文案|v0.4.0|
|onConfirm|func|无|❎|确认选中回调|
|onSelect|func|无|❎|选中回调|
|onCancel|func|无|❎|取消按钮回调|
|onClose|func|无|❎|picker关闭回调|

## columns 明细

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
|column1|array|无|✅|第一列数据|v0.4.0|
|column2|array|无|✅|第二列数据|v0.4.0|
|column3|array|无|✅|第三列数据|v0.4.0|
|column1Label|string|无|❎|第一列数据单位|v0.4.0|
|column2Label|string|无|❎|第二列数据单位|v0.4.0|
|column3Label|string|无|❎|第三列数据单位|v0.4.0|

## controller 属性

| 属性 | 类型 | 默认值 |  说明 |
|:----|:----|:------|:----|
|column1DefaultValue|number|0|第一列默认选中位置|
|column2DefaultValue|number|0|第二列默认选中位置|
|column3DefaultValue|number|0|第三列默认选中位置|
|close|func| |关闭picker|
|setSelect|func| |设置各列选中位置|



