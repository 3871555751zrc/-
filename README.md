# -
css语法小总结：
全屏的css其中一种写法如下：
```<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			.fullscreen{
				position: absolute;//absolute 定位绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>
				top:0;
				left: 0;
				bottom: 0;
				right: 0;
				border: 1px solid green;
				margin: 0px;
			}
		</style>
	</head>
	<body class="fullscreen">
		
	</body>
</html>
```

div 居中显示的小案例：
```
                    <div class="content">
			<div style="margin: 0 auto;width: 200px;height: 100px;border:1px solid burlywood;">
				//在这里面可以放那些需要居中显示的元素或者文本之类的东西，居中的核心就是 margin：0 auto 以及必须要指定width的大小
			</div>
		    </div>
```

mui主界面的仿照小案例，头部和底部都是固定不动的，所以要用fixed的position方式，并且这个fixed的定位方式没有占用文档流的位置，要在所以在头部导航栏后面的div会忽略掉头部导航栏，所以此时为了把内容正常显示出来，可以使用margin-top的方式。
```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	<link rel="stylesheet" href="common/mui.css" />
	<script type="text/javascript" src="common/mui.js" ></script>
	<style>
		.top{
			position: fixed;
			top:0px;
			height: 44px;
			width: 100%;
			border: 1px solid blueviolet;
		}
		.top h1{
			text-align: center;
		}
		.content{
			height:100px;
			border: 1px solid red;
			padding-top: 44px;
		}
		.bottom{
			position: fixed;
			bottom: 0px;
			border: 1px solid green;
			left: 0px;
			right: 0px;
			height: 50px;
		}
		.bottom1,.bottom2,.bottom3,.bottom4{
			float: left;
			margin-left: 20px;
		}
		.bottom1{
			border: 2px solid #007AFF;
		}
		.bottom2{
			border: 2px solid black;
		}
		.bottom3{
			border: 2px solid blue;
		}
		.bottom4{
			border: 2px solid red;
		}
	</style>
	</head>
	<body>
		<div class="top"><h1>标题</h1></div>
		<div class="content">
			<div style="margin: 0 auto;width: 200px;height: 100px;border:1px solid burlywood;">
				
			</div>
		</div>
		<div class="bottom">
			<div style="margin: 0 auto;border:1px solid #242424;height: 50px;width: 270px;">
			<div class="bottom1">主页</div>
			<div class="bottom2">联系人</div>
			<div class="bottom3">我的</div>
			<div class="bottom4">设置</div>
			</div>
		</div>
	</body>
</html>

```


css兼容性笔记：
最终元素的总宽度计算公式是这样的：
总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距
元素的总高度最终计算公式是这样的：
总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距
浏览器的兼容性问题
一旦为页面设置了恰当的 DTD，大多数浏览器都会按照上面的图示来呈现内容。然而 IE 5 和 6 的呈现却是不正确的。根据 W3C 的规范，元素内容占据的空间是由 width 属性设置的，而内容周围的 padding 和 border 值是另外计算的。不幸的是，IE5.X 和 6 在怪异模式中使用自己的非标准模型。这些浏览器的 width 属性不是内容的宽度，而是内容、内边距和边框的宽度的总和。
虽然有方法解决这个问题。但是目前最好的解决方案是回避这个问题。也就是，不要给元素添加具有指定宽度的内边距，而是尝试将内边距或外边距添加到元素的父元素和子元素。
IE8 及更早IE版本不支持 填充的宽度和边框的宽度属性设。
解决IE8及更早版本不兼容问题可以在HTML页面声明 <!DOCTYPE html>即可。
