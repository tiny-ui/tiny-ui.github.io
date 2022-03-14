---
layout: default
title: navigateBack
nav_order: 2
parent: 导航
grand_parent: API

---

# navigateBack
## 说明
关闭当前页面，返回上一页面

## 使用
```javascript
TinyAPI.router.navigateBack(params);
```

## 示例
```javascript
TinyAPI.router.navigateBack("id = 12");
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| params | Object | - | 否 | 关闭当前页面时，回传给上一页面的参数，类型支持String，Integer，Boolean，Object（不支持Function类型回传） | v0.3.0 |

### option参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| url | String | - | 是 | 跳转路径，格式：schema+绝对路径。schema：跳转类型（page -> 新页面） | v0.3.0 |
| params | String / Integer / Boolean / Object | - | 否 | 跳转页面传递过去的参数，类型支持String，Integer，Boolean, Object(Object只支持基础类型，不支持Function类型) | v0.3.0 |
| closeSelf | Boolean | false | 否 | 打开新页面是否关闭自身页面 | v0.3.0 |
| success | Function | - | 否 | 路径格式检验正确回调方法 | v0.3.0 |
| fail | Function | - | 否 | 路径格式不合法回调方法 | v0.3.0 |
| callback | Function | - | 否 | 当前页面关闭时，在上一页面回调方法（如果调用@navigateBack方法时有传递params，则会在此回调中将params回传） | v0.3.0 |

### fail参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
| res | Integer | - | - | 跳转失败返回错误码（400：url为空；401：schema格式错误；402：绝对路径为空） | v0.3.0 |

## 场景
```javascript
// 示例 A页面跳转B页面
TinyAPI.router.navigateTo(
	{
		url: "page://b.js",
		callback: onCallback,
	}
);

function onCallback(res: any){
	console.log(res);
}

// B页面关闭，并回传一个参数
TinyAPI.router.navigateBack("this is back msg!");

// 最后结果打印出来是：this is back msg!
```