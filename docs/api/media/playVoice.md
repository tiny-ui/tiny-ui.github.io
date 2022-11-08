---
layout: default
title: play voice
nav_order: 3
parent: 媒体
grand_parent: API
---

# playVoice
## 说明
播放手机中的音频文件

## 示例
```javascript
TinyAPI.media.playVoice(
    {
        filePath: "请付款_01.mp3",
        type: "assets",
        success: function (){},
        fail: function (res){console.log(res)},
        complete: function (){}
    }
);
```

## 入参

| 属性名      | 类型       | 属性说明                                                                                                                                  | 必填  | 默认值    | 取值范围           |
|:---------|:---------|:--------------------------------------------------------------------------------------------------------------------------------------|:----|:-------|:---------------|
| filePath | string   | SdCard音频文件完整路径（"/storage/emulated/0/Sunmi/3185614238.mp3"），或assets内音频文件名称（”3185614238.mp3）注：在Android6.0以上设备播放SDCard卡音频文件，需要动态申请内存读写权限 | 是   | -      |                |
| type     | string   | 文件路径类型，=scared表示SDCard里的文件，=assets表示apk里asset文件下的文件                                                                                   | 否   | sdcard | sdcard, assets |
| success  | function | 调用成功回调                                                                                                                                | 否   | -      | true, false    |
| fail     | function | 调用失败回调                                                                                                                                | 否   | -      |                |
| complete | function | 调用结束回调                                                                                                                                | 否   | -      |                |

## `fail`入参

| 属性名    | 类型     | 属性说明   | 必填  | 默认值     | 取值范围                 |
|:-------|:-------|:-------|:----|:--------|:---------------------|
| res    | string | 调用失败原因 |     |  |  |
