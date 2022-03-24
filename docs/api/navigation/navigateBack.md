---
layout: default
title: back
nav_order: 2
parent: 导航
grand_parent: API

---

# back
## 说明
关闭当前页面，返回上一页面

## 使用
```javascript
TinyAPI.navigation.back(params);
```

## 示例
```javascript
TinyAPI.navigation.back("id = 12");
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| params | Object | - | 否 | 关闭当前页面时，回传给上一页面的参数，类型支持String，Integer，Boolean，Object（不支持Function类型回传） | v0.3.0 |

## 场景
```javascript
// 示例 A页面跳转B页面
TinyAPI.router.navigateTo("assets://b.js",
	{
		callback: onCallback,
	}
);

function onCallback(res: any){
	console.log(res);
}

// B页面关闭，并回传一个参数
TinyAPI.navigation.back("this is back msg!");

// 最后结果打印出来是：this is back msg!
```