# 斯坦福机器学习整理1——第一周

## 监督学习（Supervised Learning）
监督学习可以分为**分类算法**和**回归算法**。回归：根据之前的数据预测出一个准确的数值。分类：预测离散的输出值。

### 线性回归
用一条直线来拟合需要的数据<img src="http://www.forkosh.com/mathtex.cgi? h(x)=\theta_{0}+\theta_{1}x">（假设函数）。

![lineFunction](file://./figures/lineFunction.png)

- 怎样求假设函数中<img src="http://www.forkosh.com/mathtex.cgi? \theta_{0},\theta_{1}">的值：
就是让**代价函数(cost function)**<img src="http://www.forkosh.com/mathtex.cgi?  J(\theta)=\frac{1}{2m}\sum^{m}_{i=1}(h_{\theta}(x^(i))-y^(i))^{2}">（表示预测值和实际值之间的误差）取得最小值。代价函数有时也被称为平方误差函数。

- 求代价函数最小值的方法：**梯度下降法（Gradient desent）**。

## 梯度下降（Gradient descent）
梯度下降法是怎样工作的：
1. 从<img src="http://www.forkosh.com/mathtex.cgi? \theta_{0},\theta_{1}">开始，将它们初始化，通常都设置为0；。
2. 不断改变<img src="http://www.forkosh.com/mathtex.cgi? \theta_{0},\theta_{1}">的值得到<img src="http://www.forkosh.com/mathtex.cgi? J(\theta_{0},\theta_{1})}">，直到得到期望的最小值。

梯度下降算法（Gradient descent algorithm）
	重复直到收敛<img src="http://www.forkosh.com/mathtex.cgi? \{\theta_{j}: = \theta_{j}-\alpha\frac{\partial}{\partial\theta_{j}}J(\theta_{0},\theta_{1})\}"> <img src="http://www.forkosh.com/mathtex.cgi? (for j=0~and ~j=1)">
	公式中:=为赋值符号（=为相等符号）；<img src="http://www.forkosh.com/mathtex.cgi?  \alpha">被称为学习速率，它的值越大，梯度下降的速度越快，但如果太大，梯度下降法可能越过最低点，甚至无法收敛，它的值越小，梯度下降速度越慢。
    正确的更新顺序：
    <img src="http://www.forkosh.com/mathtex.cgi? temp0:=\theta_{0}-\alpha\frac{\partial}{\partial\theta_{0}}J(\theta_{0},\theta_{1})">
    <img src="http://www.forkosh.com/mathtex.cgi? temp1:=\theta_{1}-\alpha\frac{\partial}{\partial\theta_{1}}J(\theta_{0},\theta_{1})">
    <img src="http://www.forkosh.com/mathtex.cgi? \theta_{0}:=temp0">
    <img src="http://www.forkosh.com/mathtex.cgi? \theta_{1}:=temp1">

代价函数为凸函数（convex function）时，只有全局最优解，总是收敛到全局最优值，没有其他的局部最优值。








