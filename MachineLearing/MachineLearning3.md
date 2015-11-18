# 斯坦福机器学习整理3——第三周
<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
## 逻辑回归（Logistic Regression）

一种分类算法，其输出值一直在0到1之间。

假设函数：<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)=g(\theta^{T}x)"> 

<img src="http://www.forkosh.com/mathtex.cgi? g(z)=\frac{1}{1+e^{-z}}">
称为Sigmoid Function或Logistic Function。如图![Logistic Function](file:///Users/wangruchen/work/github/wangruchen/MyCompilation/MachineLearing/figures/LogisticFunction.png)

