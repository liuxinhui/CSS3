# bootstrap知识点梳理
***
### 第一章CSS组件

1.1栅格系统

定义：一系列的行和列构建的一种布局，随着屏幕放大，最多展示12个列

1.1.1 container，容器，盛东西

网页上所有的内容，建议放到容器里面

1.1.2 两种布局：

固定布局：container：

流式布局：container-fluid:

栅格根据屏幕最多显示12列

栅格参数：

col-lg-3：lg，large(屏幕>=1200px) PC

col-md-3：md，middle（992px-1200px）

col-sm-3：sm,small（768px-992px）小平板

col-xs-	（小于768px）手机（超小屏幕和xl对立）

辅助类

文本颜色 text-

	<div class="text-primary">这是一段文本</div>
	<div class="text-danger">这是一段文本</div>
	<div class="text-warning">这是一段文本</div>
	<div class="text-info">这是一段文本</div>
	<div class="text-muted">这是一段文本</div>
	<div class="text-success">这是一段文本</div>

背景颜色 bg-

	<div class="bg-primary">这是一段文本</div>
	<div class="bg-danger">这是一段文本</div>
	<div class="bg-warning">这是一段文本</div>
	<div class="bg-info">这是一段文本</div>
	<div class="bg-muted">这是一段文本</div>
	<div class="bg-success">这是一段文本</div>

快速浮动：

	<div class="clearfix">
		<div class="pull-left">我是左浮动</div>
		<div class="pull-right">我是右浮动</div>
	</div>

块元素、霸道，不管多少内容，始终沾满一行

行内元素：低调，有多少内容占多大空间

左浮动：pull-left

有浮动：pull-right

浮动会将块元素转换成行内元素，不占原来的位置，有多少内容占多大的空间

清除浮动：clearfix，不受浮动的影响

文字居中：text-center

案例展示块元素垂直居中

	.container{
				width: 300px;
				height: 250px;
				background: #fff;
				border-radius: 10px;
				position: absolute;
				top: 50%;
				left: 50%;
				transform: translate(-50%,-50%);
			}
transform: translate(-50%,-50%)是相对于自身移动的百分比

###表格：只需要添加.table即可美化表格

为表格的外层div添加 .table-responsive 即可创建响应式表格，其会在小屏幕设备上（小于768px）水平滚动。当屏幕大于 768px 宽度时，水平滚动条消失。

1.斑马线，隔行换色：table-striped

2.鼠标悬停效果：table-hover

3.增加边框：table-bordered

4..table-condensed 类可以让表格更加紧凑

表格内容垂直居中：vertical-align:middle

vertical:垂直

align:对齐

	<div class="table-responsive">
				<table class="table table-bordered table-hover table-striped">
					<thead>
						<tr class="bg-info">
							<th>姓名</th>
							<th>年龄</th>
							<th>性别</th>
							<th>籍贯</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>张三</td>
							<td>18</td>
							<td>男</td>
							<td>北京市</td>
						</tr>
						<tr>
							<td>张三</td>
							<td>18</td>
							<td>男</td>
							<td>北京市</td>
						</tr>
						<tr>
							<td>张三</td>
							<td>18</td>
							<td>男</td>
							<td>北京市</td>
						</tr>
						<tr>
							<td>张三</td>
							<td>18</td>
							<td>男</td>
							<td>北京市</td>
						</tr>
					</tbody>
				</table>
			</div>	


###表单

垂直样式表单（默认）：

表单分组：form-group

表单项（input、textarea）：form-control都将被默认设置宽度属性为 width: 100%

lable的for标签是为了与表单元素绑定，当点击for标签的文字时 鼠标会定位到相应的表单元素中

	<form role="form">
				<h3 class="text-center">这是一个表单元素</h3>
				<div class="form-group">
					<label for="user">用户名</label>
					<input type="text" id="user" class="form-control" placeholder="请输入用户名" />
				</div>
				<div class="form-group">
					<label for="pwd">密码</label>
					<input type="password" id="pwd" class="form-control" placeholder="请输入密码" />
				</div>
				<div class="checkbox">
					<label>
						<input type="checkbox">记住密码
					</label>
				</div>
				<button type="submit" class="btn form-control btn-success ">登录</button>
			</form>

水平样式表单：

1. 给form标签，增加一个 form-horizontal类

2. 表单元素的form-group里使用col-lg-区分宽度


表单校验

给form-group添加 .has-warning、.has-error 或 .has-success 类到这些控件的父元素即可。任何包含在此元素之内的 .control-label、.form-control 和 .help-block 元素都将接受这些校验状态的样式。

	<div class="form-group has-success">
		<label for="user">用户名</label>
		<input type="text" id="user" class="form-control" placeholder="请输入用户名" />			
	</div>

添加额外的图标：

1.在form-group 对应的标签里面，增加has-feedback类

在input输入框的后面，创建图表<span>标签 在标签里添加 form-control-feedback 然后再加上自己想要的图标名称

	<div class="form-group has-feedback">
		<label for="user">用户名</label>
		<input type="text" id="user" class="form-control" placeholder="请输入用户名" />
		<span class="form-control-feedback glyphicon glyphicon-user"></span>	
	</div>

### 列表

给ul增加：list-group类

给li：list-group-item类

徽章：badge

每个列表项的颜色：list-group-item-颜色（success\warning\danger）

	<ul class="list-group">
				<li class="list-group-item "><a href="#">大唐网络有限公司</a><span class="badge">10</span></li>
				<li class="list-group-item"><a href="#">大唐网络有限公司</a></li> 
				<li class="list-group-item"><a href="#">大唐网络有限公司</a></li>
			</ul>

### 图片

响应式图片：增加img-responsive类

通过为图片添加 .img-responsive 类可以让图片支持响应式布局。其实质是为图片设置了 max-width: 100%; 和 height: auto; 属性

responsive：响应式的
	thumbnail：缩略图

图片的形状：
	圆角图片：img-rounded

圆形的图片：img-circle

缩略图：img-thumbnail

### 按钮

生成按钮的方式，有3种：

	<button class="btn btn-primary" type="submit">按钮1</button>
	<input type="button" class="btn btn-success" value="按钮2">
	<a href="#" class="btn btn-danger">按钮2</a>

按钮的颜色 btn-danger/success

按钮的大小 btn-lg md xs

按钮组

用btn-group包裹botton

	<div class="btn-group">
		<button class="btn btn-primary" type="submit">按钮1</button>
		<button class="btn btn-primary" type="submit">按钮1</button>
		<button class="btn btn-primary" role="group">按钮1
	</button>
	</div>

### 第二章 组件

### 下拉菜单

dropdown下拉

menu:菜单

dropdown-menu：

1.将ul列表转换成下拉菜单：增加dropdown-menu类

2.给button增加 dropdown-toggle类，如何实现点击按钮的时候让菜单显示：
data-toggle=”dropdown”

	<div class="dropdown">
			<button class="btn btn-default dropdown-toggle" data-toggle="dropdown">
				下拉菜单
				<span class="caret"></span>
			</button>
			<ul class="dropdown-menu">
				<li><a href="#">PHP大牛班</a></li>
				<li><a href="#">Web前端与HTML5</a></li>
			</ul>
		</div>

输入框组

输入框组就是给输入框的两侧增加元素或者按钮



