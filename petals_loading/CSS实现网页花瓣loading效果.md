**最终效果**

![](https://s1.ax1x.com/2020/07/04/Nztw34.png)

**完整代码**

https://github.com/1395204913/CSSDemo/tree/master/petals_loading

**主要实现代码**

首先创建父容器load,再创建6个花瓣容器petal

```javascript
<!-- 父容器 -->
    <div class="load">
        <!-- 六个花瓣 -->
        <div class="petal"></div>
        <div class="petal"></div>
        <div class="petal"></div>
        <div class="petal"></div>
        <div class="petal"></div>
        <div class="petal"></div>
    </div>
```

将父容器绘制成圆形

```javascript
.load::before{
    content: '';
    display: block;
    width: 100px;
    height: 100px;
    background-color: #fff;
    border-radius: 50%;
    opacity: 0.7;
    background-color: #eb4d4b;
}
```

绘制6个花瓣

```javascript
.petal::before{
    content: '';
    display: block;
    width: 60px;
    height: 60px;
    background-color: #fff;
    border-radius: 40px 40px 0 0;
    transform-origin: top center;
    transform:rotateX(-70deg);
    animation: flower 2.5s cubic-bezier(0.5,0,0.5,1) infinite;
}
```

此时6个花瓣集中于一处，按照一定角度张开

```javascript
.petal:nth-child(1){
    transform: rotate(0deg);
}
.petal:nth-child(2){
    transform: rotate(60deg);
}
......
```

添加动画

```javascript
@keyframes flower{
    0%,100%{
        width: 80px;
        height: 280px;
    }
    40%{
        height: 0;
    }
}
@keyframes load{
    0%{
        transform: rotate(0deg) scale(1);
    }
    50%{
        transform: rotate(360deg) scale(.4);
    }
    100%{
        transform: rotate(720deg) scale(1);
    }
}
```
