---
title: css笔记
date: 2016-08-13 14:14:34
tags: 
    - web
    - css
---
大家都喜欢页面分成左右两栏，百分比width和min-width设置左栏用了都说好，但是右栏可没有min-left属性，该怎么办？

<!--more-->

当下流行页面左边放个sidebar的左右两栏的设计，大多数情况下左右两栏的宽度用百分比决定，比如这个blog就是这样的：


```css
.sidebar {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 25%;
    min-width: 350px;
    height: 100%;
    overflow: hidden;
    background-color: #333;
    color: white;
    text-align: right;
}

.main-content {
    position: absolute;
    top: 0;
    right: 0;
    left: 25%;
    bottom: 0;
    height: 100%;
    padding: 20px 40px 0;
    overflow: auto;
    word-wrap: break-word;
}
```
    
遇到低分辨率的情况时，25%的sidebar可能不足以显示所有内容，所以sidebar加了一个min-width的条目。但是右侧内容区的左侧定位却并没有min-left这样的属性，那么该如何实现？
只要在其后添加如下代码（CSS3+）:

```css
@media all and (max-width: 1400px) {
    .main-content {
        margin-left: 0px;
        left: 350px;
    }
}
```

当前显示分辨率小于1400px时，下面的样式会自动override上面的样式，从而达到脑补中min-left的感觉。