---
layout: default
title: navigateTo
nav_order: 1
parent: 导航
grand_parent: API

---

# navigateTo
## 说明
跳转到指定页面

## 使用
```javascript
TinyAPI.router.navigateTo(options)
```

## 示例
```javascript
// 跳转新页面（所有选项）
TinyAPI.router.navigateTo(
    {
//			schema + js文件path
        url: "page://cart.js",
        params: {
            a: 1,
            b: "aaaaaa",
        },
        closeSelf: false,
        success: function () {
            console.log("route success !")
        },
        fail: function (res){
            console.log("route faile, error code =" + res);
        },
        callback: function (res) {
            console.log(res);
        },
    }
);

// 跳转新页面（只填路径）
TinyAPI.router.navigateTo(
    {
        url: "page://com.sunmi.demo/pages/cache.js",
    }
);
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| option | Object | - | 是 | 路由跳转信息 | v0.3.0 |

### option参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| url | String | - | 是 | 跳转路径，格式：schema+绝对路径。schema：跳转类型（page -> 新页面） | v0.3.0 |
| params | String / Integer / Boolean / Object | - | 否 | 跳转页面传递过去的参数，类型支持String，Integer，Boolean, Object(Object只支持基础类型，不支持Function类型) | v0.3.0 |
| closeSelf | Boolean | false | 否 | 打开新页面是否关闭自身页面 | v0.3.0 |
| success | Function | - | 否 | 路径格式检验正确回调方法 | v0.3.0 |
| fail | Function | - | 否 | 路径格式不合法回调方法 | v0.3.0 |
| callback | Function | - | 否 | 当前页面关闭时，在上一页面回调方法（如果调用[@navigateBack](navigateBack)方法时有传递params，则会在此回调中将params回传） | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| res | Integer | - | - | 跳转失败返回错误码（400：url为空；401：schema格式错误；402：绝对路径为空） | v0.3.0 |

