## Locally Adaptive Translation for Knowledge Graph Embedding ##

### Abstract ###

* 现有的方法，如`TransE`和`TransH`，通过在数据上定义一个基于全局的边缘损失函数来学习`embedding`表示；
* 然而有两个局限：1 模型参数是由一系列数据组成的封闭集合，2 忽略了两个不同实体和关系组成的知识图谱都有不同的**局部性**；
* 本文提出了`locally adaptive translation`,通过自适应确定不同的知识图谱的边缘来找到最优的损失函数。