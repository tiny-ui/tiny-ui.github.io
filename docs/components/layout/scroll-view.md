---
layout: default
title: ScrollView
nav_order: 5
parent: 布局
grand_parent: 组件
---

# ScrollView

## 说明

普通滚动布局组件。

## 示例
```javascript
function render(){
    return TinyDOM.createElement(
        "scrollView", {
            scrollAtBottom: () => {
                alert("bottom");
            },
            style: {
                backgroundColor: "black",
                width: "100%",
                height: "100%"
            }
        },
        addItem(0),
        addItem(1),
        addItem(2),
        addItem(3),
        addItem(4),
        addItem(5),
        addItem(6),
        addItem(7),
        addItem(8),
        addItem(9),
        addItem(10),
        addItem(11),
        addItem(12),
    );
}

function addItem(index) {

    return TinyDOM.createElement("column", {
        style: {

            width: "100%",
            height: 200,
        }
    }, TinyDOM.createElement("text", {
        style: {
            backgroundColor: index%2==0?"yellow":"red",
            width: "100%",
            height: 200,
        },
    }, "item " + index));
}

TinyUI.render(render());

```

## 参数

| 属性名     | 类型       | 属性说明      | 必填  | 默认值   | 取值范围                 |
|:--------|:---------|:----------|:----|:------|:---------------------|
| scrollAtBottom  | function   | 监听ScrollView滑动到底部 |    |       |           |

## 注意事项
orientation属性仅在scrollView创建时生效.
