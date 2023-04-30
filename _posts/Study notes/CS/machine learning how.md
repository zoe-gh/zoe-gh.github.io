not for publish

https://developers.google.com/machine-learning/crash-course/prereqs-and-prework

---

linux, python, java

stage 1:
Andrew Ng的机器学习课程（Machine Learning | Coursera）
Python机器学习 & Introduction to Statistical Learning with R
周志华《机器学习》

stage 2:
Kaggle（Your Home for Data Science）
Sklearn(scikit-learn: machine learning in Python)

stage 3: optional
吴恩达深度学习课程
Deep Learning - by IanGoodFellow

stage 4: 
Elements of Statistical Learning
周志华老师的《机器学习》和李航老师的《统计学习基础》

---

基础篇
1. 《Introduction to Data Mining》，这本书很浅显易懂，没有复杂高深的公式，很合适入门的人。另外可以用这本书做参考《Data Mining : Concepts and Techniques》。第二本比较厚，也多了一些数据仓库方面的知识。如果对算法比较喜欢，可以再阅读《Introduction to Machine Learning》。中文书籍方面，则推荐《机器学习实战》《统计学习方法第二版》。

2. 实现经典算法。有几个部分：

a. 关联规则挖掘 (Apriori, FPTree, etc.)

b. 分类 (C4.5, KNN, Logistic Regression, SVM, etc.)

c. 聚类 (Kmeans, DBScan, Spectral Clustering, etc.)

d. 降维 (PCA, LDA, etc.)

e. 推荐系统 (基于内容的推荐，协同过滤，如矩阵分解等)

然后在公开数据集上测试，看实现的效果。可以在下面的网站找到大量的公开数据集：http://archive.ics.uci.edu/ml/

3. 熟悉几个开源的工具: Weka (用于上手); LibSVM, scikit-learn, Shogun

4. 到 https://www.kaggle.com/ 上参加几个101的比赛，学会如何将一个问题抽象成模型，并从原始数据中构建有效的特征 (Feature Engineering).

到这一步的话基本几个国内的大公司都会给你面试的机会。



进阶篇（如果你已入门，可以看看，否则跳过）
1. 读书，下面几部都是大部头，但学完进步非常大。

a.《Pattern Recognition and Machine Learning》

b.《The Elements of Statistical Learning》

c.《Machine Learning: A Probabilistic Perspective》

第一本比较偏Bayesian；第二本比较偏Frequentist；第三本在两者之间，但我觉得跟第一本差不多，不过加了不少新内容。当然除了这几本大而全的，还有很多介绍不同领域的书，例如《Boosting Foundations and Algorithms》，《Probabilistic Graphical Models Principles and Techniques》；以及理论一些的《Foundations of Machine Learning》，《Optimization for Machine Learning》等等。这些书的课后习题也非常有用，做了才会在自己写Paper的时候推公式。

2. 读论文。包括几个相关会议：KDD，ICML，NIPS，IJCAI，AAAI，WWW，SIGIR，ICDM；以及几个相关的期刊：TKDD，TKDE，JMLR，PAMI等。跟踪新技术跟新的热点问题。当然，如果做相关research，这一步是必须的。例如我们组的风格就是上半年读Paper，暑假找问题，秋天做实验，春节左右写/投论文。

3. 跟踪热点问题。例如最近几年的Recommendation System，Social Network，Behavior Targeting等等，很多公司的业务都会涉及这些方面。以及一些热点技术，例如现在很火的Deep Learning。

4. 学习大规模并行计算的技术，例如MapReduce、MPI，GPU Computing。基本每个大公司都会用到这些技术，因为现实的数据量非常大，基本都是在计算集群上实现的。

5. 参加实际的数据挖掘的竞赛，例如KDDCUP，或 https://www.kaggle.com/ 上面的竞赛。这个过程会训练你如何在一个短的时间内解决一个实际的问题，并熟悉整个数据挖掘项目的全过程。

6. 参与一个开源项目，如上面提到的Shogun或scikit-learn还有Apache的Mahout，或为一些流行算法提供更加有效快速的实现，例如实现一个Map/Reduce平台下的SVM。这也是锻炼Coding的能力。

