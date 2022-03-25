---
layout: default
title: 概览
nav_order: 1
---

# 🚀 **面向 IoT 场景的一站式应用快速开发框架**

TinyUI 是专注于 IoT 场景下的快速研发框架，可以简化 Android 应用构建、开发以及发布，可以使用更少的代码、更丰富的 API 功能，打造高质量的应用产品。

```jsx
// 1. 页面元素
const page = () => {
    return (
        <column style={{width: "100%", height: "100%",
            justifyContent: "center", alignItems: "center"}}>
            <text style={{fontSize: 50}}>Hello，TinyUI!</text>
        </column>
    );
}

// 2. 开始渲染
TinyUI.render(page());
```

<img src="/assets/images/hello_tinyui.png" width="250" />

[快速开始]({{ site.baseurl }}{% link docs/quick-start/index.md %}){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

## 页面示例
<img src="/assets/images/tinyui_preview.png"/>
