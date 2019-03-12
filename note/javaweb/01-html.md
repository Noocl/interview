## 2.1 创建基本静态页面
### 2.1.1 设置网页头部和标题
1. 文档类型（DOCTYPE），定义当前页面使用标记语言（HTML或XHTML）的版本。
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0.1 Transitional//EN" ...>
2. 编码类型（常用）：GB2312, UTF-8, HZ
中文乱码时，加入如行。
<meta http-equiv="Content-type" content="text/html; charset=utf-8">
3. 页面标题<title></title>

### 2.1.2 设置页面正文和注释
1. 正文：常用属性
    - background：设置页面的背景图像
    - bgcolor：设置页面的背景颜色
    - text：设置页面内文本的颜色
    - link：设置页面未被访问过的链接颜色
    - vlink：设置页面已经被访问过的链接颜色
    - alink：设置页面内链接被访问时的颜色
2. 注释 <!-- 注释内容 -->

### 2.1.3 文字和段落处理
1. 设置标题文字
<h1>..<h6> align="left/center/right"
2. 设置文本文字
- 文本文字标记：<font size=数字 face=字体名 color=颜色>文字内容</font>
- 字形设置
    <b>bord</b>, <i>incline</i>, <u>underline</u>, <sub>文本下标</sub>
    <sup>文本上标</sup>, <big>大字体</big>, <small>小字体</small>
3. 设置段落标记<p></p>，段前段后都会有空行。

### 2.1.4 超级链接处理
1. 建立页面链接<a></a>
<a href=地址 name=字符串 target=打开窗口方式>热点</a>
- href：如果资源放在服务器上，可以写相对路径，否则写绝对路径。href不能与name同时使用。
- name：
- target：设定目标资源要显示的窗口
    - _blank/new：打开新的浏览器窗口
    - _parent：显示在父框架窗口中
    - _self：默认值，显示在当前窗口中
    - _top：显示在没有框架的窗口中
2. 其他形式的链接
- Email链接
    <a href="mailto:songci1106@live.com">热点</a>
- FTP链接
    <a href="ftp://10.168.1.181">热点</a>

### 2.1.5 插入图片 
1. 图片格式介绍
    - GIF：Grapthics Interchange Format，图形交换格式。
    - JPEG：Joint Photographic Experts Group，联合图像专家组
2. 设置背景图片
<body background=图片名称>
3. 插入指定图片
<img src=文件名 alt=说明 width=x height=y border=n hspace=h vspace=v align=对齐方式>
    - alt：在浏览器尚未完全读入图片时，在图片位置显示的文字。
    - width/height：单位是像素或百分比
    - hspace/vspace：设置图片左右/上下空间，单位像素。
    - border：图片边框，单位像素。
图片链接
<a href=地址><img src=图片文件名></a>

### 2.1.6 列表处理
1. 无序列表<ul>，unordered list
<ul type=符号类型1><li type=符号类型2>第一个列表项</li></ul>
type类型，适用于无序与有序：
    - disc：实心圆（默认）
    - circle：空心圆
    - square：实心方块
2. 有序列表<ol>，ordered list
<ol type=符号类型1><li type=符号类型2>第一个列表项</li></ol>
type类型，适用于无序与有序
    - 1：数字显示（默认）
    - A：大写字母
    - a：小写字母
    - I：大写罗马字母
    - i：小写罗马字母
    
---    
## 2.2 HTML页面布局
### 2.2.1 使用表格标记
1. 创建表格<table>
- bgcolor：表格背景色
- border：是否带边框
- bordercolor：边框颜色
- cellspacing：格子之间空间的大小
- cellpading：格子边框与内部内容之间的大小
- width：表格宽度，单位是绝对像素或总宽度的百分比
2. 设置表格标题
<caption> align=值 vlaign=值</caption>
- valign：设置表格标题放在表的top，middle，bottom
3. 表格设置和处理
- 跨行 <td rowspan=2>
- 跨列 <td colspan=2>
- 跨行跨列 <td colspan=2 colspan=2>

### 2.2.2 使用框架标记
1. 框架组标记<frameset>enc
frameset不能与body同时出现
- rows/cols：设置横/纵向侵害的框架数目，可以是像素也可以是百分比。
- border：边框宽度（同frame）
- bordercolor：边框颜色（同frame）
- frameborder：有无边框（同frame）
- framespacing：各窗口间的空白
2. 框架标记<frame>
- src：框架对应的源文件
- scrolling：是否加入滚动条（yes/no/auto）
- noresize：是不允许改变窗口大小，默认为允许。
<frameset rows="*" cols="160,*" framespacing="1" frameboder="yes" border="1" bordercolor="#666666">
    <frame src="../resource/1.html" name="leftFrame"/>
    <frame src="../resource/2.jpg" name="rightFrame" scrolling="no"/>
</frameset>

### 2.2.3 使用层标记
1. div介绍
division，分区。<div 参数>中间部分</div>
- id：标识符id
- class：类
- dir：文字方向
- title：元素标题
- style：行内样式
- align：对齐的方法
- onclick/ondbclick：鼠标和键盘各种事件发生时处理方法的定义。

---
## 2.3 处理表单
> textarea, select, input

### 2.3.2 使用form标记
<form action="http://baidu.com" method="post" enctype="application/x-www-form-urlencoded"
name="form1" target="_parent">
    <input type="submit" value="提交">
</form>
- enctype：数据传输的MIME类型
    - application/x-www-form-urlencode：默认方式，通常与post一起使用
    - multipart/form-data：上传文件或图片时的专用类型
- method：请求方式（get/post）

### 2.3.3 文本域和按钮
<textarea name=文本域 id=值 cols=宽度 rows=行数></textarea>
<input type=类型 name=名称 id=标识 value=按钮上的文字>
type类型：button/radio/checkbox/text/submit/reset

### 2.3.5 单选按钮和筛选框
<label>radio
    <input type="radio" name="fruit" id="apple" value="apple">
</label>
<label>checkbox
    <input type="checkbox" name=名字 id=标识 value=值>
</label>

### 2.3.7 文件域、图像域、隐藏域
<input type="file" name=名 id=标识 size=宽度 maxlength=最多字符数>
<input type="image" id=标识 src=文本 alt=显示 align=middle height=值 width=值>
<input type="hidden" name=名 id=标识 value=值> value是隐藏域表单传送的数据。
<select name="aa" id="aa">
    <option>China</option>
    <option>English</option>
    <option>Japan</option>
</select>



## 2.4 特效和多媒体处理
2.4.1 滚动效果marquee
2.4.2 背景音乐bgsound
2.4.3 Flash
2.4.4 ActiveX控件

## 2.5 谈XML与HTML的区别
xml是用来存储数据的，重在数据本身
html是用来定义数据的，重在数据的显示模式。
1. xml的语法 
<?xml: 表示xml声明的开始记号
version="1.0"，xml版本说明
encoding="gb2312"，可选项，编码声明

### 2.6.2 在HTML网页中实现空格
<pre></pre>预格式化命令，可以保留空格与换行。还有好多方式。


 





































