#CSS3简要文档
###1、结构伪类选择器

所有的结构伪类都是基于HTML文档树的，也称作文档对象模型（DOM）

>常用语法
first-child 、lastchild 、 nth-child(n)、nth-of-type(n)、odd(奇数)、even(偶数)

###2、否定伪类选择器

否定伪类选择器:not()是CSS3新增的选择器，可以起到过滤内容的作用

>语法
input:not([type=radio]):not{....}

###3、伪元素

伪元素表示DOM外部的某种文档结构,由原来的单冒号改变为双冒号的结构

>常用语法

::first-letter、::firsrt-line、::before、::after、::section

::first-letter用来选择文本快的第一个字母（首字下沉、首字母）

::firsrt-line用来匹配第一行文本

::before、::after可以文本中插入额外内容的位置，生成的内容不会成为DOM的一部分，但可以设置样式

例如：

	<div class="ui-info">
		<h2>这是一个使用before伪类元素</h2>
	</div>
	
	.ui-info{
		box-sizing:border-box;
		-webkit-box-sizing:border-box;
		width: 260px;
		padding: 10px 0;
		background-color:#000;
	}
	.ui-info h2{
		position: relative;
		color: #fff;	
	}
	.ui-info h2:after{
		content: "";
		border: 5px solid red;
		border-color:#fff transparent transparent;
		position: absolute;
		top: 10px ;
		right:10px;
	
	}

::section是用来匹配突出显示的文本

	::section{
		background:red;
		color:blue;
	}

###2、CSS3边框

2.1、border-style常用值列表

none 无边框

hidden 隐藏边框

dotted 点状

dashed 虚线

solid 实线

2.2、border类型

border-color、border-image、border-radius、border-shadow

border-color可以有颜色值如red、#000还以可以有rgba

	border-color:1px solid rgba(0,0,0,0.6)

其中transparent可以设置透明色








