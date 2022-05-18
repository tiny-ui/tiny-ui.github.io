---
layout: default
title: upload
nav_order: 5
parent: 网络
grand_parent: API

---

# upload
## 说明
上传图片

## 示例
```javascript
var data = [
    {
        "bucketId":1028075469,
        "chooseModel":1,
        "compressPath":"/storage/emulated/0/Android/data/com.sunmi.elephant.yzk/cache/luban_disk_ca...",
        "compressed":true,
        "cropImageHeight":0,
        "cropImageWidth":0,
        "cropOffsetX":0,
        "cropOffsetY":0,
        "cropResultAspectRatio":0,
        "dateAddedTime":1651384785,
        "duration":0,
        "fileName":"Screenshot_20220501_135941_com.tencent.mm.png",
        "height":521,
        "id":2069553,
        "isChecked":false,
        "isCut":false,
        "isEditorImage":false,
        "isGalleryEnabledMask":false,
        "isMaxSelectEnabledMask":false,
        "isOriginal":true,
        "mimeType":"media/png",
        "num":1,
        "originalPath":"content://media/external/images/media/2069553",
        "parentFolderName":"Screenshots",
        "path":"content://media/external/images/media/2069553",
        "position":15,
        "realPath":"/storage/emulated/0/Pictures/Screenshots/Screenshot_20220501_135941_com.ten...",
        "sandboxPath":"/storage/emulated/0/Android/data/com.sunmi.elephant.yzk/cache/luban_disk_ca...",
        "size":273130,
        "width":659
    }
];
TinyAPI.request.upload(
    {
        file: data, // 只上传data里的realPath参数
        url: "http://max-test.sunmi.com/api/v1/upload",
        upload: "uploadFile",
        headers: {
            "user": "%7B%22activated%22%3Atrue%2C%22did%22%3A%227411%22%2C%22",
            "uid": "SM001",
        },
        params: {
            version: "1.0",
            method: "create"
        },
        form: {
            request: {
                name: "picture.jpg",
                env: "debug"
            },
            context: {
                projectCode: "20331gq",
                projectSubType: "APP"
            }
        },
        success: function (res) {
            console.log(res);
        },
        fail: function (msg) {
            console.log(msg);
        }
    }
);
```
---
success示例
{: .text-red-000 }
```json
{
  "url":"http://max-beluga.dev.sunmi.com/api/v1/upload?version=1.0&method=upload&pat...",
  "status":200,
  "headers":{
    "namesAndValues":[
      "Content-Type",
      "application/json;charset\u003dUTF-8",
      "Tr..."
    ]
  },
  "body":{
    "code":1,
    "data":{
      "downloadUrl":"https://max-beluga.oss-accelerate.aliyuncs.com/assets/develop/static/TNT220...",
      "fileCode":"RES220518vjfzs83h2eu4v5idle142htag",
      "fileName":"RES220518vjfzs83h2eu4v5idle142htag.png",
      "name":"pic.jpg",
      "status":true
    },
    "success":true
  }
}
```

## 参数

| 属性名     | 类型       | 属性说明      | 必填  | 默认值   | 取值范围                 |
|:--------|:---------|:----------|:----|:------|:---------------------|
| file    | Arrays   | 上传图片      | 是   |       |  |
| url     | String   | 上传地址      | 是   |       |           |
| upload  | String   | 上传图片对应参数名 | 是   |       |           |
| headers | Object   | 网络请求头     | 否   |       |   |
| params  | Object   | 网络请求数据体   | 否   |       |   |
| form    | Object   | 网络form结构体 | 是   |       |   |
| success | Function | 上传成功回调    | 否   |       |   |
| fail    | Function | 上传失败回调    | 否   |       |   |

### success参数

| 属性名     | 类型       | 属性说明      | 必填  | 默认值   | 取值范围
|:----|:----|:------|:-----|:----|:-----------|:-----|
| url | String | 网络请求地址 |  |  | |:-----|
| status | Integer | 网络请求结果状态码 |  |  | |:-----|
| headers | Object | 网络请求结果headers |  |  |  |:-----|
| body | Object | 网络请求结果 |  |  |  |:-----|