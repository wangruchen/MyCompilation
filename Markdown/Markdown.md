# Markdown学习笔记

## 插入数学公式
参考文章：[Markdown中插入数学公式的方法](http://blog.csdn.net/xiahouzuoxin/article/details/26478179)

1. 使用Google Chart的服务器

	```
	<img src="http://chart.googleapis.com/chart?cht=tx&chl= 在此插入Latex公式" style="border:none;">
	```
2. 使用forkosh服务器

	```
	<img src="http://www.forkosh.com/mathtex.cgi? 在此处插入Latex公式">
	```
3. 使用MathJax引擎

	```
	<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
	```
	然后，再使用Tex写公式。`$$公式$$`表示行间公式，本来Tex中使用\(公式\)表示行内公式，但因为Markdown中`\`是转义字符，所以在Markdown中输入行内公式使用`\\(公式\\)`，如下代码：
	
	```
	$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$
\\(x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\\)
	```