# js-2
day2

//实现js特效 无缝滚动。

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>

</head>
<style>
	*{
	margin: 0;
	padding: 0;
}
#container{
	width: 500px;
	height: 240px;
	border: 1px solid #ccc;
	margin: 50px auto;
	overflow: hidden;
	position: relative;
}
#img-list{
	list-style: none;
	height: 150px;
	position: absolute;
}
#img-list li{
	width: 150px;
	height: 150px;
	padding-right: 15px;
	float: left;	
}
#img-list img{
	width: 150px;
	height: 150px;
}
#buttons{
	height: 50px;
	text-align: center;
	position: absolute;
	margin-left: -105px;
	left: 50%;
	top: 160px;

}
#left,#right{
	height: 50px;
	width: 100px;
	float: left;
	text-align: center;
	line-height: 50px;
	background: #ccc;
	margin-right: 10px;
}
</style>
<body>
	<div id="container">
		<ul id="img-list">
			<li><img src="img/1.jpg"></li>
			<li><img src="img/2.jpg"></li>
			<li><img src="img/3.jpg"></li>
			<li><img src="img/4.jpg"></li>
		</ul>
		<div id="buttons">
			<span id="left">&lt;&lt;向左</span>
			<span id="right" style="margin-right=0">向右&gt;&gt;</span>
		</div>
	</div>

	<script type="text/javascript">
		var oUl = document.getElementById('img-list');
		var oLeft = document.getElementById('left');
		var oRight = document.getElementById('right');
		var ispeed = -2;
		oUl.innerHTML += oUl.innerHTML;
		var aLi = oUl.getElementsByTagName('li');

			oUl.style.width = aLi.length * aLi[0].offsetWidth  + 'px';
		
		setInterval(function(){
			if(oUl.offsetLeft <= -oUl.offsetWidth / 2){
				oUl.style.left = 0;
			}
			if(oUl.offsetLeft > 0){
				oUl.style.left = -oUl.offsetWidth / 2 + 'px'; 
			}
			oUl.style.left = oUl.offsetLeft + ispeed +'px';
		},20);
		oLeft.onmouseover = function(){
			ispeed = -2;
		};
		oRight.onmouseover = function(){
			ispeed = 2;
		};
	</script>
</body>
</html>




//今天看的博客地址
http://www.w3cfuns.com/notes/18686/12ac2afe61f976d6f7c81452b0449f0a
讲的是css中postion的用法
postion要用之前就应该明白什么事什么是文档流。文档流是将窗体自上而下分成一行行, 并在每行中按从左至右的顺序排放元素,即为文档流。 
只有三种情况会使得元素脱离文档流，分别是：浮动、绝对定位和相对定位。

