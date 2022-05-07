# HTML基础

# 1.简单的 HTML 页面架构

`<!DOCTYPE html>` 文档类型声明标签，告诉浏览器这个页面采取html5版本来显示页面。

`<head> </head>` 头部标签，网页标签以及一些引入的内容在此部分。

`charset="UTF-8"` 字符集，必须写。采取UTF-8编码格式来保存文字，如果不写就会乱码。

`<title>百度一下，你就知道</title>` 网页栏的内容

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220413144443.png)

`<body>xxx</body>` body标签的内容会显示在页面上，head头部内容不显示。

`<!--xxxx-->` 注释标签，不会被执行。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
	</body>
</html> 
<!--这是一个注释-->
```

# 2.HTML常见标签

## 2.1 meta 标签

`<meta>` 标签可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的关键词和描述。

设置网站关键字，这是给搜索引擎看的，本网页的关键词。

`<meta name="keywords" content="网络安全，WEB渗透，数据安全，渗透测试"/>`

这是一个描述。

`<meta name="description" content="这是一个网安笔记"/>`

## 2.2 link 标签

`<link>` 标签定义文档与外部资源的关系。

## 2.3 script标签

`<script>` 标签一般用于引入js文件。

## 2.4 p 标签

`<p>` 为段落标签。

## 2.5 标题标签

HTML提供了6个等级的网页标题，字号由大到小。

`<h1>一级标题</h1>` 

`<h2>二级标题</h2> ` 

`<h3>三级标题</h3> ` 

`<h4>四级标题</h4>` 

`<h5>五级标题</h5>` 

`<h6>六级标题</h6>` 

`</br>` 换行标签

`<hr>`换行线标签

## 2.6 文本属性

`<strong></strong>` 加粗。

`<b></b>`加粗。

`<i></i>`斜体。

`<u></u> `下划线。

`<sup></sup>`上标。

`<sub></sub>`下标。

`<del></del>` 删除线。

`<font></font> `规定字体属性。

​    `size`字体的大小，单位px。

​    `color` 字体颜色。

`<pre></pre>` 字体呈现源码样式，定义预格式化的文本。被包围在 pre 元素中的文本通常会保留空格和换行符。而文本也会呈现为等宽字体。

# 3. form 表单

`<form>` 用于为用户输入创建HTML表单，用于向服务器传输数据。

1.规定当提交表单时向何处发送表单数据。

下面是一处搜索框内的`form`表单，

`action`表示表单要提交的目的地，`method`是提交的方式`get`。

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220413224504.png)

下面是一处登录框的`form`表单，提交方式为`post`。

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220413224752549.png)

2.规定在发送表单数据之前如何对其进行编码。

`enctype` 属性可能的值：

	- `application/x-www-form-urlencoded` (默认值)
	- `multipart/form-data` 
	- `text/plain` 

# 4. input 标签

`name` 表示的该文本输入框名称。

`size` 输入框的长度大小。

`maxlength` 输入框中允许输入字符的最大数。

`value` 输入框中的默认值。

`readonly` 只读，表示该框中只能显示，不能添加修改。

input 的类型：

- type=password 密码输入框

- type=file 文件上传

- type=hidden 隐藏域

`button` 按钮

`checkbox` 复选框

`radio` 单选框

`type=submit` 提交按钮

`type=reset`  重置按钮

`&nbsp;` 空格

`<label></label>` 标签为 input 元素定义标签，标签内的for 属性应该等于相关元素的 id 元素，以便将它们捆绑起来。可以通过使用 "for" 属性将 label 绑定到另一个元素，或者直接在 label 元素内部放置元素。

下面是一个form表单的代码以及其在浏览器中的显示。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<form action="" method="post" >
			<label>用户名：</label><input type="text" name="username" size="30" maxlength="4" value="admin" readonly/></br>
			<label>密&nbsp;码：</label><input type="password" name="password" /></br>
			<label for="email">邮&nbsp;箱：</label><input type="text" name="email" id="email" /></br>
			<label>技&nbsp;能：</label>安全开发<input type="checkbox">渗透测试<input type="checkbox"></br>
			<label>性&nbsp;别：</label>男<input type="radio" value="1" name="sex">女<input type="radio" name="sex" value="2"></br>
			<input type="hidden" value="1"/>
			<input type="submit" vale="提交"/>
			<input type="reset" value="重置" />
			<input type="button" value="button" />
		</form>
		
		<hr>
		
		<form method="post" enctype="multipart/form-data">
			<input type="file" name="file" />
			<input type="submit" />
		</form>
	</body>
</html>
```

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220413231348.png)

# 5. a 标签

`<a></a>` 标签用于控制界面与页面之间的跳转。

- `self` 在当前页面打开被链接文档。（默认）

- `_blank` 打开另一个新的页面进行跳转到被链接文档。

- `_parent` 在父框架集中打开被链接文档。

