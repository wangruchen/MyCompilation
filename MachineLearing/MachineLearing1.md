# 机器学习方法分类
参考文章：[机器学习常见算法分类汇总](http://www.ctocio.com/hotnews/15919.html)

<!-- ## 监督学习
常见算法有： 

1. 逻辑回归（Logistic Regression）
2. 反向传递神经网络（Back Propagation Neural Network）

## 非监督学习
常见算法有：

1. Apriori算法
2. K-Means算法

## 半监督学习
常见算法有：

1. 图论推理算法（Graph Inference）
2. 拉普拉斯支持向量机（Laplacian SVM）

## 强化学习 -->
## 回归算法
机器学习监督学习算法分为**分类算法**和**回归算法**两种，其实就是根据类别标签分布类型为离散型、连续性而定义的。分类算法用于离散型分布预测；回归算法用于连续型分布预测，可以在给定输入的时候预测出一个数值。

常见的回归算法有：

1. 最小二乘法（Ordinary Least Square）
2. 逻辑回归（Logistic Regression）
3. 逐步式回归（Stepwise Regression）
4. 多元自适应回归样条（Multivariate Adaptive Regression Splines）
5. 本地散点平滑估计（Locally Estimated Scatterplot Smoothing）

## 基于实例的算法
常见的算法有：

1. K-Nearest Neighbor(KNN)
2. 学习矢量量化（Learning Vector Quantization, LVQ）
3. 组织映射算法（Self-Organizing Map, SOM）

## 正则化方法
常见算法有：

1. Ridge Regression
2. Least Absolute Shrinkage and Selection Operator(LASSO)
3. 弹性网络（Elastic Net）

## 决策树
常见算法有：

1. 分类及回归树（Classification and Regression Tree, CART）
2. ID3(Iterative Dichotomiser 3)
3. C4.5
4. Chi-squared Automatic Interaction Detection(CHAID)
5. Decision Stump
6. 随机森林（Random Forest）
7. 多元自适应回归样条（MARS）
8. 梯度推进机（Gradient Boosting Machine, GBM）

## 贝叶斯方法
常见算法有：

1. 朴素贝叶斯算法
2. 平均单依赖估计（Averaged One-Dependence Estimators, AODE）
3. Bayesian Belief Network(BBN)

## 基于核的算法
常见算法有：

1. 支持向量机（Support Vector Machine, SVM）
2. 径向基函数（Radial Basis Function, RBF）
3. 线性判别分析（Linear Discriminate Analysis, LDA）

## 聚类算法
常见算法有：

1. K-Means算法
2. 期望最大化算法（Expectation Maximization, EM）

## 关联规则学习
常见算法有：

1. Apriori算法
2. Eclat算法

## 人工神经网络
常见算法有：

1. 感知器神经网络（Perceptron Neural Network）
2. 反向传递（Back Propagation）
3. Hopfield网络
4. 自组织映射（Self-Organizing Map, SOM）

## 深度学习
常见算法有：

1. 受限波尔兹曼机（Restricted Boltzmann Machine, RBN）
2. Deep Belief Networks（DBN）
3. 卷积网络（Convolutional Network）
4. 堆栈式自动编码器（Stacked Auto-encoders）

## 降低维度算法
常见算法包括：

1. 主成分分析（Principle Component Analysis, PCA）
2. 偏最小二乘回归（Partial Least Spuare Regression, PLS）
3. Sammon映射
4. 多维尺度（Multi-Dimensional Scaling, MDS）
5. 投影追踪（Projection Pursuit）

## 集成学习（Ensemble learning）
集成学习是使用一系列较弱的学习器进行学习,并使用某种规则把各个学习结果进行整合从而获得比单个学习器更好的学习效果的一种机器学习方法。集成学习按照基本分类器之间的关系可以分为**异态集成学习**和**同态集成学习**。异态集成学习是指弱分类器之间本身不同,而同态集成 学习是指弱分类器之间本身相同只是参数不同。

常见算法有：

1. Bagging
2. Boostion
3. Gasen