---
layout: default
title: read
nav_order: 2
parent: 文件
grand_parent: API
---

# read
## 说明
读取手机内存在的文件内容

## 示例
```javascript
TinyAPI.file.read(
    {
        path: "sunmi",
        name: "abc.txt",
        pathType: 1,
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

| 属性名      | 类型       | 属性说明       | 必填  | 默认值 | 取值范围                                                         |
|:---------|:---------|:-----------|:----|:----|:-------------------------------------------------------------|
| path     | string   | 文件保存路径     | 否   |     |                                                              |
| name     | string   | 文件名（含后缀）   | 是   |     |                                                              |
| pathType | number   | 使用路径类型     | 否   | 0   | 0：自定义文件绝对路径（path为必填）<br/> 1：该apk的缓存相对路径<br/> 2：sd卡的apk缓存相对路径 |
| success  | function | 成功读取文件内容回调 | 是   |     |                                                              |
| fail     | function | 失败回调       | 否   |     |                                                              |


