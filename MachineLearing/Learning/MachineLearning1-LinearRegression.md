# 机器学习——线性回归（Linear Regression）

<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

## 线性回归（Linear Regression）

线性回归（Linear Regression）是假设的特征和结果满足线性关系，可以用一个线性模型表示。

**用途：**用一个连续回归模型进行预测，预测出输入特征对应结果的具体数值。

**假设函数：**输入m个训练样本，<img src="http://www.forkosh.com/mathtex.cgi? (x^{1},y^{1}),\cdots,(x^{m},y^{m})">，假设函数为
$$h\_{\theta}=\theta^{T}X=\sum^{n}\_{i=1}\theta\_{i}x_{i}$$其中<img src="http://www.forkosh.com/mathtex.cgi? \theta">为参数，<img src="http://www.forkosh.com/mathtex.cgi? X">代表样本的特征。

**学习过程：**通过对训练样本的学习，确定假设函数的参数<img src="http://www.forkosh.com/mathtex.cgi? \theta">使得样本的实际值y和预测值<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}">最接近。用代价函数<img src="http://www.forkosh.com/mathtex.cgi? J(\theta)">表示样本实际值和预测值之间的距离。

### 代价函数（Cost Function）

**代价函数：**$$J(\theta)=\frac{1}{2}\sum^{m}\_{i=1}(h_{\theta}(x^{i})-y^{i})^{2}$$取得最小值时可以求得对应的<img src="http://www.forkosh.com/mathtex.cgi? \theta">。

怎样求得代价函数的最小值：**Gradient Descent**和**Normal Equation**。

### 梯度下降法（Gradient Descent）

**基本思想：**赋给<img src="http://www.forkosh.com/mathtex.cgi? \theta">一个初始值，通过迭代不断更新<img src="http://www.forkosh.com/mathtex.cgi? \theta">的值使代价函数达到最小：$$\theta\_{j}:=\theta\_{j}-\alpha\frac{\partial}{\partial\theta\_{j}}J(\theta)$$其中<img src="http://www.forkosh.com/mathtex.cgi? \alpha">为学习速率，它的大小决定梯度下降法的快慢；<img src="http://www.forkosh.com/mathtex.cgi? \frac{\partial}{\partial\theta_{j}}J(\theta)">为代价函数的偏导数，所以$$\theta\_{j}:=\theta\_{j}+\alpha(y^{(i)}-h\_{\theta}(x^{(i)}))x^{i}\_{j}$$

梯度下降法收敛速度比较慢，另外一种直接计算的方法是Normal Equation。

### Normal Equation

将训练集特征表示为X矩阵，结果表示为y向量，那么<img src="http://www.forkosh.com/mathtex.cgi? \theta">为$$\theta=(X^{T}X)^{-1}X^{T}y$$

### Gradient Descent和Normal Equation的适用情况

Gradient Descent缺点：

- 需要选择学习速率<img src="http://www.forkosh.com/mathtex.cgi? \alpha">
- 需要进行迭代，速度较慢。

Normal Equation缺点：

- 特征较多时，计算量大，耗时多。（如果特征上万维，计算速度会变慢，此时可以考虑梯度下降法）

Gradient Descent比较常用。
