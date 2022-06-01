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

# 注册页面生命周期
## 说明
注册页面生命周期

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

// 页面回退
TinyAPI.base.registerLifecycle("onBack", () => {
    console.log("this is onBack callback");
})
```

## 参数

| 属性名      | 类型       | 属性说明                                                      | 必填 | 默认值                                                      | 取值范围   |
|:---------|:---------|:----------------------------------------------------------|:-----|:---------------------------------------------------------|:-------|
| name     | string   | 对应的生命周期名称                                                 | 是 |  | onStart、onResume、onPause、onStop、onDestroy、onBack |
| callback | function | 在对应时期执行的方法                                                | 是 |                                               |  |

{:toc}

# 取消注册生命周期
## 说明
取消注册生命周期

## 示例
```javascript
// 取消注册onStart事件
TinyAPI.base.unregisterLifecycle("onStart")

// 取消注册onResume事件
TinyAPI.base.unregisterLifecycle("onResume")

// 取消注册onPause事件
TinyAPI.base.unregisterLifecycle("onPause")

// 取消注册onStop事件
TinyAPI.base.unregisterLifecycle("onStop")

// 取消注册onDestroy事件
TinyAPI.base.unregisterLifecycle("onDestroy")

// 取消注册onBack事件
TinyAPI.base.unregisterLifecycle("onBack")
```

## 参数

| 属性名      | 类型       | 属性说明                                                     | 必填 | 默认值                                                     | 取值范围   |
|:---------|:---------|:---------------------------------------------------------|:-----|:--------------------------------------------------------|:-------|
| name     | string   | 对应的生命周期名称 | 是 |                                                         |                onStart、onResume、onPause、onStop、onDestroy、onBack                       |  |