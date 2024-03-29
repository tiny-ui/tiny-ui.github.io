---
layout: default
title: 三方API开发
parent: 快速开始
nav_order: 3
---

# 介绍
使用该协议可以自由开发符合业务的功能API，并将其注册进大程序IDE内调用

# 接入流程
## 创建`Android Module`
创建对应的模块，在该模块实现需要导入到`tiny`工程的功能
(JDK版本 >= 1.8, gradle版本 >= 6.x)

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
`com.sunmi.android.elephant:tiny-annotation:x.x.x`
`com.sunmi.android.elephant:tiny-core:x.x.x`
`com.sunmi.android.elephant:tiny-compile:x.x.x`

## 添加包路径
在模块下的`AndroidManifest.xml`，添加对应的`package`

<img src="/assets/images/add_package_name.png">

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

### TinyModule包含方法

| 方法名                    | 方法描述                                               |
|:-----------------------|:---------------------------------------------------|
| getAndroidContext      | 获取当前页面Context上下文                                   |
| getJSContext           | 获取JS Context上下文                                    |
| getTinyContext         | 获取TinyContext接口                                    |
| getInstanceContext     | 获取Instance示例                                       |
| getDisplay             | 获取屏幕属性接口                                           |
| onModuleCreate         | 在页面创建自己时期调用                                        |
| onResult               | 等同于Activity的onResult()，在页面执行方法回调时期调用               |
| onBackPressed          | 等同于Activity的onBackPressed(), 在按下物理返回键时期调用          |
| onConfigurationChanged | 等同于Activity的onConfigurationChanged()，在页面发生配置变更时期调用 |
| onStart                | 等同于Activity的onStart()                              |
| onResume               | 等同于Activity的onResume()                             |
| onPause                | 等同于Activity的onPause()                              |
| onStop                 | 等同于Activity的onStop()                               |
| onDestroy              | 等同于Activity的onDestroy()                            |

### 定义`DSL`的模块名
给类添加注解`@TinyModule`并标明模块名，如`device`。`DSL`调用时为`API命名空间.device`。

| 属性名  | 类型      | 属性说明                      | 必填  | 默认值   |
|:-----|:--------|:--------------------------|:----|:------|
| name | string  | 在DSL层调用时输入的模块名（开头只能是英文字母） | 是   |       |
| lazy | boolean | 懒加载该模块                    | 否   | false |
| desc | string  | 对当前模块的信息描述                | 否   |       |

### 定义`DSL`的方法名
给方法添加注解`@TinyMethod`，如方法名`funcImpl`。`DSL`调用时为`API命名空间.device.funcImpl()`

| 属性名  | 类型      | 属性说明           | 必填  | 默认值   |
|:-----|:--------|:---------------|:----|:------|
| desc | string  | 对当前模块的信息描述 | 否   |       |

### 对方法入参注解
如果方法有入参，需要给参数添加注解`@TinyParams`。

| 属性名  | 类型      | 属性说明                     | 必填  | 默认值   |
|:-----|:--------|:-------------------------|:----|:------|
| name | string  | 在IDE显示入参的命名，没有则使用代码中的参数名 | 否   |       |
| desc | string  | 对当前入参的信息描述               | 否   |       |

<img src="/assets/images/create_method.png">

### 构造函数不为空(可选)
#### 传入具体实现类
TinyModule注解的类构造函数需要传入实现类

在接口类添加注解`TinyInterface`并标明传入的类名
在实现类添加注解`TinyInterfaceImpl`并标明传入的类名

<img src="/assets/images/create_interface.png">

### 常见问题
方法入参支持类型

| 类名                | 说明                                             |
|:------------------|:-----------------------------------------------|
| java.lang.Object  | 只能是Object类型，不能是自定义类                            |
| java.lang.String  |                                                |
| java.lang.Boolean |                                                |
| java.lang.Long    |                                                |
| java.lang.Double  |                                                |
| java.lang.Float   |                                                |
| java.lang.Integer |                                                |
| com.whl.quickjs.wrapper.JSObject  | 类似于自定义类，可通过getProperty / setProperty来设置/获取对应属性 |
| com.whl.quickjs.wrapper.JSFunction  | 类似于回调使用，入参格式为不定长度Object                        |
| com.whl.quickjs.wrapper.JSArray  | 类似于Array，可通过get / set来设置/获取指定下标参数              |

## 开发完成，上传到`maven`
### 配置上传仓库
在模块的build.gradle文件: 
1. plugins下，添加`id 'maven'`;
2. 添加上传阿里云仓库地址

```text
uploadArchives {
    repositories {
        mavenDeployer {
            repository(url: "https://packages.aliyun.com/maven/repository/2302879-release-oY4Gsc/"){
                authentication(
                        userName: "63758ec075c5eada02fc8225",
                        password: "k9n]hZq7tw7l"
                )
            }
            pom.groupId = "你的group id"
            pom.artifactId = "你的模块 id"
            pom.version = "你的版本号"
        }
    }
}
```

### 上传到`maven`
将实现的模块代码上传到指定私有云`maven`仓库

<img src="/assets/images/upload_maven.png">

### 将`maven`地址注册到商米开发者中心，同时将模块下生成的meta.json一并上传至开发者中心

<img src="/assets/images/upload_meta.png">