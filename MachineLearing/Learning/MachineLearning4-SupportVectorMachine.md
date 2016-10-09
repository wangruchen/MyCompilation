# 机器学习——支持向量机（Support Vector Machine, SVM）

<script type="text/javascript"
 src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

参考：[Standford公开课machine learning](https://class.coursera.org/ml/class/index)

支持向量机（Support Vector Machine, SVM）根据样本的特征，将其映射到高维空间中，在这个空间中建立一个最大间隔超平面，将两类样本划分开。这个超平面成为决策边界（Decision boundary），使用SVM训练分类器时，就是为了得到最大间隔超平面。

## Linear Decision Boundary
不需要引入核函数。

**假设函数：**$$h_{w,b}(x)=g(w^{T}x+b)$$

**代价函数：**$$\min\_{\theta}C\sum^{m}\_{i=1}[y^{(i)}cost\_{1}(\theta^{T}x^{(i)})+(1-y^{(i)})cost\_{0}(\theta^{Tx^{(i)}})]+\frac{1}{2}\sum^{n}\_{i=1}\theta^{2}_{j}$$其中参数<img src="http://www.forkosh.com/mathtex.cgi? C=\frac{1}{\lambda}">，C越大倾向于过拟合，C越小倾向于欠拟合。

cost1和cost0如图![SVM-cost](file:///Users/wangruchen/work/github/wangruchen/MyCompilation/MachineLearing/Learning/figures/SVM-cost.png)

逻辑回归强调所有点尽可能地远决策边界，得到的分类结果越确定。而在分类过程中，我们更应该关注靠近决策边界的样本，让它们尽可能的远离决策边界，这是SVM的思路。

## Non-linear Decision Boundary

对于Non-linear Decision Boundary，利用多项式拟合的方法进行预测，引入核函数。

设<img src="http://www.forkosh.com/mathtex.cgi? f_{1},f_{2},\cdots,f_{n}">为提取的样本特征。

**假设函数：**$$h\_{\theta}(x)=g(\theta\_{0}f\_{0}+\theta\_{1}f\_{1}+\cdots+\theta\_{n}f\_{n})$$当<img src="http://www.forkosh.com/mathtex.cgi? \theta_{0}f_{0}+\theta_{1}f_{1}+\cdots+\theta_{n}f_{n}\ge0">时，<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)=1">，否则<img src="http://www.forkosh.com/mathtex.cgi? h_{\theta}(x)=0">。其中，通过引入*核函数*来表示f。

### 核函数
核函数计算待分类样本与训练样本之间的相似度。

**1、线性核函数**
即不采用核函数。

**2、多项式核**
$$f\_{1}=((xl^{(1)})+1)^{d}$$

**3、高斯核（Gaussian Kernel）（也叫做径向基核，Radial Basis Function，RBF）：**
$$f\_{1}=similarity(x,l^{(1)})=e^{(-\frac{||x-l^{(1)}||^{2}}{2\sigma^{2}})}=e^{(-\frac{\sum^{n}_{j=1}(x-l^{(1)})^{2}}{2\sigma^{2}})}$$其中<img src="http://www.forkosh.com/mathtex.cgi? l">为训练样本，若样本x与<img src="http://www.forkosh.com/mathtex.cgi? l">越相似，<img src="http://www.forkosh.com/mathtex.cgi? f">越接近1；反之越接近0。

**4、Sigmoid核（Sigmoid Kernel）**
$$f=\tanh(x−δ))$$

用核<img src="http://www.forkosh.com/mathtex.cgi? f">代替x得到的**代价函数**为：$$\min\_{\theta}C\sum^{m}\_{i=1}y^{(i)}cost\_{1}(\theta^{T}f^{(i)})+(1-y^{(i)})cost\_{0}(\theta^{T}f^{(i)})+\frac{1}{2}\sum^{n}\_{j=1}\theta^{2}\_{j}
$$


在SVM训练中，将核函数带入代价函数，通过最小化该函数就可得到参数<img src="http://www.forkosh.com/mathtex.cgi? \theta">，并进行预测：

- 若<img src="http://www.forkosh.com/mathtex.cgi? \theta^{T}f\ge0">，预测结果为1；否则为0。

### 参数的确定

- 代价函数中的<img src="http://www.forkosh.com/mathtex.cgi? C=\frac{1}{\lambda}">，C大倾向于过拟合，C小倾向于欠拟合。
- 代价函数中的<img src="http://www.forkosh.com/mathtex.cgi? \sigma^{2}">，<img src="http://www.forkosh.com/mathtex.cgi? \sigma^{2}">大，核函数图像较为扁平；<img src="http://www.forkosh.com/mathtex.cgi? \sigma^{2}">小，核函数图像较为窄尖。

