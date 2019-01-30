

### Graph Convolution Networks 
1. [**AAAI'19**] [Graph Convolutional Networks for Text Classification](https:\\arxiv.org\pdf\1809.05679.pdf), by Liang Yao, Chengsheng Mao, Yuan Luo. [[Notes](./2019.md#aaai19)]


### Teacher-Student Network 
+ [**AAAI'18**] Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106.pdf), *AAAI*, 2018.
  > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。


1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 
1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. 