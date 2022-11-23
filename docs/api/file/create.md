---
layout: default
title: create
nav_order: 1
parent: 文件
grand_parent: API
---

# create
## 说明
创建新文件（相同路径的文件将会删除，并重新创建新的）

## 示例
```javascript
TinyAPI.file.create(
    {
        path: "sunmi",
        name: "abc.txt",
        pathType: 1,
        content: "sunmi is a global company",
        success: (res) => {
            console.log(res)
        },
        fail: (res) => {
            console.log(res)
        }
    }
);
```

## 参数

| 属性名      | 类型       | 属性说明     | 必填  | 默认值 | 取值范围                                                         |
|:---------|:---------|:---------|:----|:----|:-------------------------------------------------------------|
| path     | string   | 文件保存路径   | 否   |     |                                                              |
| name     | string   | 文件名（含后缀） | 是   |     |                                                              |
| pathType | number   | 使用路径类型   | 否   | 0   | 0：自定义文件绝对路径（path为必填）<br/> 1：该apk的缓存相对路径<br/> 2：sd卡的apk缓存相对路径 |
| success  | function | 成功回调     | 否   |     |                                                              |
| fail     | function | 失败回调     | 否   |     |                                                              |
| content  | string   | 写入文件内容   | 是   |     |                                                              |


