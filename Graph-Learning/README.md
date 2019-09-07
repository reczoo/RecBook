# Graphs
A curated list of awesome resources on graph learning

+ [Graph Embedding](#KGraph-Embedding)
+ [Knowledge Graph](#Knowledge-Graph)
+ [Graph Neural Networks](#Graph-Neural-Networks)
+ [Relational Network](#Relational-Network)


### Graph Embedding
1. [**KDD'18**] [Billion-scale Commodity Embedding for E-commerce Recommendation in Alibaba](https://arxiv.org/abs/1803.02349), Jizhe Wang, Pipei Huang, Huan Zhao, Zhibo Zhang, Binqiang Zhao, Dik Lun Lee. [**Alibaba**]
   > 本文将基于DeepWalk的graph embedding应用召回。首先根据用户点击序列进行建图，用户点击A-->B，即有一条边，边权重为co-occurrences. Item graph建好后根据random walk的方式生成sequences，再利用word2vec进行embedding. 改进之处： 1. 节点加入side information，即category, shop, price等item信息 2. GES直接利用side info做average，EGES进而考虑weigted average，就是每个item对于side info的权重不同，而这个权重是学出来的，每个item都不同。对于cold-start item，直接去side info的平均作为item embedding。[[Read more...](https://blog.csdn.net/sxf1061926959/article/details/88078008)]

1. [**KDD'18**] [Deep Variational Network Embedding in Wasserstein Space](http://pengcui.thumedialab.com/papers/NE-DeepVariational.pdf), by Dingyuan Zhu, Peng Cui, Daixin Wang, Wenwu Zhu.
   > 本文DVNE也考虑first + second order proximity用于. First order: 相邻节点embedding要相似，这个同word2vec的objective. Second order:  拥有公共neighbors的节点要相似。本文利用gussian embedding和Wasserstein distance进行改进，将node映射为gaussian distribution, 并利用W2-distance来计算两个node之间的距离。对于second-order proximity, 使用Autoencoder的方法encode每个节点的neighbors (节点的transition vector to neighbors)，得到中间表示层u, Sigma, 再decode的出节点的neighbors. 两个order的loss共同优化。

### Knowledge Graph
1. [**CIKM'18**] [RippleNet: Propagating User Preferences on the Knowledge Graph for Recommender Systems](https://arxiv.org/abs/1803.03467), by Hongwei Wang, Fuzheng Zhang, Jialin Wang, Miao Zhao, Wenjie Li, Xing Xie, Minyi Guo. 

### Graph Neural Networks

### Relational Network