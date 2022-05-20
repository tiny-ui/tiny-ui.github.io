---
layout: default
title: register
nav_order: 1
parent: 事件
grand_parent: API
---

# register
## 说明
注册当前页面监听事件

## 示例
```javascript
TinyAPI.event.register(
    "back", [
        function (res) {
            console.log("action1 = " + res);
        },
        function (res) {
            console.log("action2 = " + res);
        }
    ]
);
```

## 参数

| 属性名          | 类型     | 属性说明   | 必填  | 默认值     | 取值范围                 |
|:-------------|:-------|:-------|:----|:--------|:---------------------|
| name         | string | 事件名称   | 是   |  |  |
| events       | arrays | 监听事件列表 | 是   |     |           |

## events入参

| 属性名    | 类型     | 属性说明      | 必填  | 默认值     | 取值范围                 |
|:-------|:-------|:----------|:----|:--------|:---------------------|
| res    | object | 调用该事件传入参数 |     |  |  |