最后，我总结了深度学习、机器学习领域中所有会用到的数学知识，大家在制定计划时可以以这些知识点为脉络进行学习，如无必要，不要投入太多时间去学习这些以外的知识

微积分
微积分是现代数学的基础，线性代数，矩阵论，概率论，信息论，最优化方法等数学课程都需要用到微积分的知识。单就机器学习和深度学习来说，更多用到的是微分。积分基本上只在概率论中被使用，概率密度函数，分布函数等概念和计算都要借助于积分来定义或计算。 几乎所有学习算法在训练或者预测时都是求解最优化问题，因此需要依赖于微积分来求解函数的极值，而模型中某些函数的选取，也有数学性质上的考量。对于机器学习而言，微积分的主要作用是： 1.求解函数的极值 2.分析函数的性质 下面列出机器学习和深度学习中所需的微积分知识点，显然，不是课本里所讲的所有内容都是需要的，我们只列出所必须的。

极限：极限是高等数学和初等数学的分水岭，也是微积分这座大厦的基石，是导数、微分、积分等概念的基础。虽然在机器学习里不直接用到极限的知识，但要理解导数和积分，它是必须的。

上确界与下确界：这一对概念对工科的微积分来说是陌生的，但在机器学习中会经常用到，不要看到论文或书里的sup和inf不知道什么意思。

导数：其重要性众所周知，求函数的极值需要它，分析函数的性质需要它。典型的如梯度下降法的推导，logistic函数导数的计算。熟练地计算函数的导数是基本功。

Lipschitz连续性：这一概念在工科教材中同样没有提及，但对分析算法的性质却很有用，在GAN，深度学习算法的稳定性、泛化性能分析中都有用武之地。

导数与函数的单调性：某些算法的推导，如神经网络的激活函数，AdaBoost算法，都需要研究函数的单调性。

导数与函数的极值：这个在机器学习中处于中心地位，大部分优化问题都是连续优化问题，因此可以通过求导数为0的点而求函数的极值，以实现最小化损失函数，最大化似然函数等目标。

导数与函数的凹凸性：在凸化，Jensen不等式的证明中都有它的应用。

泰勒公式：又一个核心知识点。在优化算法中广泛使用，从梯度下降法，牛顿法，拟牛顿法，到AdaBoost算法，梯度提升算法，XGBoost的推导都离不开它。

不定积分：积分在机器学习中使用的相对较少，主要用于概率的计算中，它是定积分的基础。

定积分：包括广义积分，被用于概率论的计算中。机器学习中很大一类算法是概率型算法，如贝叶斯分类器，概率图模型，变分推断等。这些地方都涉及到对概率密度函数进行积分。
变上限积分。分布函数是典型的变上线积分函数，同样主要用于概率计算中。

牛顿-莱布尼兹公式。在机器学习中很少直接使用，但它是微积分中最重要的公式之一，为定积分的计算提供了依据。

常微分方程。在某些论文中会使用，但一般算法用不到。

偏导数。重要性不用多说，机器学习里绝大部分函数都是多元函数，要求其极值，偏导数是绕不开的。

梯度。决定了多元函数的单调性和极值，梯度下降法的推导离不开它。几乎所有连续优化算法都需要计算函数的梯度值，且以寻找梯度为0的点作为目标。

高阶偏导数。确定函数的极值离不开它，光有梯度值还无法确定函数的极值。

链式法则。同样使用广泛，各种神经网络的反向传播算法都依赖于链式法则。

Hessian矩阵。决定了函数的极值和凹凸性，对使用工科教材的同学可能是陌生的。

多元函数的极值判别法则。虽然不直接使用，但对理解最优化方法至关重要。

多元函数的凹凸性判别法则。证明一个问题是凸优化问题是离不开它的。

Jacobian矩阵。工科教材一般没有介绍这一概念，但和Hessian矩阵一样，并不难理解，使用它可以简化多元复合函数的求导公式，在反向传播算法中广泛使用。

向量与矩阵求导。常见的一次函数，二次函数的梯度，Hessian矩阵的计算公式要烂熟于心，推导并不复杂。

