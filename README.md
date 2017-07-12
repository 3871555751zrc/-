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
