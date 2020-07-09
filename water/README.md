**最终效果**

![UZsFTs.gif](https://s1.ax1x.com/2020/07/08/UZsFTs.gif)

**完整代码**

https://github.com/1395204913/CSSDemo/tree/master/water

**主要实现代码**

首先创建外圈容器container和内圈容器wave

```javascript
<div class="container">
        <div class="wave"></div>
    </div>
```

将两元素居中放置且设置为圆形

```javascript
.container,
.wave {
    width: 12.5rem;
    height: 12.5rem;
    border-radius: 50%;
    /* 居中 */
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
```

设置container容器和海平面wave样式样式

```javascript
.container {
    padding: 0.625rem;
    border: 4px solid #00d8d6;
}
.wave {
    background-color: #34e7e4;
    overflow: hidden;
}
```

“海浪”的形成是通过动态遮挡部分海平面所形成的，

![UZya80.png](https://s1.ax1x.com/2020/07/08/UZya80.png)

因此设置遮挡物样式

```javascript
.wave:after{
    content: "";
    width: 300px;
    height: 250px;
    background-color: rgba(255, 255, 255, 0.8);
    position: absolute;
    left: 50%;
    top: 0;
    transform: translate(-50%,-60%);
    border-radius: 40%;
    // 最后加上动画效果，海浪就做出来了
    animation: wave 5s  linear infinite;
}
```

添加动画

```javascript
@keyframes wave{
    100%{
        transform: translate(-50%,-60%) rotate(360deg);
    }
}
```
