
### Teacher-Student Network 

1. [**NIPS'18**] [KDGAN: Knowledge Distillation with Generative Adversarial Networks](https://papers.nips.cc/paper/7358-kdgan-knowledge-distillation-with-generative-adversarial-networks), by Xiaojie Wang, Rui Zhang, Yu Sun, Jianzhong Qi. [**Twitter**]

1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [**Alibaba**]
    > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。

1. [] Knowledge Distillation Across Ensembles of Multilingual Models for Low-resource Languages

1. [] Distilling Knowledge from Ensembles of Neural Networks for Speech Recognition

1. [] Robust Speech Recognition Using Generalized Distillation Framework

1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 

1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
    > Hinton首先提出了Knowledge Distillation (KD)的概念，通过teacher-student架构将复杂网络的知识transfer到简单sudent网络中，提升student的效果。与直接用teacher网络的output作为label学习不同，KD采用了一个temperature的技巧，将softmax的输出进行了转化，能够提供更细节的label。但本质来说，KD利用的是label之间的相关性，相当于把原始one-hot的label变成了连续分布，这样student网络也能更好的学习。也是因为这样，KD在二分类的效果一般。同时，KD相当于对student加了一个regularizer，所以和dropout的效果会相互抵消。[[Read more...](https://www.zhihu.com/question/50519680)]

### Graph Convolution Networks 

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


### Adversarial Learning

