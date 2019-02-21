## 基于rem、em的布局策略

* 统一标准组件最高层父元素字体16px

* 基于16px推算组件内所有子元素的宽、高、字体大小、盒子属性等等(em实现)

* 如果发现全局根元素有rem实现特性，则推算出组件内所有元素的宽、高等等按照rem标准实现

* 例如，根元素16px，则父元素字体大小为1rem

```html
<!--根元素字体大小为 16px 对应的宽度 160px-->
<div style="font-size:16px">
 <div style="width:160px"></div>
</div>
<!--根元素字体大小为 16px 对应的宽度 10em (适配em)-->
<div style="font-size:16px">
 <div style="width:10em"></div>
</div>
<!--dom (html) 根元素字体大小为1rem 对应的宽度10em(适配em)-->
<html style="font-size:16px">
<div style="font-size:1rem">
 <div style="width:10em"></div>
</div>
```

## 设计图通用尺寸算法，全部以iPhone 6,6s,7,8 为主要机型

* Points(尺寸大小) 375 × 667

* Pixels(像素密度) 750 × 1334

* dom根元素为 50px，即<html style="font-size:50px"></html>

* ratio(比率) 0.32 基于此比率算出实现rem特性的页面，实现响应式

## 使用规范

* 尽量不要对设置字体大小的标签，嵌套子元素
* 设置所有组件的根元素，统一字体大小，子元素全部使用em实现

## 文档目录

  * [toast](toast.md)
  * [messagebox](messagebox.md)