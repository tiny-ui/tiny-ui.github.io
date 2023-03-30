---
layout: default 
title: TabView
nav_order: 4 
parent: 扩展 
grand_parent: 组件
---

# TabView

## 说明

Tab 容器

## 示例

```javascript
function demo() {
    return TinyDOM.createElement("column", {
            style: {
                backgroundColor: "green",
                width: "100%",
                height: "100%",
                alignItems: "center",
            }
        },
        TinyDOM.createElement("tabView", {
            style: {
                backgroundColor: "pick",
                width: "100%",
            },
            selection: 1,
            tabs: [{
                text: 'aa',
                selectedText: "bbb",
                bgColor: "#909090",
                selectedBgColor: "#a1a1a1"
            }, 'b', 'c', TinyDOM.createElement("text", {}, "d")]
        })
    );
}

TinyUI.render(demo());
```
## 截图
<img src="/assets/images/tabView.png"/>

## 参数

| 属性                 | 类型     | 默认值 | 取值范围 | 说明  |
|--------------------| -------- | ------ | ---- | --------------- |
| tabs               | array   |      |    | tab 标题数据         | 
| selection          | number   |      |    | 选中指定位置         |
| indicatorFullWidth | boolean   |      |   | 底部指示器是否占整个tab全宽         |

### tab参数
```javascript
// tabs 参数列表支持纯文字，icon 加文字和自定义组件
tabs = [
    "纯文字", 
    {
        text: "默认文字",
        selectedText: "选中文字",
        textColor: "#a2a2a2", //默认字体颜色
        textFontSize: "12",
        selectedTextFontSize: "14",
        icon: "", //图片URL, 目前只支持远程图片
        selectedTextColor: "#909090", //选中字体颜色
        bgColor: "#a2a2a2", //默认背景颜色
        selectedBgColor: "#909090" //选中背景颜色
    },
    TinyDOM.createElement("text", {}, "默认文字")]
```
