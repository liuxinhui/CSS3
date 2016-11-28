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

2.3、border-radius

圆角的设置技巧

（1）当border-radius的半径值小于或等于border的厚度时，元素内部就不具有圆角效果

（2）元素的宽度是高度的2倍，并且圆角半径等于高度值时 可以制作上/下半圆

（3）元素的高度是宽度的2倍，并且圆角半径等于高度值时 可以制作左/右半圆

（4）制作扇形：宽 高 圆角半径相同

（5）椭圆 宽是高的2倍 圆角半径的水平半径等于元素宽度

2.4、border-shadow

border-shadow：x-offset y-offset blur-radius spread-radius color

###3、CSS3背景

新增的属性

background-origin 指定背景图片的起点

background-clip指定背景图的显示范围

background-size 指定背景图的尺寸

background-break 指定内敛元素的背景图平铺时循环方式

3.1、background-origin:padding-box || boder-box || content-box

padding-box:从padding的外边缘显示

border-box从border的外边缘显示

content-box从content的外边缘显示

3.2、background-clip背景裁切

background-origin:padding-box || boder-box || content-box

3.3、background-size背景尺寸

background-size:auto||cover||contain

cover:将背景放大，以适合铺满整个容器，但是会使图片失真

contain：保持图片的宽高比例，将图片缩放到宽高正好适应所定义的容器区域

































