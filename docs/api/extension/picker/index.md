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

## 使用

```javascript
let controller = TinyAPI.picker.showPicker({})
```


## picker controller

controller 是调用 showPicker 函数返回的一个js object,用于控制picker.

```javascript
let controller = TinyAPI.picker.showPicker({
    columns: {
        column1: ["北京", "上海", "广州"],
        column2: ["朝阳区", "丰台区", "海淀区"],
        column3: ["朝阳a", "朝阳b", "朝阳c",]
    },
})

// 第一列默认选中位置
let column1DefaultValue = controller.column1DefaultValue()
// 第二列默认选中位置
let column2DefaultValue = controller.column2DefaultValue()
// 第三列默认选中位置
let column3DefaultValue = controller.column3DefaultValue()

// 北京,丰台区,朝阳 C
// 选中第1列的0个 item,第二列的第1个 item,第三列的第2个item.
controller.setSelect([0, 1, 2]);

// 关闭浮层
setTimeout(function () {
    controller.close();
}, 3000)

```



## linkage

是否开启联动

```javascript
TinyAPI.picker.showPicker({
    columns:
        {
            linkage: true,
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
        }
});
```



## textXOffset

设置滚轮x轴偏移量

```javascript
TinyAPI.picker.showPicker({
    // 设置x轴偏移量,分别给第一列设置10,第二列设置20,第三列设置10
    textXOffset: [10, 20, 10],
    columns:
        {
            linkage: true,
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
        }
});
```



## dividerType

设置分割线类型

```javascript
TinyAPI.picker.showPicker({
    dividerType: "warp",
    columns:
        {
            linkage: true,
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
        }
});
```



## dividerColor

设置分割线颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    dividerColor: "red",
    columns:
        {
            linkage: true,
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
        }
});
```



## textColorCenter

设置滚轮选中位置文本颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    textColorCenter: "red",
    columns:
        {
            linkage: true,
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
        }
});
```



## textColorOut

设置滚轮未选中文本颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    textColorOut: "white",
    columns:
        {
            linkage: true,
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
        }
});
```



## titleColor

标题文本颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    titleColor: "white",
    columns:
        {
            linkage: true,
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
        }
});
```



## cancelColor

取消按钮文本颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    cancelColor: "white",
    columns:
        {
            linkage: true,
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
        }
});
```



## submitColor

确认按钮颜色

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    submitColor: "white",
    columns:
        {
            linkage: true,
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
        }
});
```



## titleSize

标题大小

```javascript
TinyAPI.picker.showPicker({
    // 支持#ffffff 、red ,rgb(255,255,255),rgba(255,255,255,1)
    titleSize: 50,
    columns:
        {
            linkage: true,
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
        }
});
```



## subCalSize

取消 确认按钮大小.

```javascript
TinyAPI.picker.showPicker({

    subCalSize: 40,
    columns:
        {
            linkage: true,
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
        }
});
```



## contentSize

滚轮文字大小设置

```javascript
TinyAPI.picker.showPicker({

    contentSize: 40,
    columns:
        {
            linkage: true,
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
        }
});
```



## lineSpacingMultiplier

滚轮间距设置（1.2-2.0倍，此为文字高度的间距倍数)

```javascript
TinyAPI.picker.showPicker({

    lineSpacingMultiplier: 2.0,
    columns:
        {
            linkage: true,
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
        }
});
```



## defaultValue

滚轮默认选中位置

```javascript
TinyAPI.picker.showPicker({
    //设置第一列默认选中第0个,第二列第1个,第三列第0个
    defaultValue: [0, 1, 0],
    columns:
        {
            linkage: true,
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
        }
});
```



## closeOnMaskClick

是否允许点击蒙层关闭picker

```javascript
TinyAPI.picker.showPicker({
    //禁用点击蒙层关闭picker
    closeOnMaskClick: false,
    columns:
        {
            linkage: true,
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
        }
});
```



## confirmText

确认按钮文本.

```javascript
TinyAPI.picker.showPicker({
    confirmText: "confirmText",
    columns:
        {
            linkage: true,
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
        }
});
```



## cancelText

取消按钮文本

```javascript
TinyAPI.picker.showPicker({
    cancelText: "cancelText",
    columns:
        {
            linkage: true,
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
        }
});
```


## title

标题文本

```javascript
TinyAPI.picker.showPicker({

    title: "title",
    columns:
        {
            linkage: true,
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
        }
});
```



## onConfirm

确认选择回调

```javascript
TinyAPI.picker.showPicker({
    //column1Index 第一列选中索引.
    //column2Index 第二列选中索引.
    //column3Index 第三列选中索引.
    onConfirm: function (column1Index, column2Index, column3Index) {

    },
    columns:
        {
            linkage: true,
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
        }
});
```



## onSelect

滚轮选中回调

```javascript
TinyAPI.picker.showPicker({
    //column1Index 第一列选中索引.
    //column2Index 第二列选中索引.
    //column3Index 第三列选中索引.
    onSelect: function (column1Index, column2Index, column3Index) {

    },
    columns:
        {
            linkage: true,
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
        }
});
```



## onCancel

用户点击取消回调

```javascript
TinyAPI.picker.showPicker({
    onCancel: function () {

    },
    columns:
        {
            linkage: true,
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
        }
});
```



## onClose

picker 关闭回调

```javascript
TinyAPI.picker.showPicker({
    //column1Index 第一列选中索引.
    //column2Index 第二列选中索引.
    //column3Index 第三列选中索引.
    onClose: function () {
        
    },
    columns:
        {
            linkage: true,
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
        }
});
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



