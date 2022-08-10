---
layout: default
title: 三方模块开发
parent: 快速开始
nav_order: 3
---

# 介绍
使用该能力可以自由开发符合业务的功能和组件，并将其注册进大程序IDE调用

# 接入流程
## 创建`Android Module`
创建对应的模块，在该模块实现需要导入到`tiny`工程的功能

<img src="/assets/images/create_module.png">

## 引入依赖
在`module`的`gradle`文件下，添加阿里云`maven url`

<img src="/assets/images/gradle_psw.png">

在`dependencies`下，添加最新版本的`tiny-core`, `tiny-annotation`, `tiny-compile`
`com.sunmi.android.elephant:tiny-annotation:+`
`com.sunmi.android.elephant:tiny-core:+`
`com.sunmi.android.elephant:tiny-compile:+`

<img src="/assets/images/gradle_dependencies.png">

## 添加功能服务
### 继承`TinyModule`，并实现相关功能代码

### 定义`DSL`的模块名
给类添加注解`TinyModule`并标明模块名，如`device`。`DSL`调用时为`TinyAPI.device`。
lazy表示是否懒加载该模块，不填默认为false

<img src="/assets/images/module_name.png">

### 构造函数不为空
#### 传入具体实现类
TinyModule注解的类构造函数需要传入实现类

<img src="/assets/images/constructor_impl.png">

在接口类添加注解`TinyInterface`并标明传入的类名
在实现类添加注解`TinyInterfaceImpl`并标明传入的类名

<img src="/assets/images/create_interface.png">
<img src="/assets/images/create_impl.png">

### 定义`DSL`的方法名
给方法添加注解，如方法名`funcImpl`。`DSL`调用时为`TinyAPI.device.funcImpl()`

<img src="/assets/images/create_method.png">

## 添加组件
### 继承`Component`或者`ComponentLayout`，并实现相关代码

### 定义`DSL`的组件名
给类添加注解`TinyComponent`并标明组件名，如`custom`。`DSL`调用时为`TinyDOM.createElement("custom")`

<img src="/assets/images/create_component.png">

## 上传到`maven`
将实现的模块代码上传到`maven`

<img src="/assets/images/upload_maven.png">

## 将`maven`地址注册到商米开发者中心