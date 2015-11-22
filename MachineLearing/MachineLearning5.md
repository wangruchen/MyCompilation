# 斯坦福机器学习整理5——第五周

Neural learning

<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

## Cost Function

代价函数：
$$
J(\theta)=-\frac{1}{m}[\sum^{m}\_{i=1}\sum^{K}\_{k=1}y^{(i)}\_{k}\log h\_{\theta}(x^{(i)})\_{k}+(1-y^{(i)}\_{k})\log (1-h\_{\theta}(x^{(i)})\_{k})]+\frac{\lambda}{2m}\sum^{L-1}\_{l=1}\sum^{s\_{l}}\_{i=1}\sum^{s\_{l+1}}\_{j=1}(\theta^{(l)}\_{j})^{2}
$$

## Forward Propagation(前向传播)

## Back Propagation(反向传播)

用来计算代价函数的导数。
反向传播算法就是计算一个项<img src="http://www.forkosh.com/mathtex.cgi? \delta^{(l)}_{j}">，代表第l层上单元j的激励误差。

假设训练集为<img src="http://www.forkosh.com/mathtex.cgi? \{(x^{(1)},y^{(1)}),\cdots,(x^{(m)},y^{(m)})\}">，算法流程：

1. 令<img src="http://www.forkosh.com/mathtex.cgi? \Delta^{(l)}_{ij}=0 ~ (for ~all~l,i,j)">
2. For <img src="http://www.forkosh.com/mathtex.cgi? i=1"> to <img src="http://www.forkosh.com/mathtex.cgi? m">
	1. 令 <img src="http://www.forkosh.com/mathtex.cgi? a^{(1)}=x^{(i)}">
	2. 用前向传播计算<img src="http://www.forkosh.com/mathtex.cgi? a^{(l)}"> for <img src="http://www.forkosh.com/mathtex.cgi? l=2,3,\cdots,L">
	3. 用<img src="http://www.forkosh.com/mathtex.cgi? y^{(i)}">，计算<img src="http://www.forkosh.com/mathtex.cgi? \delta^{(L)}=a^{(L)}-y^{(i)}">
	4. 计算<img src="http://www.forkosh.com/mathtex.cgi? \delta^{(L-1)},\delta^{(L-2)},\cdots,\delta^{(2)}">
	5. <img src="http://www.forkosh.com/mathtex.cgi? \Delta^{(l)}_{ij}:=\Delta^{(l)}_{ij}+a^{(l)}_{j}\delta^{(l+1)}_{i}">
3. <img src="http://www.forkosh.com/mathtex.cgi? D^{(l)}_{ij}:=\frac{1}{m}\Delta^{(l)}_{ij}+\lambda\theta^{(l)}_{ij}~">if<img src="http://www.forkosh.com/mathtex.cgi? ~j\ne 0">

	<img src="http://www.forkosh.com/mathtex.cgi? D^{(l)}_{ij}:=\frac{1}{m}\Delta^{(l)}_{ij}~">if<img src="http://www.forkosh.com/mathtex.cgi? ~j= 0">
4. 代价函数的偏导数为<img src="http://www.forkosh.com/mathtex.cgi? \frac{\partial}{\partial\theta^{(l)}_{ij}}J(\theta)=D^{(l)}_{ij}">

## Gradient Checking(梯度检验)