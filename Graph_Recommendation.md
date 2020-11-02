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

1. [**SIGIR'19**] [Neural Graph Collaborative Filtering](https://arxiv.org/abs/1905.08108), by Xiang Wang, Xiangnan He, Meng Wang, Fuli Feng, Tat-Seng Chua.
    > 传统的CF没有显示的将user-item的高阶相邻关系映射到embedding中，本文提出了基于GNN中的embedding propagation机制将user的embedding传递给item、item的embedding传递给user，通过多层embedding propagation累加，捕获high-order connectivity. 与之前work中item graph不同，本文的message passing包含一个点积项，即把u_i与i_j的点积进行传递，有点类似relational network中的做法。同时，这样建模也能看做是SVD++ (neighborhood)算法的generalization。最后CF依然是u和i的点积来计算，并用BPR loss来利用implicit feedback做训练。最后评测了NDCG@K和Recall@K。

1. [**WWW'19**] [Graph Neural Networks for Social Recommendation](https://arxiv.org/abs/1902.07243), by Wenqi Fan, Yao Ma, Qing Li, Yuan He, Eric Zhao, Jiliang Tang, Dawei Yin. [**JD**]

1. [**WWW'19**] [Heterogeneous Graph Attention Network](https://arxiv.org/abs/1903.07293), by Xiao Wang, Houye Ji, Chuan Shi, Bai Wang, Peng Cui, P. Yu, Yanfang Ye.
    > 当前的GNN都是建立在同构图(homogeneous)上的模型，本文考虑了节点的不同性质(heterogeneous)，节点与节点之间通过meta-path建立连接。HAN提出了node-level和semantic-level两层attention，首先考虑了同一类型meta-path的节点中的重要性并做attention aggregation, 每种meta-path得到一个node vector。然后再对K个node vectors计算相应地重要性再做aggregation，得到最终的node representation，用于节点分类或聚类任务。Node attention以当前node 作为key，计算与其他节点的weight；semantic attention以一个未知的q作为key，聚合多类型下的node vector。 实验对比了DeepWalk、GCN和GAT算法，都有提高。

1. [**AAAI'19**] [Graph Convolutional Networks for Text Classification](https:\\arxiv.org\pdf\1809.05679.pdf), by Liang Yao, Chengsheng Mao, Yuan Luo. [[Notes](./2019.md#aaai19)]
   > 本文建立了word-word和word-document的一个全局graph，其中word与word之间的边用PMI作为权重，document与word的边使用TF-IDF作为权重，这个graph有效关联了全局的统计信息。相比之前模型针对单个句子建模时只考虑的local context，例如当每个batch只更新当前batch的word向量。但基于graph的模型能有效提取周围node的信息，从而获取了一部分全局信息。Model使用了两层的GCN模型，相当于提取图2-hop的节点信息。最后一层直接将document (node) embedding向量(维度为class label的种类)进行一个softmax进行分类。但是本文的缺陷是只考虑图中已有的节点，如何在test阶段对新的document进行建模还是一个问题。

1. [**AAAI'19**] [Session-based Recommendation with Graph Neural Networks](https://arxiv.org/abs/1811.00855), by Shu Wu, Yuyuan Tang, Yanqiao Zhu, Liang Wang, Xing Xie, Tieniu Tan. [**Microsoft**]

1. [**WWW'18**] [Graph Convolutional Neural Networks for Web-Scale Recommender Systems](https://arxiv.org/abs/1806.01973), by Rex Ying, Ruining He, Kaifeng Chen, Pong Eksombatchai, William L. Hamilton, Jure Leskovec. [**Pinterest**]
    > 本文利用GNN的思路(GraphSAGE算法)来处理item (node) embedding，首先利用了boards-pins的包含关系建图，再对neighbors采样(importance sampling)做信息聚合，这里利用item的内容特征也利用item graph的structure信息。聚合之后的vector与自身vector做融合得到更新的节点vector。最终的node embedding supervision使用用户点击行为，用户同一session点击的两个item为正，当前item与随机采到的item为负。负采样做了优化：personalized randomwalk后top2000-5000的样本为hard negatives。离线评价指标为MRR。综上，GNN使用了两个图的信息（boards-pins graph和点击图）。

    
### Relational Network

1. [**NeurIPS'18**] [Recurrent Relational Networks](https://arxiv.org/abs/1711.08028), by Rasmus Berg Palm, Ulrich Paquet, Ole Winther. [**Google**]
    > 本文改进了Simple Relational Network [NIPS'17]的版本，由原来的单层改为多层recurrent relational network，并用于解9x9的数独问题。RRN包含message passing, recurrent node updates, supervised training三步。Message passing即从邻接节点获取融合消息m_ij = f(hi, hj), node updates即利用m_ij更新当前节点hi=g(hi, xi, mi)。最后supervised training构建node classficaiton模型r(hi)或graph classificaiton模型r(sum(hi))。f, g, r都可以是MLP映射。该模型框架比较通用

1. [**NeurIPS'18**] [LinkNet: Relational Embedding for Scene Graph](https://papers.nips.cc/paper/7337-linknet-relational-embedding-for-scene-graph.pdf), by Sanghyun Woo, Dahun Kim, Donghyeon Cho, In So Kweon.

1. [**NeurIPS'17**] [A Simple Neural Network Module for Relational Reasoning](https://papers.nips.cc/paper/7082-a-simple-neural-network-module-for-relational-reasoning.pdf), Adam Santoro, David Raposo, David G. Barrett, Mateusz Malinowski, Razvan Pascanu, Peter Battaglia, Timothy Lillicrap. [**Google**]
    > 本文提出了一个简单有效的单层Relational network。即RN(O)=f(sum(g(oi, oj))) 这里g, f都是MLP网络。g(oi, oj)考虑一个sample内任意两个object之间的关系（这里的object不是raw feature而是CNN之后的latent feature vector），相当于在一个完全图上计算各个边的权重，把重要的关系凸显出来。f函数即是综合考虑所有的关联关系，进行预测。在VQA物体位置问答中，该模型达到了最佳效果。[[Read more...](https://zhuanlan.zhihu.com/p/34969534)]