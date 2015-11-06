# 机器学习整理1

## 监督学习（Supervised Learning）
监督学习可以分为**分类算法**和**回归算法**。回归：根据之前的数据预测出一个准确的数值。分类：预测离散的输出值。

### 线性回归
用一条直线来拟合需要的数据<img src="http://www.forkosh.com/mathtex.cgi? h(x)=\theta_{0}+\theta_{1}x">（假设函数）。

![lineFunction](file://./figures/lineFunction.png)

- 怎样求假设函数中<img src="http://www.forkosh.com/mathtex.cgi? \theta_{0},\theta_{1}">的值：
就是让**代价函数(cost function)**<img src="http://www.forkosh.com/mathtex.cgi?  \frac{1}{2m}\sum^{m}_{i=1}(h_{\theta}(x^(i))-y^(i))^{2}">（表示预测值和实际值之间的误差）取得最小值。代价函数有时也被称为平方误差函数。

- 求代价函数最小值的方法：梯度下降法（Gradient desent）。

## 梯度下降（Gradient descent）