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
