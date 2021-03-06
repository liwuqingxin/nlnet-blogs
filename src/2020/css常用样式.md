个人是个前端盲，东拼西凑地想改个[主题](https://www.cnblogs.com/liwuqingxin/p/14381825.html)，半路过来逛逛，学习记录下<i class="icon" id="smile" size="24"> </i>。请注意，以下内容来源于网络的文章都已注明了来源，如需学习细节请移步原文。直接列出的代码都是测试通过有效的。

# 文字渐变色

==参考== [文字颜色渐变的 3 种方法](https://zhuanlan.zhihu.com/p/80946714)、[文字颜色渐变的 3 种方法（二）](https://www.cnblogs.com/ypppt/p/13334613.html)。

```css
/* 方法一 */
.gradient-text-one{ 
	background: linear-gradient(to right, var(--theme-color), var(--code-emphasize-color));
	-webkit-background-clip: text;
	color: transparent;
}
```

```css
/* 方法二 */
.box { position: relative; text-align: left;
    text-indent:30px;
    line-height: 50px; font-size: 40px;
    font-weight: bolder;
    color: red;
    -webkit-mask-image: -webkit-gradient(linear, 0 0, 0 bottom, from(yellow), to(rgba(0, 0, 255, 0)));
}
```

# 背景图片缩放

==参考== [背景图片缩放](https://www.cnblogs.com/yanyunliu/p/10328576.html)。

```css
.zoomImage {
    background-image:url(images/yuantiao.jpg);
    background-repeat:no-repeat;
    background-size:100% 100%;
    -moz-background-size:100% 100%;
}
```

# 悬浮元素（叠放元素）

==参考== [How to Stack Elements in CSS](https://css-tricks.com/how-to-stack-elements-in-css/)。

```css
  ...
  position: absolute;
  ...
```

# Hover影响其他元素

==参考== [How to affect other elements when one element is hovered](https://stackoverflow.com/questions/4502633/how-to-affect-other-elements-when-one-element-is-hovered)

If the cube is directly inside the container:

```css
#container:hover > #cube { background-color: yellow; }
```

If cube is next to (after containers closing tag) the container:

```css
#container:hover + #cube { background-color: yellow; }
```

If the cube is somewhere inside the container:

```css
#container:hover #cube { background-color: yellow; }
```

If the cube is a sibling of the container:

```css
#container:hover ~ #cube { background-color: yellow; }
```

# id和class结合查找

==参考== [How to combine class and ID in CSS selector?](https://stackoverflow.com/questions/1028248/how-to-combine-class-and-id-in-css-selector)、[Multiple Class / ID and Class Selectors](https://css-tricks.com/multiple-class-id-selectors/)

```html
<div class="sectionA" id="content">
    Lorem Ipsum...
</div>
```

```css
div#content.myClass {
    
}
```

# 使用svg

==参考== [在Html或者css3中如何使用SVG](https://blog.csdn.net/weixin_36872950/article/details/103796472)

修改其他人的代码，比如博客、主题等，直接使用base64会比较方便。（[SVG文件在线转base64 >> ](https://www.css-js.com/tools/base64.html)）

```css
.svg{
	width:300px;
	height:300px;
	background-image:url('data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBzdGFuZGFsb25lPSJubyI/PjwhRE9DVFlQRSBzdmcgUFVCTElDICItLy9XM0MvL0RURCBTVkcgMS4xLy9FTiIgImh0dHA6Ly93d3cudzMub3JnL0dyYXBoaWNzL1NWRy8xLjEvRFREL3N2ZzExLmR0ZCI+PHN2ZyB0PSIxNTc3MzgyODEzNDI1IiBjbGFzcz0iaWNvbiIgdmlld0JveD0iMCAwIDEwMjQgMTAyNCIgdmVyc2lvbj0iMS4xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHAtaWQ9IjE4OTMiIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCI+PGRlZnM+PHN0eWxlIHR5cGU9InRleHQvY3NzIj5AZm9udC1mYWNlIHsgZm9udC1mYW1pbHk6IHRhb2tlemh1c2hvdWljb25mb250OyBzcmM6IHVybCgiLy9hdC5hbGljZG4uY29tL3QvZm9udF8xNDAzODYxX2c3cjl1N3hoZmYuZW90PyNpZWZpeCIpIGZvcm1hdCgiZW1iZWRkZWQtb3BlbnR5cGUiKSwgdXJsKCIvL2F0LmFsaWNkbi5jb20vdC9mb250XzE0MDM4NjFfZzdyOXU3eGhmZi53b2ZmMiIpIGZvcm1hdCgid29mZjIiKSwgdXJsKCIvL2F0LmFsaWNkbi5jb20vdC9mb250XzE0MDM4NjFfZzdyOXU3eGhmZi53b2ZmIikgZm9ybWF0KCJ3b2ZmIiksIHVybCgiLy9hdC5hbGljZG4uY29tL3QvZm9udF8xNDAzODYxX2c3cjl1N3hoZmYudHRmIikgZm9ybWF0KCJ0cnVldHlwZSIpLCB1cmwoIi8vYXQuYWxpY2RuLmNvbS90L2ZvbnRfMTQwMzg2MV9nN3I5dTd4aGZmLnN2ZyNpY29uZm9udCIpIGZvcm1hdCgic3ZnIik7IH0KPC9zdHlsZT48L2RlZnM+PHBhdGggZD0iTTUxMy45IDY2LjJjLTIzOS4xIDAtNDMzIDE5My45LTQzMyA0MzNzMTkzLjkgNDMzIDQzMyA0MzMgNDMzLTE5My45IDQzMy00MzMtMTkzLjktNDMzLTQzMy00MzN6TTM5OS4yIDYxN0wzODUgNjMzLjggMjI1LjggNDk0LjIgMzgzLjUgMzUzbDE1LjggMTUuMy0xNDIgMTI1LjlMMzk5LjIgNjE3eiBtMzcuOSAyNmwtMTUuOC05LjIgMTY3LjEtMjkwIDE1LjggOS4yLTE2Ny4xIDI5MHogbTIwNi41LTkuMkw2MjkuNCA2MTdsMTQxLjktMTIyLjctMTQxLjktMTI1LjkgMTUuOC0xNS4zIDE1Ny43IDE0MS4yLTE1OS4zIDEzOS41eiIgZmlsbD0iIzBhNmJhYyIgcC1pZD0iMTg5NCI+PC9wYXRoPjwvc3ZnPg==');
	background-repeat:no-repeat;	
}
```

# transform直观说明

==参考== [https://developer.mozilla.org/](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-function/rotate3d())

注意，这个网站可以很直观的学习一些css的原理。这些知识甚至可以映射到相通的领域。

# HTML在线渲染

==地址== [plnkr](http://plnkr.co/edit/3hHI6tnuXmmdJwM4?open=lib%2Fscript.js)



==未完待续== 不定期持续更新<i class="icon" id="dragon" size="24"> </i>...