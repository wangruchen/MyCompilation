# 机器学习——朴素贝叶斯（Naive Bayesian）

参考资料[分类算法之朴素贝叶斯分类](http://www.cnblogs.com/leoo2sk/archive/2010/09/17/1829190.html)

<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

朴素贝叶斯算法的理论基础为贝叶斯定理。

## 贝叶斯定理

在事件B已经发生的前提下，事件A发生的概率为P(A|B)，求解公式为：

$$
P(A|B)=\frac{P(AB)}{P(B)}=\frac{P(A|B)P(B)}{P(A)}
$$

## 朴素贝叶斯分类的原理流程

设<img src="http://www.forkosh.com/mathtex.cgi? x=\{a_{1},a_{a},\cdots,a_{m}\}">为一个待分类样本，a为样本的特征。可能所属的类别为<img src="http://www.forkosh.com/mathtex.cgi? y_{1},\cdots,y_{n}">。

1. 根据已知的训练样本集，统计得到在各类别下各个特征属性的条件概率估计。即<img src="http://www.forkosh.com/mathtex.cgi? P(a_{1}|y_{1},\cdots,P(a_{m}|y_{1});P(a_{1}|y_{2},\cdots,P(a_{m}|y_{2});\cdots">
2. 如果各个特征属性条件独立，则根据贝叶斯定理有：
	
	$$
	P(y_{i}|x)=\frac{P(x|y\_{i})P(y\_{i})}{P(x)}
	$$
	分母对所有类别为常数。所以
	$$
	P(x|y\_{i})P(y\_{i})=P(a\_{1}|y\_{i})P(a\_{2}|y\_{i})\cdots P(a\_{m}|y\_{i})P(y\_{i})
	$$
3. 求得<img src="http://www.forkosh.com/mathtex.cgi? P(y_{i}|x)">后，计算<img src="http://www.forkosh.com/mathtex.cgi? P(y_{k}|x)=\max\{P(y_{1}|x),P(y_{2}|x),\cdots,P(y_{n}|x)\}">，则<img src="http://www.forkosh.com/mathtex.cgi? x\in y_{k}">。
