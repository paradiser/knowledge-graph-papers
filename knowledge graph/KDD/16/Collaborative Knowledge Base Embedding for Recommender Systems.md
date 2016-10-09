## Collaborative Knowledge Base Embedding for Recommender Systems ##

### Abstract ###

* 传统的协同过滤算法受数据稀疏性的影响而性能受限，本文想利用知识库中的异构信息来提升推荐系统的推荐质量；
* 本文设计了三个部件来提取item的语义表示：
	* 结构信息：用`TransR`来提取结构化表示；
	* 文本信息：用`stacked denoising auto-encoders`；
	* 可视化信息：`stacked convolutional auto-encoders`；
* 然后本文设计了一个框架：`Collaborative Knowledge Base Embedding`，联合学习协同过滤中的隐表示和知识库中的语义表示。