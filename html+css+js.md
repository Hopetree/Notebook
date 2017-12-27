# 资源收集
- bootstrap时间轴：<https://bootsnipp.com/snippets/featured/timeline-responsive>

- Font Awesome 图标的大小不一致导致占用像素不同的问题，使用.fa-fw 即可保证宽度一致，当然也可以自定义宽度然后居中对齐
- 消息提示的小标签

```
<span class="msg text-center">4</span>
.msg {
    font-size:13px;
    position: absolute;
    top: 0px;
    right: 1.25rem;
    z-index: 3;
    color: #fff;
    display: block;
    min-width: 16px;
    padding: 0 3px;
    height: 16px;
    border-radius: 16px;
    line-height: 16px;
    background: red;
}
```
- 一个图片360度旋转的CSS
```
.img1 {
            transition: All 0.4s ease-in-out;
            -webkit-transition: All 0.4s ease-in-out;
            -moz-transition: All 0.4s ease-in-out;
            -o-transition: All 0.4s ease-in-out;
        }

       .img1:hover {
            transform: rotate(360deg);
            -webkit-transform: rotate(360deg);
            -moz-transform: rotate(360deg);
            -o-transform: rotate(360deg);
            -ms-transform: rotate(360deg);
        }
```
- before伪元素的例子
```
.kk:before {
    position: absolute;
    top: 1.3rem;
    left: .5rem;
    width: 0;
    height: 0;
    border-style: solid;
    border-color: #fff #fff #fff #4285f4;
    -webkit-transform-origin: 25% center;
    transform-origin: 25% center;
    border-width: 4px;
    content: "";
}
```
