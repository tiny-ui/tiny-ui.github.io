---
layout: default
title: get
nav_order: 1
parent: 网络
grand_parent: API

---

# get
## 说明
发送网络请求GET

## 使用
```javascript
TinyAPI.request.get(option);
```

## 示例
```javascript
TinyAPI.request.get(
    {
        url: "http://codecworld.pro/cw/employer/all",
        headers: {
            "authorization": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIyMCIsImlzcyI6ImN3LmNvbSIsImp3dC11c2VyLW5hbWUta2V5IjoiZW1wbG95ZXIsZ2FtYmxlciIsImV4cCI6MTY0MjIxODM5MSwiaWF0IjoxNjQxOTU5MTkxfQ.eVi69Yk6a9WiNTX43knvcnpxeStWcqYPPH0mmUfo0tY",
            "refresh_token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIyMCxwYyIsImlzcyI6ImN3LmNvbSIsImp3dC11c2VyLW5hbWUta2V5IjoiZW1wbG95ZXIsZ2FtYmxlciIsImV4cCI6MTY0MjIxODM5MSwiaWF0IjoxNjQxOTU5MTkxfQ.cz6HP58X3DUQQ6eqyRWLu1DTtFyZTF1JCcR5RKNrqs8",
        },
        timeout: 3000,
        responseType: "json",
        success: function (res) {
            console.log(res.url);
            console.log(res.status);
            console.log(res.headers);
            console.log(res.body);
        },
        fail: function (res) {
            console.log(res);
        }
    }
);
```
---
success示例
{: .text-red-000 }
```json
{
    "headers":{
        "Connection":"keep-alive",
        "Content-Type":"application/json;charset=UTF-8",
        "Date":"Fri,14Jan202210:46:05GMT",
        "Server":"nginx/1.20.1",
        "Set-Cookie":"rememberMe=deleteMe;Path=/;Max-Age=0;Expires=Thu,13-Jan-202210:46:05GMT",
        "Transfer-Encoding":"chunked",
        "Vary":"Access-Control-Request-Headers"
    },
    "status":200,
    "body":{
        "code":200,
        "msg":"操作成功",
        "data":{
            "totalRows":21,
            "totalPages":7,
            "pageNum":1,
            "pageSize":3,
            "curPageSize":3,
            "list":[
                {
                    "id":23,
                    "name":"doraemon",
                    "phone":"153221",
                    "salary":0,
                    "bonus":0,
                    "age":0,
                    "sex":"男",
                    "dept":null,
                    "role":"运营专员",
                    "salt":"e387f2938200459bb625",
                    "password":"b1f7517de7670ae3196798953019aefb",
                    "status":1,
                    "pic":null,
                    "other":null,
                    "createTime":"2021-07-27 14:06:39",
                    "vacation":0,
                    "location":null,
                    "degree":null
                },
            ]
        }
    },
    "url":"http://codecworld.pro/cw/employer/all"
}
```

## 参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| option | Object | - | 是 | 请求入参 | v0.3.0 |

### option参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| url | String | - | 是 | 网络请求地址（url长度限制为7868） | v0.3.0 |
| headers | Object | - | 否 | 网络请求头的key和value属性必须是String类型 | v0.3.0 |
| responseType | String | json | 否 | 网络请求数据类型（json） | v0.3.0 |
| timeout | Integer | 5000 | 否 | 网络请求超时时间（单位ms） | v0.3.0 |
| success | Function | - | 是 | 网络请求成功返回结果回调参数 | v0.3.0 |
| fail | Function | - | 否 | 网络请求失败返回结果回调参数 | v0.3.0 |

### success参数

| 属性 | 类型 | 默认值 | 必填 | 说明 | 最低版本支持 |
|:----|:----|:------|:-----|:----|:-----------|
| url | String | - | - | 网络请求地址 | v0.3.0 |
| status | Integer | - | - | 网络请求结果状态码 | v0.3.0 |
| headers | Object | - | - | 网络请求结果headers | v0.3.0 |
| body | Object | - | - | 网络请求结果 | v0.3.0 |

