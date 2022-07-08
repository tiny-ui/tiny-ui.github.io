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

<img src="/assets/images/create_module.jpg">

## 引入依赖
在`module`的`gradle`文件下，添加阿里云`maven url`

<img src="/assets/images/gradle_psw.jpg">

在`dependencies`下，添加最新版本的`tiny-core`, `tiny-annotation`, `tiny-compile`
`com.sunmi.android.elephant:tiny-annotation:0.1.+`
`com.sunmi.android.elephant:tiny-core:0.1.+`
`com.sunmi.android.elephant:tiny-compile:0.1.+`

<img src="/assets/images/gradle_dependencies.jpg">

## 添加功能服务
### 继承`TinyModule`，并实现相关功能代码

<img src="/assets/images/tinymodule.jpg">

### 定义`DSL`的模块名
给类添加注解`TinyModule`并标明模块名，如`device`。`DSL`调用时为`TinyAPI.device`

<img src="/assets/images/module_name.jpg">

### 构造函数不为空
#### 传入具体实现类
TinyModule注解的类构造函数需要传入实现类

<img src="/assets/images/construtor_impl.jpg">

在实现类添加注解`TinyModuleImpl`并标明传入的类名

<img src="/assets/images/create_impl.jpg">

#### 传入接口
TinyModule注解的类构造函数需要传入接口，实现类也实现了接口

<img src="/assets/images/construtor_interface.jpg">
<img src="/assets/images/create_interface.jpg">

在接口添加注解`TinyInterface`并标明传入类名

<img src="/assets/images/interface_annotation.jpg">

### 定义`DSL`的方法名
给方法添加注解，如方法名`funcImpl`。`DSL`调用时为`TinyAPI.device.funcImpl()`

<img src="/assets/images/method_name.jpg">

## 添加组件
### 继承`Component`或者`ComponentLayout`，并实现相关代码

<img src="/assets/images/create_component.jpg">

### 定义`DSL`的组件名
给类添加注解`TinyComponent`并标明组件名，如`custom`。`DSL`调用时为`TinyDOM.createElement("custom")`

<img src="/assets/images/component_name.jpg">

## 上传到`maven`
将实现的模块代码上传到`maven`

<img src="/assets/images/upload_maven.jpg">

## 将`maven`地址注册到商米开发者中心