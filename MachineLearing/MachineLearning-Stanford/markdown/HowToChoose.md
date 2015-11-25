# How to choosing machine learning classifier

参考文章：[How to choose algorithms for Microsoft Azure Machine Learning](https://azure.microsoft.com/en-us/documentation/articles/machine-learning-algorithm-choice/)

怎样选择机器学习分类器，Microsoft Azure Machine Learning Algorithm Cheat Sheet给出了选择分类器的依据。它概括性的将面对的问题简单化，很多方法的方法和问题都没有考虑，打它可以给我们寻找合适的分类器指出一个正确的大致方向。
![Microsoft Azure Machine Learning Algorithm Cheat Sheet](file:///Users/wangruchen/work/github/wangruchen/MyCompilation/MachineLearing/figures/microsoft-machine-learning-algorithm-cheat-sheet.pdf)

## Machine Learning
学习算法分为三种类型：监督学习、非监督学习和强化学习。
### Supervised Learning
有训练集，监督学习的几种类型：分类、回归和异常检测。

- Classification: 预测样本的种类
- Regression: 预测样本的一个值
- Anomaly detection: 异常检测也称为离群点检测，是用来发现不同于预期的样本，例如检测信用卡异常。

### Unsupervised Learning
没有已知分类的训练集。

### Reinforcement Learning(强化学习)
强化学习是一种以环境反馈作为输入的、适应环境的机器学习方法。主要应用在过程控制、调度管理、机器人控制和信息检索等方面。
