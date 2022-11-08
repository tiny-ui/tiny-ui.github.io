---
layout: default
title: resume voice
nav_order: 6
parent: 媒体
grand_parent: API
---

# resumeVoice
## 说明
恢复当前语音播放

## 示例
```javascript
TinyAPI.media.resumeVoice(
    {
        success: function (){},
        fail: function (res){console.log(res)},
        complete: function (){}
    }
);
```

## 入参

| 属性名      | 类型       | 属性说明                                                                                                                                  | 必填  | 默认值    | 取值范围           |
|:---------|:---------|:--------------------------------------------------------------------------------------------------------------------------------------|:----|:-------|:---------------|
| success  | function | 调用成功回调                                                                                                                                | 否   | -      | true, false    |
| fail     | function | 调用失败回调                                                                                                                                | 否   | -      |                |
| complete | function | 调用结束回调                                                                                                                                | 否   | -      |                |

## `fail`入参

| 属性名    | 类型     | 属性说明   | 必填  | 默认值     | 取值范围                 |
|:-------|:-------|:-------|:----|:--------|:---------------------|
| res    | string | 调用失败原因 |     |  |  |
