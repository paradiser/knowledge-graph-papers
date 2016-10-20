## Collaborative Knowledge Base Embedding for Recommender Systems ##

### Abstract ###

* 传统的协同过滤算法受数据稀疏性的影响而性能受限，本文想利用知识库中的异构信息来提升推荐系统的推荐质量；
* 本文设计了三个部件来提取item的语义表示：
	* 结构信息：用`TransR`来提取结构化表示；
	* 文本信息：用`stacked denoising auto-encoders`；
	* 可视化信息：`stacked convolutional auto-encoders`；
* 然后本文设计了一个框架：`Collaborative Knowledge Base Embedding`，联合学习协同过滤中的隐表示和知识库中的语义表示。

### Introduction ###

* 传统的协同过滤算法存在的问题：
	* 传统的协同过滤算法受数据稀疏性的影响而性能受限；
	* 传统的协同过滤算法无法推荐**新的items**，因为新的商品没有用户的历史反馈信息。
* 现有的基于知识库的工作中存在的问题：
	* 只利用了单一的网络结构信息，忽略了item的其他信息，例如**文本上的、视觉上的**；
	* 依赖于沉重和复杂的特征工程过程来提取特征。
* 本文解决上述问题的方法：
	* 在协同过滤的方法中加入了item的文本内容和可视化内容；
	* 设计了三种embedding的模块，分别表示item的结构，文本和可视化信息。


### Preliminary ###

本文针对用户的隐式反馈信息来考虑推荐这个问题。

![公式1](../images/1.png)

隐式反馈如上公式，user i和 item j有交互就可以设为1(有交互表示user关注过此item)。

本文把item以及和item相关的属性都看做**item entities**。

**提出问题**

* 在给定了结构信息、文本信息、图像信息和用户的隐式反馈信息后，我们给每一个用户推荐一个可能感兴趣的items列表。


### Overview ###

下图是模型框架图：![figure2](../images/2.png)

模型分为两步：先知识库embedding，再联合学习。

### Knowledge Base Embedding ###

#### Structural Embedding ####

**TransR：**
TransR认为实体和关系不在同一个特征空间，所以实体需要通过投影矩阵**M*****r***投影到关系空间，如图所示：![figure2](../images/3.png)

投影后的实体向量为：![figure3](../images/4.png)

打分函数设为： ![figure4](../images/5.png)

**Bayesian TransR：**