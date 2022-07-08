---
layout: default
title: download
nav_order: 6
parent: 网络
grand_parent: API
---

# download

## 说明
下载指定url到对应手机路径下

## 示例
```javascript
TinyAPI.request.download(
    {
        url: "https://dogefs.s3.ladydaily.com/~/source/unsplash/photo-1527693381201-45771cd9716f?ixid=MnwxMjA3fDB8MHxzZWFyY2h8ODJ8fGdpcmwlMjBhbG9uZXxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80",
        dir: "/storage/emulated/0/Android/data/com.sunmi.elephant.test/cache",
        name: "pic.jpg",
        success: (current, total, done) => {
            console.log(current + total + done);
        },
        fail: (err) => {
            console.error(err);
        }
    }
)
```

## 入参

| 属性名     | 类型       | 属性说明        | 必填  | 默认值  | 取值范围                   |
|:--------|:---------|:------------|:----|:-----|:-----------------------|
| url     | string   | 下载地址        | 是   |      |  |
| dir     | string   | 存放下载文件地址    | 否   | 包路径下 |  |
| name    | string   | 文件名称（包含后缀名） | 是   |      |  |
| success | function | 下载进度回调      | 否   |      |  |
| fail    | function | 下载失败回调      | 否   |      |  |

### `success`参数

| 属性名     | 类型      | 属性说明    | 必填  | 默认值    | 取值范围                   |
|:--------|:--------|:--------|:----|:-------|:-----------------------|
| current | number  | 当前已下载大小 |     |  |  |
| total   | number  | 文件总大小   |     |  |  |
| done    | boolean | 是否已完成下载 |     |  |  |

### `fail`参数

| 属性名 | 类型     | 属性说明   | 必填  | 默认值    | 取值范围                   |
|:----|:-------|:-------|:----|:-------|:-----------------------|
| err | string | 下载失败信息 |     |  |  |