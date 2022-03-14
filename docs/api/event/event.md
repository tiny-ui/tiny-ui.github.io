---
layout: default
title: 页面生命周期
nav_order: 1
parent: 应用级事件
grand_parent: API
---

# 页面生命周期
## 说明
注册app页面生命周期

## 使用
```javascript
TinyAPI.lifecycle.register(name, callback);
```

## 示例
```javascript
// 页面加载完成
TinyAPI.lifecycle.register("onCreate", () => {
    console.log("this is onCreate callback");
})

// A页面跳转到B页面后
TinyAPI.lifecycle.register("onStop", () => {
    console.log("this is onStop callback");
})

// 页面被关闭前期
TinyAPI.lifecycle.register("onDestroy", () => {
    console.log("this is onDestroy callback");
})

// 页面横竖屏改变
TinyAPI.lifecycle.register("onChanged", () => {
    console.log("this is onCreate callback");
})
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| name | String | - | 是 | 对应的生命周期名称（目前支持onCreate、onStop、onDestroy、onChanged四种） | v0.3.0 |
| callback | Function | - | 是 | 在对应时期执行的方法 | v0.3.0 |
