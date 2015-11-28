# 机器学习——逻辑回归（Logistic Regression）

<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

逻辑回归本质上是线性回归，但它是一种二分类算法，其输出值在0到1之间。

**假设函数：**$$h\_{\theta}(x)=g(\theta^{T}x)=\frac{1}{1+e^{-\theta^{T}x}}$$其中$$g(z)=\frac{1}{1+e^{z}}$$为Sigmoid Function，如图![Logistic Function](file:///Users/wangruchen/work/github/wangruchen/MyCompilation/MachineLearing/MachineLearning-Stanford/figures/LogisticFunction.png)。

**具体过程：**

1. 构造假设函数<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)">。
2. 构造代价函数。逻辑回归的代价函数为：$$J(\theta)=\frac{1}{m}\sum^{m}\_{i=1}Cost(h\_{\theta}(x^{(i)}),y^{(i)})=-\frac{1}{m}[\sum^{m}\_{i=1}y^{i}\log h\_{\theta}(x^{(i)})+(1-y^{(i)})\log (1-h\_{\theta}(x^{(i)}))]$$
3. 用梯度下降法求代价函数取得最小值是对应的参数<img src="http://www.forkosh.com/mathtex.cgi? \theta">。$$
\theta_{j}:=\theta\_{j}-\alpha\frac{\partial}{\partial\theta\_{j}J(\theta)}=\theta\_{j}-\alpha\frac{1}{m}\sum^{m}\_{i=1}(h\_{\theta}(x^{(i)})-y^{(i)})x^{(i)}\_{j}$$
4. 求得参数<img src="http://www.forkosh.com/mathtex.cgi? \theta">后代入到假设函数得到分类结果。
	- 如果hθ(x)≥0.5，则预测y=1，既y属于正例；
	- 如果hθ(x)<0.5，则预测y=0，既y属于负例；

**求代价函数最小的方法**

1. Gradient descent（梯度下降法）
2. Conjugated gradient（共轭梯度法）
3. Quasi-Newton（拟牛顿法）
4. BFGS
5. L-BFGs（Limited-memory BFGS）

后面三种方法的优点：1.不需要手动选择学习率<img src="http://www.forkosh.com/mathtex.cgi? \alpha">；2.收敛速度比梯度下降法要快。缺点是算法比梯度下降法要复杂。

## 多分类问题
将多分类问题看成多个二分类问题：保留其中一类，剩下的作为另一类。对于一个新的输入变量x，分别对每一个类进行预测，取概率最大的那一类作为分类结果：$$\max\_{i}h^{(i)}\_{\theta}(x)$$