---
layout: default 
title: ViewPage 
nav_order: 5 
parent: 扩展 
grand_parent: 组件
---

# PageView

## 说明

翻页组件，内置支持 TabView，提供 Tab + PageView 的联动功能

## 示例

```javascript
app = () => {
    return TinyDOM.createElement("pageView", {
        tabView: () => {
            return TinyDOM.createElement("tabView", {
                style: {
                    backgroundColor: "pick",
                    width: "100%",
                },
                tabs: [{
                    "text": 'aa',
                    "selectedText": "bbb",
                    bgColor: "#909090",
                    selectedBgColor: "#a1a1a1"
                }, 'b', 'c', TinyDOM.createElement("text", {}, "d")]
            })
        },
        renderItem: (index) => {
            return TinyDOM.createElement("text", {}, "sunmi = " + index);
        },
        itemCount: 1,
        selection: 1,
        onPageChange: (index) => {
            console.log(index)
        }
    })
}
TinyUI.render(app());
```

## 参数

| 属性          |    类型    | 必填  | 默认值 | 取值范围 |      说明      |
|-------------|:--------:|:---:|:---:|:----:|:------------:|
| tabView     | function |     |     |      |   tab 标题数据   |
| renderItem  | function |  是  |     |      |   需要渲染的组件    |
| itemCount   |  number  |  是  |  1  |      |  展示页面组件的数量   |
| onPageChange | function |     |     |      | 页面组件切换时的监听事件 |
| selecion    |  number  |     |  0  |      |   设置选中的页面    |
