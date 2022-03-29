---
layout: default
title: Tiny.js
parent: 架构
nav_order: 1
---

# Tiny.js 说明
Tiny.js 是内置的一个简单的 JavaScript 库，提供给 DSL 层使用，主要包括三个对象：
- TinyUI ：提供 `render` 方法，将元素渲染到实际的画布中。
- TinyDOM ：
  - 提供了 `createElement` 方法，创建一个元素。
  - 定义了 ```Element``` 类，用于描述 DOM 元素以及使用方法。
- TinyAPI ：API 功能相关，例如：网络、文件、图片等。

**需要注意的是，Element 里的方法不支持操作没有渲染到画布上的 DOM 元素**，示例如下：

正确的是：
```jsx
const text = <text>Hello</text>
TinyUI.render(text);
text.setText('World'); // text 已经渲染到画布上，可以正常操作
```

错误的是：
```jsx
const text = <text>Hello</text>
text.setText('World');// text 未渲染到画布上，所以这行代码不会起作用
TinyUI.render(text);
```

## 主要代码
### TinyUI
```javascript
var TinyUI = {
    render: (element) => {
        // 调用原生方法，渲染到实际画布
      __native_render__(element);
    }
};
```

### TinyDOM
```javascript
/* 原生方法定义 */
var TinyDOM = {
    // 获取节点，返回 => element
    getElementById: (id, thisObj) => {},
    // 属性设置方法，返回 => boolean
    setAttribute: (id, key, value, thisObj) => {},
    // 样式设置方法，返回 => boolean
    setStyles: (id, style, thisObj) => {},
    // 单个属性设置方法，返回 => boolean
    setStyle: (id, key, value, thisObj) => {},
    // 属性获取方法，返回 => object
    getAttribute: (id, key, thisObj) => {},
    // 添加事件方法，返回 => ID
    addEventListener: (id, action, handler, thisObj) => {},
    // 添加一个节点，返回 => boolean
    appendChild: (id, child, thisObj) => {},
    // 插入一个节点，返回 => boolean
    insertBefore: (id, newChild, refChild, thisObj) => {},
    // 移除一个节点，返回 => boolean
    removeChild: (id, child, thisObj) => {}
};

// Element 节点类
{
    // 默认自增 ID
    let e_id = 1;

    class Element {
        constructor(type) {
            this.id = (e_id++).toString();
            this.type = type;
            this.props = {};
            this.children = [];
        }

        getElementById(id) {
            return TinyDOM.getElementById(id, this);
        }

        getAttribute(key) {
            return TinyDOM.getAttribute(this.id, key, this);
        }

        setAttribute(key, value) {
            return TinyDOM.setAttribute(this.id, key, value, this);
        }

        addEventListener(key, handler) {
            return TinyDOM.addEventListener(this.id, key, handler, this);
        }

        appendChild(child) {
            return TinyDOM.appendChild(this.id, child, this);
        }

        insertBefore(newChild, refChild) {
            return TinyDOM.insertBefore(this.id, newChild, refChild, this);
        }

        removeChild(childId) {
            return TinyDOM.removeChild(this.id, childId, this);
        }

        setStyle(key, value) {
            return TinyDOM.setStyle(this.id, key, value, this);
        }

        setStyles(style) {
            return TinyDOM.setStyle(this.id, style, this);
        }

    }

    TinyDOM.Element = Element;

    // 节点创建方法
    TinyDOM.createElement = (type, props, ...children) => {
        let element = new Element();
        element.type = type;

        if (props != null) {
            element.props = props;
            if (props.id) {
                element.id = props.id;
            }
        }

        if (element.props.style == null) {
            element.props.style = {};
        }

        if (!Array.isArray(children)) {
            throw new Error("Only support type with Array Type");
        }

        children = children.flat();
        children = children.filter((item) => {
            return item instanceof Object || typeof item === 'string';
        });

        if (children.length === 1) {
            let text = children[0];
            if (typeof text === 'string') {
                element.props.text = text;
            }
        }

        element.children = children;

        return element;
    };
}
```

### TinyAPI
实际方法会在框架层进行注入，这里只定义 `TinyAPI` 对象。
```javascript
var TinyAPI = {};
```
