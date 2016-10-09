## Representation Learning of Knowledge Graphs with Entity Descriptions ##

### Abstract ###

* 现有的方法侧重于学习如何表示知识三元组（实体-关系-实体），但是现有的方法很难利用好知识图谱中实体的**精炼的描述**；
* 本文提出了新的知识图谱的表示学习方法，我们使用了两种编码方式：`continuous bag-of-words`和`deep convolutional neural models`，我们使用三元组和实体描述共同进一步学习知识表示；
* [作者分享的源码](https://github.com/xrb92/DKRL)。



### Introduction ###

#### Motivation ####

* 随着图的规模越来越大，传统的基于图的方法已克服不了计算效率和数据稀疏性的问题。所以，知识图谱的表示学习油然而生，实体和关系被一组低维向量空间表示（embedding）。

#### Innovation ####

* 不仅对传统的三元组建模，也对**实体描述**建模，模型叫 *Description-Embodied Knowledge Representation
Learning (DKRL).*，其中三元组建模采用了传统的`TransE`算法，实体描述采用了`continuous bag-of-words`和`deep convolutional neural models`。

#### Evaluation ####

* 两个基准：知识图谱补全（knowledge graph completion）和实体类型分类（entity type classification）。



### Methodology ###

* **Continuous Bag-of-words Encoder：**用传统的文本特征提取方法，如`TF-IDF`，来选出top n个实体描述的关键词，将这些关键词的embedding加和，便是这个实体的embedding；
* **Convolutional Neural Network Encoder：**因为CBOW忽略了描述中的**词序信息**，需要CNN来挖掘隐藏在词序中的文本信息。

#### 

