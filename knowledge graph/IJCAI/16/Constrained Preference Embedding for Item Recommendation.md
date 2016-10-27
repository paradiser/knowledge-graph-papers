## Constrained Preference Embedding for Item Recommendation ##

### Abstract ###

* 传统的基于矩阵分解的算法，把用户反馈信息看做**标量**，计算出来的preference degree是user向量和item向量的乘积，最后也是以**标量**表示的。
* 而本文用**constrained vectors**表示用户反馈信息，我们发现这种表示比传统的矩阵分解算法在item recommendation上表现更好。

### Introduction ###

传统的矩阵分解技术把用户的显式反馈看做一个个的**数值**，用户和item看做是低维向量，用户和item向量的乘积就是用户对item的偏好程度。

把用户反馈看做标量的不足之处：

* 比如给item打分（1~5分），虽然分值上服从均匀分布，但是偏好程度不是线性的。因为大多数人更倾向于打3~5分，所以1分到3分的差距是大于3分到5分的差距的
* 在一些隐式反馈信息上（如浏览，收藏，标记），传统的方法也只能简单的把观测到的隐式反馈设为1，未被观测的设为0，无法获取**不同行为的偏好程度**；

我们的算法CPE(constrained preference embedding)：

* 我们不把行为看做是数值，而是把它们和user，item一起表示在高维空间，即所有实体和行为都由D维的向量表示。

### Constrained Preference Embedding ###

* [fig.1](https://raw.githubusercontent.com/paradiser/knowledge-graph-papers/master/knowledge%20graph/IJCAI/16/images/1.png)