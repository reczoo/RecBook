
### Teacher-Student Network 

1. [**NIPS'18**] [KDGAN: Knowledge Distillation with Generative Adversarial Networks](https://papers.nips.cc/paper/7358-kdgan-knowledge-distillation-with-generative-adversarial-networks), by Xiaojie Wang, Rui Zhang, Yu Sun, Jianzhong Qi. [**Twitter**]

1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [**Alibaba**]
    > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。

1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 

1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
    > Hinton首先提出了Knowledge Distillation (KD)的概念，通过teacher-student架构将复杂网络的知识transfer到简单sudent网络中，提升student的效果。与直接用teacher网络的output作为label学习不同，KD采用了一个temperature的技巧，将softmax的输出进行了转化，能够提供更细节的label。但本质来说，KD利用的是label之间的相关性，相当于把原始one-hot的label变成了连续分布，这样student网络也能更好的学习。也是因为这样，KD在二分类的效果一般。同时，KD相当于对student加了一个regularizer，所以和dropout的效果会相互抵消。[[Read more...](https://www.zhihu.com/question/50519680)]

### Graph Convolution Networks 

1. [**AAAI'19**] [Graph Convolutional Networks for Text Classification](https:\\arxiv.org\pdf\1809.05679.pdf), by Liang Yao, Chengsheng Mao, Yuan Luo. [[Notes](./2019.md#aaai19)]

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

