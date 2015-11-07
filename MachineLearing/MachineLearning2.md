# 斯坦福机器学习整理2——第二周

## 多元线性回归
多元是指用来预测多个特征量或变量。
<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)=\theta_{0}x_{0}+\theta_{1}x_{1}+\cdots+\theta_{n}x_{n}=\theta^{T}x,x_{0}=1">
其采用梯度下降法求代价函数最小值：
重复直到收敛<img src="http://www.forkosh.com/mathtex.cgi? \{\theta_{j}: = \theta_{j}-\alpha\frac{\partial}{\partial\theta_{j}}J(\theta_{0},\theta_{1})\}">

## 梯度下降运算中的技巧

### feature scaling（数据归一化方法）
如果一个机器学习问题有多个特征，这些特征取值都在一个相近的范围（归一化），这样梯度下降法能更快的收敛。
feature scaling：将特征取值约束到-1到+1之间。
- mean normalization<img src="http://www.forkosh.com/mathtex.cgi? x=\frac{x-mean}{range}">