泰勒公式。理解梯度下降法，牛顿法的优化算法的基石。

多重积分。主要用于概率论中，计算随机向量的积分，如正态分布。

线性代数与矩阵论
相对于微积分，线性代数似乎用的更多，而且有一部分属于矩阵论/矩阵分析的范畴，超出了工科线性代数教材的范围。下面列出线性代数和矩阵论的常用知识点。

向量及其运算：机器学习算法的输入很多时候是向量，如样本的特征向量。因此熟练掌握向量以及常用的运算是理解机器学习的基础。

矩阵及其运算：与向量一样，是线性代数的核心概念，各种运算，常用矩阵，必须烂熟于心。

行列式：直接使用的少，在概率论，某些模型的推导中偶尔使用。

线性方程组：直接使用的少，但这是线性代数的核心内容。

特征值与特征向量：在机器学习中被广泛使用，很多问题最后归结于求解矩阵的特征值和特征向量。如流形学习，谱聚类，线性判别分析，主成分分析等。

广义特征值：工科线性代数教材一般不提及此概念，但在流形学习，谱聚类等算法中经常用到它。

Rayleigh商：工科教材一般不提及它。在某些算法的推导过程中会用到，如线性判别分析。
矩阵的谱范数与条件数：工科教材一般不提及它。在某些算法的分析中会用到它，它刻画了矩阵的重要性质。

二次型：很多目标函数是二次函数，因此二次型的地位不言而喻。

Cholesky分解：某些算法的推导中会用到它，工科教材一般不提及它。

特征值分解：对机器学习非常重要，很多问题最后归结于特征值分解，如主成分分析，线性判别分析等。

奇异值分解：在机器学习中广泛使用，从正态贝叶斯分类器，到主题模型等，都有它的影子。

概率论与信息论

概率论与信息论在机器学习中用得非常多。概率论的知识，一般不超出工科教材的范畴。而信息论是很多同学没有学过的，不过只要你理解了微积分和概率论，理解这些概念并不是难事。下面列出常用的概率论与信息论知识点。

随机事件与概率：这是理解随机变量的基础，也是概率论中最基本的知识。

条件概率与独立性：条件概率非常重要，在机器学习中，只要有概率模型的地方，通常离不开它。独立性在很多地方也被使用，如概率论图模型。

条件独立：在概率论图模型中广泛使用，一定要理解它。

全概率公式：基础公式，地位不用多说。

贝叶斯公式：在机器学习的概率型算法中处于灵魂地位，几乎所有生成模型都要用到它。

离散型随机变量与连续型随机变量：重要性不用多说，概率质量函数，概率密度函数，分布函数，一定要熟练掌握。

数学期望：非常重要，好多地方都有它的影子。

方差与标准差：非常重要，刻画概率分布的重要指标。

Jensen不等式：在很多推导和证明中都要用它，如EM算法，变分推断。

常用概率分布：包括均匀分布，正态分布，伯努利分布，二项分布，多项分布，t分布等，在各种机器学习算法中广泛使用。

随机向量：多元的随机变量，在实际中更有用。

协方差：经常使用的一个概念，如主成分分析，多元正态分布中。

参数估计：包括最大似然估计，最大后验概率估计，贝叶斯估计，核密度估计，一定要弄清楚它们是怎么回事。

随机算法：包括采样算法，遗传算法，蒙特卡洛算法，在机器学习中也经常使用。

信息论中的一些概念，包括熵，交叉熵，KL散度，JS散度，互信息，信息增益，一定要深刻理解这些概念。如果你不理解KL散度，那怎么理解变分推断和VAE？

最优化方法
前面已经说过，最优化方法是机器学习的灵魂，用于确定模型的参数或预测结果。不幸的是，工科专业一般没有学过这门课。不过只要你理解了微积分和线性代数，并不难推导出这些算法。下面列出常用的最优化方法知识点：

梯度下降法：最简单的优化算法，但却很有用，尤其在深度学习中。

随机梯度下降法：在深度学习中的重要性妇孺皆知。

最速下降法：梯度下降法的改进型，是理解梯度提升等算法的基础。

