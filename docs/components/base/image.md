---
layout: default
title: Image
nav_order: 3
parent: 基础
grand_parent: 组件
---

# Image

## 说明
图片组件

## 示例
```javascript
TinyUI.render(TinyDOM.createElement(
    "column", {
    style: {
        width: "100%",
        height: "100%"
    }
},
    TinyDOM.createElement("image", {
        style: {
            width: "90%",
            height:"70%"
        },
        src: "https://dogefs.s3.ladydaily.com/~/source/unsplash/photo-1527693381201-45771cd9716f?ixid=MnwxMjA3fDB8MHxzZWFyY2h8ODJ8fGdpcmwlMjBhbG9uZXxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"
    })
));
```

## 参数

| 属性 | 类型     | 默认值 | 取值范围 | 说明  |
| ---- | -------- | ------ | ---- | --------------- |
| src | string   |      |    | 图片资源,目前仅支持网络图片         |
| alt | string   |      |    | 图片加载失败占位图,目前仅支持网络图片         |
| borderRadius | number   |    | | 图片圆角         |
| borderTopLeftRadius | number   |      |    | 图片左上圆角         |
| borderTopRightRadius | number   |      |    | 图片右上圆角         |
| borderBottomLeftRadius | number   |      |    | 图片左下圆角         |
| borderBottomRightRadius | number   |      |    | 图片右下圆角         |
| scaleType | string   |  centerCrop    | 'matrix', 'fitXY', 'fitStart', 'fitCenter', 'fitEnd', 'centerCrop', 'centerInside', 'center'   | 图片拉伸模式,详见下文 '图片拉伸模式'         |

## 图片拉伸模式
### matrix:
Scale using the image matrix when drawing.
绘制时使用图像矩阵进行缩放.

### fitXY:
Scale in X and Y independently, so that src matches dst exactly. This may change the aspect ratio of the src.
在 X 和 Y 中独立缩放，以便 src 与 dst 完全匹配。 这可能会改变 src 的纵横比。

### fitStart:
Compute a scale that will maintain the original src aspect ratio, but will also ensure that src fits entirely inside dst. At least one axis (X or Y) will fit exactly. START aligns the result to the left and top edges of dst.
计算将保持原始 src 纵横比的比例，但也将确保 src 完全适合 dst。 至少有一个轴（X 或 Y）将完全吻合。 START 将结果与 dst 的左边缘和上边缘对齐。

### fitCenter:
Compute a scale that will maintain the original src aspect ratio, but will also ensure that src fits entirely inside dst. At least one axis (X or Y) will fit exactly. The result is centered inside dst.
计算将保持原始 src 纵横比的比例，但也将确保 src 完全适合 dst。 至少有一个轴（X 或 Y）将完全吻合。 结果以 dst 为中心。

### fitEnd:
Compute a scale that will maintain the original src aspect ratio, but will also ensure that src fits entirely inside dst. At least one axis (X or Y) will fit exactly. END aligns the result to the right and bottom edges of dst.
计算将保持原始 src 纵横比的比例，但也将确保 src 完全适合 dst。 至少有一个轴（X 或 Y）将完全吻合。 END 将结果与 dst 的右边缘和下边缘对齐。

### centerCrop:
Scale the image uniformly (maintain the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the view (minus padding).
均匀缩放图像（保持图像的纵横比），使图像的两个尺寸（宽度和高度）等于或大于视图的相应尺寸（减去填充）。

### centerInside:
Scale the image uniformly (maintain the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or less than the corresponding dimension of the view (minus padding). The image is then centered in the view.
均匀缩放图像（保持图像的纵横比），使图像的两个尺寸（宽度和高度）等于或小于视图的相应尺寸（减去填充）。 然后图像在视图中居中。

### center:
Center the image in the view, but perform no scaling.
在视图中居中图像，但不执行缩放.
