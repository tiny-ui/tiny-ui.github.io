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
在新建`module`的`gradle`文件下的`repositories`，添加阿里云`maven url`

```text
maven {
            url 'https://packages.aliyun.com/maven/repository/2140287-release-Q0hGNK/'
            credentials {
                username '6359fe31eb6ad002b1d7999a'
                password 'LOwPng1O)0Jp'
            }
        }
```

在`dependencies`下，添加最新版本的`tiny-core`, `tiny-annotation`, `tiny-compile`，例如
`com.sunmi.android.elephant:tiny-annotation:0.4.7-alpha-19`
`com.sunmi.android.elephant:tiny-core:0.4.7-alpha-19`
`com.sunmi.android.elephant:tiny-compile:0.4.7-alpha-19`

### 常见问题
出现获取不到依赖情况：
1. 可以尝试把拉取阿里云的maven放到repositories首位
2. 把offline模式打开

## 添加命名空间
在新建`module`的`gradle`文件的`defaultConfig`，新增以下代码
```text
javaCompileOptions {
            annotationProcessorOptions {
                arguments = ["PROJECT_DIR" : project.projectDir.path,"COMPONENT_SPACE":"在开发者中心提供的组件命名空间的值","API_SPACE":"在开发者中心提供的API命名空间的值"]
            }
}
```

<img src="/assets/images/gradle_space.png">

## 添加功能服务
### 继承`TinyModule`，并实现相关功能代码

```text
public class APIModule extends TinyModule {

}
```

### 定义`DSL`的模块名
给类添加注解`TinyModule`并标明模块名，如`device`。`DSL`调用时为`命名空间.device`。

| 属性名  | 类型      | 属性说明           | 必填  | 默认值   |
|:-----|:--------|:---------------|:----|:------|
| name | string  | 在DSL层调用时输入的模块名 | 是   |       |
| lazy | boolean | 懒加载该模块 | 否   | false |
| desc | string  | 对当前模块的信息描述 | 否   |       |

<img src="/assets/images/module_name.png">

### 构造函数不为空(可选)
#### 传入具体实现类
TinyModule注解的类构造函数需要传入实现类

<img src="/assets/images/constructor_impl.png">

在接口类添加注解`TinyInterface`并标明传入的类名
在实现类添加注解`TinyInterfaceImpl`并标明传入的类名

<img src="/assets/images/create_interface.png">
<img src="/assets/images/create_impl.png">

### 定义`DSL`的方法名
给方法添加注解，如方法名`funcImpl`。`DSL`调用时为`命名空间.device.funcImpl()`

| 属性名  | 类型      | 属性说明           | 必填  | 默认值   |
|:-----|:--------|:---------------|:----|:------|
| desc | string  | 对当前模块的信息描述 | 否   |       |

<img src="/assets/images/create_method.png">

## 添加组件
### 继承`Component`或者`ComponentLayout`，并实现相关代码

### 定义`DSL`的组件名
给类添加注解`TinyComponent`并标明组件名，如`custom`。`DSL`调用时为`TinyDOM.createElement("custom")`

<img src="/assets/images/create_component.png">

## 上传到`maven`
将实现的模块代码上传到`maven`

<img src="/assets/images/upload_maven.png">

## 将`maven`地址注册到商米开发者中心，同时将模块下生成的meta.json一并上传至开发者中心