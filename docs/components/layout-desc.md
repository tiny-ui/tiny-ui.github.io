---
layout: default
title: 布局说明
parent: 组件
nav_order: 2
---

# 布局说明

## 布局体系
是基于 Facebook 的 Yoga 引擎，兼容 Flexbox 布局，遵守 W3C 的规范。
具体可参考官网：[yoga](https://yogalayout.com/)

### 单位说明

### 颜色
颜色值目前仅支持 16进制、RGB、以及颜色值常量
16进制:'#ffffff'
常量:'red'
RGB:'rgb(255,255,255)'

### 尺寸
尺寸目前支持%、以及px等比换算
百分比计算:
取父容器宽高进行百分比计算.
例如:
parent.width * 30%
px等比换算:
设备屏幕宽度 / 画布基准值(通常是ide侧,或者设计稿宽度)*像素
简而言之进行UI绘制时,只需要传入画布上的px值即可完成适配工作.
