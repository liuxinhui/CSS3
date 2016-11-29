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

>2.1、border-style常用值列表

none 无边框

hidden 隐藏边框

dotted 点状

dashed 虚线

solid 实线

>2.2、border类型

border-color、border-image、border-radius、border-shadow

border-color可以有颜色值如red、#000还以可以有rgba

	border-color:1px solid rgba(0,0,0,0.6)

其中transparent可以设置透明色

>2.3、border-radius

圆角的设置技巧

（1）当border-radius的半径值小于或等于border的厚度时，元素内部就不具有圆角效果

（2）元素的宽度是高度的2倍，并且圆角半径等于高度值时 可以制作上/下半圆

（3）元素的高度是宽度的2倍，并且圆角半径等于高度值时 可以制作左/右半圆

（4）制作扇形：宽 高 圆角半径相同

（5）椭圆 宽是高的2倍 圆角半径的水平半径等于元素宽度

>2.4、border-shadow

border-shadow：x-offset y-offset blur-radius spread-radius color

###3、CSS3背景

新增的属性

background-origin 指定背景图片的起点

background-clip指定背景图的显示范围

background-size 指定背景图的尺寸

background-break 指定内敛元素的背景图平铺时循环方式

>3.1、background-origin:padding-box || boder-box || content-box

padding-box:从padding的外边缘显示

border-box从border的外边缘显示

content-box从content的外边缘显示

>3.2、background-clip背景裁切

background-origin:padding-box || boder-box || content-box

>3.3、background-size背景尺寸

background-size:auto||cover||contain

cover:将背景放大，以适合铺满整个容器，但是会使图片失真

contain：保持图片的宽高比例，将图片缩放到宽高正好适应所定义的容器区域

###4、CSS3文本

font-style / font-weight/ font-size-adjust(定义是否强制对文本使用同一尺寸) font-stretch（定义横向拉伸变形字体） 

>4.1、CSS文本类型

word-spacig:normal/lenght  词与词之间的距离

lettet-spacing:none/length 字符与字符的距离

vertical-align:baseline/sub/suber/bottom 垂直对齐方式

text-decoration:none/underline/overline/line-through/blink

text-indent:length

text-align:left/center/right/justify 文本水平对齐方式

line-height 文本行高

text-transform:none/uppercase/lowercase/capitalize 定义文本大小写

text-shadow 定义文本阴影效果

white-space 定义文字和文本之间的空白字符

direction 控制文本的流入方向

>4.2、text-shadow

text-shadow:color x-offset y-offset blur-radius

>4.3、text-overflow 文本溢出属性

text-overflow:clip/ellipsis

clip:不显示省略标记（...）只是简单的裁切

cllipsis：显示省略标记(...)，省略标记插入的位置是最后一个字符

###5、CSS3颜色特性

>5.1、CSS3透明属性

opacity:alphavalue/inherit

>5.1、CSS3颜色模式

rgba模式/hsl模式/hsla模式

###6、CSS3盒模型

>6.1、box-sizing属性及语法参数

box-sizing属性主要用来控制元素的盒模型的解析模式，主要目的是控制元素的总宽度

box-sizing:content-box||border-box||inherit

content-box:让元素维持标准的盒模型。element width/height=border+padding+content width/height

border-box:元素内容的width/height=盒子的宽或高-padding-border（可以保证设置的宽度值不会因为padding和border的值而改变）

inherit：继承了父元素的盒模型模式

>6.2、outline外轮廓属性

outline不占网页布局空间，是一种动态样式，只有元素获取到焦点或者被激活时呈现

outline:color style offset

###7、CSS3伸缩布局盒模型

CSS3引入了新的布局模式----Flexbox布局

>7.1、初始化盒模型

	display: box !important;
	display:-webkit-box !important;
	display: flxe;
	display: -webkit-flex;

>7.2、伸缩流方向box-orient

box-orient属性主要用来创建主轴，从而定义了伸缩项目在伸缩容器中的流动方向

horizontal:从左到右水平排列

vertical:从上到下垂直排列

inline-axis:沿着内联轴排列

block-axis:沿着块轴排列

>7.3、布局顺序box-direction

伸缩项目在容器中的流动顺序

box-direction:normal||reverse

>7.4、主轴对齐box-pack（水平）

box-pack：start||center||end||justify

>7.5、侧轴对齐box-align(垂直)

box-align：start||center||end||baseline||stretch

>7.6伸缩性box-flex

box-flex:<number>

>7.7、显示box-ordinal-group

排列顺序是从小到大的顺序排列

经验：如果希望整个页面的布局和浏览器窗口可视区域一样高，需要设置html和body的height一样

	html,body{
		height:100%;
	}

###8、css3多列布局

columns:包括column-width和column-count

column-gap:定义间距

column-rule定义边框

column-span定义跨列

column-fill控制每列的列高效果

###9、CSS3渐变

>9.1、线性渐变

颜色沿着一条直线过渡

语法：参数第一个to top是渐变方向，第二 第三分别是起始颜色

	linear-gradient(to top,orange,green);
	
>9.2、径向渐变

径向渐变是圆形或椭圆形渐变

语法：

radial-gradient（）

###10、CSS3变形

允许css3在2D或者3D空间进行变形操作

>10.1、变形属性及函数

X/Y可用的函数 translateX()、translateY()、scaleX()、scaleY()、skewX()、skewY()

transform常用的transform-function功能

translate()位移、scale()缩放、rotate()旋转、skew()倾斜

###11、CSS3过渡

transition是一个复合属性

transition-property:指定过渡的css属性

transition-duration:指定完成过渡所需的时间

transition-timing-function:指定过渡的函数

transition-day:指定过渡开始出现的延迟时间

例如：

	transition:<property> <duration> <animation type> <dey>;
	transition:background 2s linear 2s,border-radius 3s ease-in 3s;

transition-timing-function函数的属性值 如下：

ease:由快到慢，逐渐变慢

linear:恒速

ease-in:速度越来越快，呈一种加速状态，艰险效果

ease-out:速度越来越慢，呈一种减速状态，渐隐效果

ease-in-out：先加速再减速，呈现渐显渐隐效果

###12、CSS3动画

>12.1、CSS3动画属性

animation属性可以通过@keyframes构建一些transition的动画效果

语法：

	animation:<animation-name> <animation-duration> <animation-timing-function> <animation-delay> <animation-iteration-count> <animation-direction> <animation-play-state> <animation-fill-mode>

animation-iteration-count 动画的播放次数

animation-iteration-count:infinite 

animation-fill-mode 设置动画时间外属性

animation-fill-mode:none|forwards|backwards|both
























