---
layout: default
title: 页面生命周期
nav_order: 2
parent: 基础
grand_parent: API
---

# 应用级事件

{: .no_toc }

## 目录

{: .no_toc .text-delta }

1. TOC
{:toc}

# 页面生命周期

## 说明
注册页面生命周期

## 使用
```javascript
TinyAPI.base.registerLifecycle(name, callback);
```

## 示例
```javascript
// 页面正在加载，由不可见变为可见
TinyAPI.base.registerLifecycle("onStart", () => {
    console.log("this is onStart callback");
})

// 页面加载完成，并显示在屏幕上
TinyAPI.base.registerLifecycle("onResume", () => {
    console.log("this is onResume callback");
})

// 页面正在停止，并且即将进入不可见状态
TinyAPI.base.registerLifecycle("onPause", () => {
    console.log("this is onPause callback");
})

// 页面已经停止，并处于不可见状态
TinyAPI.base.registerLifecycle("onStop", () => {
    console.log("this is onStop callback");
})

// 页面销毁
TinyAPI.base.registerLifecycle("onDestroy", () => {
    console.log("this is onDestroy callback");
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明                                                       | 最低版本支持 |
|:----|:----|:------|:-----|:---------------------------------------------------------|:-----------|
| name | String | - | 是 | 对应的生命周期名称（目前支持onStart、onResume、onPause、onStop、onDestroy） | v0.3.0 |
| callback | Function | - | 是 | 在对应时期执行的方法                                               | v0.3.0 |
