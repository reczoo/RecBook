# Knowledge Distillation

1. [**NIPS'18**] [KDGAN: Knowledge Distillation with Generative Adversarial Networks](https://papers.nips.cc/paper/7358-kdgan-knowledge-distillation-with-generative-adversarial-networks), by Xiaojie Wang, Rui Zhang, Yu Sun, Jianzhong Qi. [**Twitter**]

1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [**Alibaba**]
    > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。

1. [] Knowledge Distillation Across Ensembles of Multilingual Models for Low-resource Languages

1. [] Distilling Knowledge from Ensembles of Neural Networks for Speech Recognition

1. [] Robust Speech Recognition Using Generalized Distillation Framework

1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 

1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
    > Hinton首先提出了Knowledge Distillation (KD)的概念，通过teacher-student架构将复杂网络的知识transfer到简单sudent网络中，提升student的效果。与直接用teacher网络的output作为label学习不同，KD采用了一个temperature的技巧，将softmax的输出进行了转化，能够提供更细节的label。但本质来说，KD利用的是label之间的相关性，相当于把原始one-hot的label变成了连续分布，这样student网络也能更好的学习。也是因为这样，KD在二分类的效果一般。同时，KD相当于对student加了一个regularizer，所以和dropout的效果会相互抵消。[[Read more...](https://www.zhihu.com/question/50519680)]