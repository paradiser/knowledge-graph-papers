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