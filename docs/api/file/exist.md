---
layout: default
title: exist
nav_order: 3
parent: 文件
grand_parent: API
---

# exist
## 说明
检查本地是否有指定文件

## 示例
```javascript
TinyAPI.file.existFile(
    {
        path: "/storage/emulated/0/sunmi/pay.mp3",
        callback: (res) => {
            console.log(res)
        }
    }
);
```

## 参数

| 属性名      | 类型       | 属性说明   | 必填  | 默认值 | 取值范围                                                         |
|:---------|:---------|:-------|:----|:----|:-------------------------------------------------------------|
| path     | string   | 文件绝对路径 | 是   |     |                                                              |
| callback | function | 结果回调   | 是   |     |                                                              |

## callback 入参

| 属性名 | 类型      | 属性说明     | 必填  | 默认值 | 取值范围                |
|:----|:--------|:---------|:----|:----|:--------------------|
| res | boolean | 是否存在指定文件 |     |     | true（存在），false（不存在） |

