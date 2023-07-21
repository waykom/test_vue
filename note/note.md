## 20230721

### CSS 设置元素的横向滚动

> 对于父元素

```css
	// 设置为弹性盒子
	display: flex;
	// 设置元素溢出时所需的行为,如果内容溢出，则浏览器提供滚动条。
	overflow: auto;
```

> 对于各个子元素

```css
	// 设置flex元素的收缩大小
	flex-shrink: 0;
```

> 对于移动端开发或小程序开发，横向滚动条有时会影响美观，为此可以隐藏掉横向滚动条
>
> 父类添加 `::-webkit-scrollbar` 伪类元素，添加一条声明 `display: none;`

```css
    father::-webkit-scrollbar {
        display: none;
    }
```



### CSS 实现倒三角最简单的方法

> HTML

```html
	<div class="box"></div>
```

> CSS

```css
	.box {
		width: 0;
		height: 0;
		border: 50px solid transparent;
		border-top-color: red;
	}
```

