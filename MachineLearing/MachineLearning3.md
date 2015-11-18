# 斯坦福机器学习整理3——第三周
<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
## 逻辑回归（Logistic Regression）

一种分类算法，其输出值一直在0到1之间。

假设函数：<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)=g(\theta^{T}x)"> 

<img src="http://www.forkosh.com/mathtex.cgi? g(z)=\frac{1}{1+e^{-z}}">
称为Sigmoid Function或Logistic Function。如图![Logistic Function](file:///Users/wangruchen/work/github/wangruchen/MyCompilation/MachineLearing/figures/LogisticFunction.png)
假设函数：
$$ h\_{\theta}(x)=\frac{1}{1+e^{-\theta^{T}x}}$$


### 逻辑回归具体过程

#### 1. 构造假设函数
构造假设函数，确定decision boundary（划分种类的边界），根据当<img src="http://www.forkosh.com/mathtex.cgi? \theta^{T}x \ge 0">时，<img src="http://www.forkosh.com/mathtex.cgi? y=1">。确定了<img src="http://www.forkosh.com/mathtex.cgi? \theta">就可以确定decision boundary。
#### 2. 构造cost函数
拟合参数<img src="http://www.forkosh.com/mathtex.cgi? \theta">
#### 3. 梯度下降法求<img src="http://www.forkosh.com/mathtex.cgi? J(\theta)">的最小值