- `_top` 在整个窗口中打开被链接文档。

锚文本：

`<a name="2">锚点</a>` 

`<a href="#2">返回锚点</a>` 

# 7. img 标签

`img` 标签用于插入图片

- `src` 图片的相对路径。

- `width` 图片的高度。

- `height` 图片的宽度。

- `alt` 图片的替代文本。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>第三课</title>
	</head>
	<body>
		<p name="top">xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<a name="666">锚点</a>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<p>xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx</p>
		<a href="http://www.baidu.com">百度</a>
		<a href="http://www.baidu.com" target="_self">百度</a>
		<a href="http://www.baidu.com" target="_blank">百度</a>
		<a href="#top">返回顶部</a>
		<a href="#2">返回锚点</a></br>
	<hr>
	<img src="img/logo.jpg" width="100" height="100" alt="logo">
	</body>
</html>
```

# 8. table 标签

`<table></table>` 是表格标签，在网页中为表格形式。

- `border` 值为外边框粗细程度。
- `cellpadding` 内边框与内容的空白。
- `cellspacing` 内边框与外边框的空白。
- `width` 外边框的宽度。
- `height` 外边框的高度。
- `<caption></caption>`表格的标题。
- `<tr></tr>` 行。
- `<th></th>` 表格，一般用于第一行，字体加粗居中。
- `<td></td>` 表格，用于其余行，其内字体左对齐。
  - `rowspan` 竖。
  - `colspan` 行。

例子：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<table border="5" cellpadding='1' cellspacing='50' width="1000" height="400">
			<caption>姓名 图</caption>
			<tr>
				<th>#</th><th>姓名</th><th>年龄</th>
			</tr>
			<tr>
				<td>1</td><td>鲁班</td><td>30</td>
			</tr>
			<tr>
				<td>2</td><td>马超</td><td>15</td>
			</tr>
		</table>
		
		
		<table border="1" cellpadding='10'>
			<tr>
				<th>#</th><th>姓名</th><th>年龄</th>
			</tr>
			<tr>
				<td>1</td><td>刘备</td><td rowspan='2'>30</td>
			</tr>
			<tr>
				<td>2</td><td>鲁班</td>
			</tr>
			<tr>
				<td>3</td><td>马超</td><td>15</td>
			</tr>
			<tr>
				<td>4</td><td>鲁班大师</td><td rowspan='2'>40</td>
			</tr>
			<tr>
				<td>5</td><td>典韦</td>
			</tr>
			<tr>
				<td>总数</td><td colspan="2">6</td>
			</tr>
		</table>
	</body>
</html>
```

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220414122433.png)

# 9. ul 标签

`<ul></ul>`里面包含`<li></li>`子标签，是无序列表。

ul 标签的type属性：square、circle、disc 分别代表 方块、圆圈、圆点。

# 10. ol 标签

`<ol></ol>`里面包含`<li></li>`子标签，是有序列表。

ol 标签的type属性：

- 数字列表  `1` 

- 小写字母列表 `a` 

- 大写字母列表 `A` 

- 罗马字母列表 `I` 

- 小写罗马字母列表 `i` 

例子：

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>无序列表与有序列表</title>
	</head>
	<body>
		<ul type="square"> <!--无序列表-->
                       
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
		</ul>
		<ul type="circle"> <!--无序列表-->
                       
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
		</ul>
		<ul type="disc"> <!--无序列表-->
                       
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
		</ul>
		<ol type="1"> <!--有序列表-->
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
			<li>啦啦啦啦啦啦</li>
		</ol>
	</body>
</html>
```

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220415224243.png)

# 11. frameset标签

`<frameset></frameset>` 标签定义一个框架集，它被用来组织多个窗口，每个窗口都是一个独立的html界面。不能嵌套在body标签里。

`<frameset> `有两个参数：

- `cols` 列的数目和尺寸。

- `rows` 行的数目和尺寸。

**注意！只能用其中一个参数。要么是 rows，要么是 cols，不能同时定义。**

`frame` 是在html页面内嵌入框架，框架内可以连接另一个页面，一般都是在`frameset`中使用。

- `scrolling` 滚动条
  - `auto` 在需要的情况下出现滚动条（默认值）。
  - `yes` 始终显示滚动条（即使不需要）。
  - `no`从不显示滚动条（即使需要）。

例子1：

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<frameset cols="30%,*" >
		<frame src="http://www.baidu.com" scrolling="no"/>
		<frame src="http://www.sogou.com" />
	</frameset>
	<body>
		
	</body>
</html>
```

例子2：

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<frameset rows="50%,50%" >
		<frame src="http://www.baidu.com" scrolling="no"/>
		<frame src="http://www.sogou.com" />
	</frameset>
	<body>
		
	</body>
</html>
```

例子3：

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220415230834.png)

![](https://gitee.com/defyou/BlogImageBed/raw/master/img/20220415230923.png)

