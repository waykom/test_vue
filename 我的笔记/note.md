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



### CSS 处理文字溢出

> 单行文字溢出在文字溢出处显示省略号

```css
farther{
  	overflow: hidden;
}
child {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
```

> 多行文字溢出

```css
text{
    display:-webkit-box;
    // 设置可以显示的行数
    -webkit-line-clamp:8;
    -webkit-box-orient:vertical;
    overflow:hidden;
}
```



### uni-swiper 改变面板指示点样式为横条

>   若为全局更改，推荐在App.vue中加入

```css
uni-swiper .uni-swiper-dot {
	width: 60rpx;
	height: 4rpx;	
	border-radius: 6rpx;
}
uni-swiper .uni-swiper-dot-active {
	width: 60rpx;
	border-radius: 6rpx;
}
```



### 如何在 repl.it 中创建一个 Web 服务器?

> 要做到这一点，在你的项目中创建一个新的文件，叫做 `keep_alive.py`
>
> 然后添加以下代码:

```python
    from flask import Flask
    from threading import Thread

    app = Flask('')

    @app.route('/')
    def home():
        return "Hello. I am alive!"

    def run():
      app.run(host='0.0.0.0',port=8080)

    def keep_alive():
        t = Thread(target=run)
        t.start()
```

> 在 `main.py` 的顶部添加以下一行来导入服务器。

```python
    from keep_alive import keep_alive
```

> 运行Web服务器 `keep_alive()`