梯度下降法的改进型：如AdaGrad，AdaDelta，Adam等，使用深度学习开源库的时候经常会看到这些名字。

牛顿法：二阶优化算法的典型代表，只是在深度学习中用的少。在logistic回归等算法的训练中会用到它。

拟牛顿法：牛顿法的改进，在条件随机场等模型的训练中会用到L-BFGS等算法。

坐标下降法：在logistic回归等模型的训练中会用到它，不难理解。

凸优化：最优化中的核心概念之一，如果一个问题被证明为凸优化问题，恭喜你，它基本上可以较好的解决。

拉格朗日乘数法：在各种算分的推导中经常使用，如主成分分析，线性判别分析等，如果不熟练掌握它，你将非常艰难。

KKT条件：拉格朗日乘数法扩展到带不等式约束后的版本，在SVM的推导中将会使用。

拉格朗日对偶：不太好理解的知识点，在SVM的推导中经常用到，不过套公式并不难。

多目标优化：一般很少使用，在多目标NAS中会使用它，如帕累托最优等概念。

变分法：用于求解泛函的极值，在某些理论推导中会用到它，如通过变分法可以证明在均值和方差一定的情况下，正态分布的熵最大。

图论
机器学习中的某些问题可以用图论的方法解决，如流形学习，谱聚类。某些算法的表达也可能用到图论的知识，如深度学习中的计算图，NAS中的网络拓扑结构图。概率图模型让很多初学者谈虎色变，它是图论与概率论的完美结合。下面介绍常用的图论知识点。 图的基本概念：如顶点，边，有向图，无向图等。

邻接矩阵与加权度矩阵：图论中的核心概念，边一般都带有权重的。

某些特殊的图：如二部图，有向无环图等，在深度学习中经常会用到他们。

最短路径问题：经典的Dijkstra算法是每个程序员必须掌握的。

拉普拉斯矩阵和归一化拉普拉斯矩阵：比较难理解的概念，机器学习中的很多算法，如流形学习，使用图论的半监督学习，谱聚类都离不开它。理解这个矩阵和它的性质，是理解这些算法的基础。





最后附上自己整理的入门书单和课程，里面小蓝书、花书一类的我没放进去，因为我认为并不适合入门。这里我列的课程和书目都是非常beginner-friendly，适合新手读。其中有些书是几年前我看过的，而有些书是19年才写的，非常接近目前业界的深度学习应用，个人推荐看新书。（不知为何，新书的评分通常更高）

数学课程

麻省理工公开课：线性代数_全35集_网易公开课
可汗学院-线性代数入门
线性代数应该这样学 (豆瓣),
高等微積分 - 臺大開放式課程 (NTU OpenCourseWare)。
概率论与数理统计 (豆瓣)
算法课程

Coursera-机器学习-Andrew Ng
BiliBili-机器学习基石-林轩田
CS231n: Convolutional Neural Networks for Visual Recognition
Deep Learning Tutorial from Stanford -Stanford计算机系官方tutorial，Andrew Ng执笔
An Introduction to Statistical Learning with Applications in R 强烈推荐看Simple版
Python深度学习 豆瓣评分9.6，深度学习类目下排名第一
动手学深度学习 豆瓣评分9.3，李沐老师写的
深度学习入门 豆瓣评分9.4，斋藤康毅大神写的
论文

The Learning Machines - 一个导论性质的文章，让你大致了解深度学习是什么，用来干什么的。
Deep Learning - (Review Article in Nature, May 2015) 三大神 Yann LeCun, Yoshua Bengio, and Geoffrey Hinton的文章，不解释。
Growing Pains in Deep Learning
Deep Learning in Neural Networks - This technical report provides an overview of deep learning and related techniques with a special focus on developments in recent years. 主要看点是深度学习近两年（2012-2014）的进展情况。
深度学习代码库

H2O - 一个开源的可扩展的库，支持Java, Python, Scala, and R
Deeplearning4j - Java库，整合了Hadoop和Spark
Caffe - Yangqing Jia读研究生的时候开发的，现在还是由Berkeley维护。
Theano - 最流行的Python库