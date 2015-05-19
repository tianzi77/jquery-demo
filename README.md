<!doctype html>
<!--jq107-->
<html>
</body>
</html>
<head>
<meta charset="utf-8">
<title>tianzi  code</title>
<script src="http://code.jquery.com/jquery-latest.js"></script>
<script type="text/javascript">
$(function(){
	//添加mask层
	$(".chakan").click(function(){
		var maskHeight=$(document).height();
		var maskWith=$(document).width();
		$('<div class="mask"></div>').appendTo($("body"));
		$("div.mask").css({
			"background":"#000",
			"opacity":0.4,
			"position":"absolute",
			"left":0,
			"top":0,
			"z-index":2,
			"width":maskWith,
			"height":maskHeight
		});

		//查看信息
		var arr=[];
		$(this).parent().siblings().each(function(){
			arr.push($(this).text());
		})
		$(".mydiv").show().children().each(function(i){
			$(this).children("span").text(arr[i])
		})
		$(".down").click(function(){
		$(this).parent().hide();
		$(".mask").remove();
	})

		//删除列表
		$(".del").click(function(){
			$(this).parents("tr").remove();
		})
	})
})
</script>
<style type="text/css">
#table{
	width: 700px;
	border:1px solid #abcdef;
	border-collapse: collapse;
	margin: 0 auto;
	font-family: "微软雅黑";
}
#table th,#table td{
	border:1px solid #abcdef;
	text-align: center;
}
#table td a{
	text-decoration: none;
	color: #abcdef;
}
div.mydiv{
	width: 330px;
	border:1px dotted red;
	padding: 10px;
	position: relative;
	left: 50%;
	z-index: 4;
	display: none;
	font-family: "微软雅黑";
	background: #fff;
}
div.mydiv p{
	border-bottom: 1px solid red;
	color: #abcdef;
}
div.mydiv a{
	text-decoration: none;
	color: #abcdef;
}
button{
	color:#fff;
	background: red;
	position: absolute;
	right: 0;
	top: 0;
}
</style>
</head>
<body>
<table id="table">
	<tr>
		<th>姓名</th>
		<th>年龄</th>
		<th>职业</th>
		<th>长相</th>
		<th>工资</th>
		<th>功能</th>
	</tr>
	<tr>
		<td>小哲</td>
		<td>24</td>
		<td>研究生</td>
		<td>美女</td>
		<td>10000</td>
		<td><a href="#" class="chakan">查看</a>&nbsp;<a href="#" class="del">删除</a></td>
	</tr>
	<tr>
		<td>天子</td>
		<td>23</td>
		<td>本科生</td>
		<td>帅哥</td>
		<td>8000</td>
		<td><a href="#" class="chakan">查看</a>&nbsp;<a href="#" class="del">删除</a></td>
	</tr>
	<tr>
		<td>张三</td>
		<td>33</td>
		<td>前端工程师</td>
		<td>帅哥</td>
		<td>3000</td>
		<td><a href="#" class="chakan">查看</a>&nbsp;<a href="#" class="del">删除</a></td>
	</tr>
	<tr>
		<td>李四</td>
		<td>33</td>
		<td>java工程师</td>
		<td>丑女</td>
		<td>1000</td>
		<td><a href="#" class="chakan">查看</a>&nbsp;<a href="#" class="del">删除</a></td>
	</tr>
</table>
	<div class="mydiv">
		<p><strong>姓名</strong>:<span></span></p>
		<p><strong>年龄</strong>:<span></span></p>
		<p><strong>职位</strong>:<span></span></p>
		<p><strong>长相</strong>:<span></span></p>
		<p><strong>工资</strong>:<span></span></p>
		<button class="down">关闭</button>
	</div>
</body>
</html>
