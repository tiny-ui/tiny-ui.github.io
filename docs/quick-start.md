---
layout: default
title: 快速开始
nav_order: 2
---

# 快速开始
一个 `hello world` 的例子：

```javascript
// 1. 定义页面元素
const page = () => {
    return (
        <column id="container">
            <text id={"text"} style={{fontSize: 50}}>Hello，Tiny UI!</text>
        </column>
    );
}

// 2. 渲染入口方法
TinyUI.render(page());
```

<img src="/assets/images/hello_world.png" width="250" />

