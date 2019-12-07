# Knowledge Distillation

### Understanding KD
1. [**ICML'19**] [Towards Understanding Knowledge Distillation](http://proceedings.mlr.press/v97/phuong19a.html), by Mary Phuong, Christoph Lampert. 
1. [**Arxiv'18**] [Training Deep Neural Networks in Generations: A More Tolerant Teacher Educates Better Students](https://arxiv.org/abs/1805.05551), by Chenglin Yang, Lingxi Xie, Siyuan Qiao, Alan Yuille.
1. **[Arxiv'19]** On the Efficacy of Knowledge Distillation, by Jang Hyun Cho, Bharath Hariharan.
1. **[Arixiv'19]** Distillation ≈ Early Stopping? Harvesting Dark Knowledge Utilizing Anisotropic Information Retrieval For Overparameterized Neural Network, by Bin Dong, Jikai Hou, Yiping Lu, Zhihua Zhang.

### Knowledge Type
1. [**CVPR'19**] [Relational Knowledge Distillation](http://openaccess.thecvf.com/content_CVPR_2019/html/Park_Relational_Knowledge_Distillation_CVPR_2019_paper.html), by Wonpyo Park, Dongju Kim, Yan Lu, Minsu Cho.

    > 传统的KD都是teacher的output和student的output进行比较，使得两个点的距离越近越好。本文指出，在KD中用点与点之间的关系更能够表达知识，而不是仅仅使用一个样本点来表征teacher的知识。为了更好的表征知识，本文提出要拉近pair与pair之间（或者是triplet与triplet之间）的距离，而不是点与点的距离。作者提出了RKD，具体的实现是两个loss，一个distance loss可以用来对pair建模，一个angle loss可以用来对triplet建模。同时，作者还指出RKD loss要与传统的点对点loss一起使用效果更佳。

1. **[CVPR’19]** [Knowledge Distillation via Instance Relationship Graph](http://openaccess.thecvf.com/content_CVPR_2019/papers/Liu_Knowledge_Distillation_via_Instance_Relationship_Graph_CVPR_2019_paper.pdf)

    >和Relational Knowledge Distillation这篇类似，将多个sample建图，在逼近的时候不是考虑某一个孤立的点，而是考虑图与图之间的距离。# details TBD

1. **[Arxiv'19]** [Triplet Distillation for Deep Face Recognition](https://arxiv.org/pdf/1905.04457)

1. Knowledge Representing: Efficient, Sparse Representation of Prior Knowledge for Knowledge Distillation

1. [ECCV'18] [Graph Distillation for Action Detection with Privileged Modalities](https://arxiv.org/pdf/1712.00108) **[Google, Li Feifei]**

1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
  
    > Hinton首先提出了Knowledge Distillation (KD)的概念，通过teacher-student架构将复杂网络的知识transfer到简单sudent网络中，提升student的效果。与直接用teacher网络的output作为label学习不同，KD采用了一个temperature的技巧，将softmax的输出进行了转化，能够提供更细节的label。但本质来说，KD利用的是label之间的相关性，相当于把原始one-hot的label变成了连续分布，这样student网络也能更好的学习。也是因为这样，KD在二分类的效果一般。同时，KD相当于对student加了一个regularizer，所以和dropout的效果会相互抵消。[[Read more...](https://www.zhihu.com/question/50519680)]
    >
    
1. **[Arxiv'19]** [Knowledge Distillation from Internal Representations](https://arxiv.org/pdf/1910.03723) **[Amazon]**

    > 本文是针对BERT的distillation，目的是将BERT-base压缩成原层数的1/2。传统的KD只是通过label来在两个网络之间传递知识，本文额外地使用了内部的attention矩阵，使得两个网络的attention矩阵的KL散度最小。另外，由于BERT是一个多层结构，作者也提出了一个progressively的训练方式，在训练的过程中，先约束前面几层，随着训练的进行，逐渐开始约束后面几层。这样做的好处是使得模型模仿的难度减小。

### Transfer Scheme
1. **[ICLR'19]** [Knowledge Flow: Improve Upon Your Teachers](https://arxiv.org/pdf/1904.05878.pdf)

1. [**Arxiv'19**] [Improved Knowledge Distillation via Teacher Assistant: Bridging the Gap Between Student and Teacher](https://arxiv.org/abs/1902.03393), by Seyed-Iman Mirzadeh, Mehrdad Farajtabar, Ang Li, Hassan Ghasemzadeh. [**DeepMind**]

   > 作者指出，在teacher和student的capacity差距（gap）比较大的时候，transfer的效果会比较差。这种时候需要引入一个中等size的TA，它的capacity介于teacher的student之间，来对这个gap进行衔接。也即从传统的T->S的KD变成了T->TA->S。

1. [**ICLR'16**] [Net2Net: Accelerating Learning via Knowledge Transfer](https://arxiv.org/abs/1511.05641), by Tianqi Chen, Ian Goodfellow, Jonathon Shlens. [**Google**]

+ **RL for KD**
1. [**ICLR'18**] [N2N Learning: Network to Network Compression via Policy Gradient Reinforcement Learning](https://arxiv.org/abs/1709.06030), by Anubhav Ashok, Nicholas Rhinehart, Fares Beainy, Kris M. Kitani. [**Volvo**]

+ **Adversarial KD**
1. [**NeurIPS'18**] [KDGAN: Knowledge Distillation with Generative Adversarial Networks](https://papers.nips.cc/paper/7358-kdgan-knowledge-distillation-with-generative-adversarial-networks), by Xiaojie Wang, Rui Zhang, Yu Sun, Jianzhong Qi. [**Twitter**]
Adversial learning multiple teachers
MEAL: Multi-Model Ensemble via Adversarial Learning
1. [**ICASSP'18**] [Adversarial Teacher-Student Learning for Unsupervised Domain Adaptation](https://arxiv.org/abs/1804.00644), by Zhong Meng, Jinyu Li, Yifan Gong, Biing-Hwang (Fred) Juang.
1. An Adversarial Feature Distillation Method for Audio Classification


### Self Distillation
1. [**AAAI'19**] [Data-Distortion Guided Self-Distillation for Deep Neural Networks](https://aaai.org/ojs/index.php/AAAI/article/view/4498), by Ting-Bing Xu, Cheng-Lin Liu.

1. [**ICML'18**] [Born Again Neural Networks](https://arxiv.org/pdf/1805.04770.pdf), by Tommaso Furlanello, Zachary C. Lipton, Michael Tschannen, Laurent Itti, Anima Anandkumar. [**Amazon**]

   > 本文不将KD用于模型压缩，而是使得teacher和student的结构相同，通过训练一个序列的模型，每个时刻的模型都向上一个时刻的模型进行蒸馏。作者发现通过这样做，在不改变模型结构的情况下，能够显著的提升模型的性能。同时，作者发现KD引入的梯度可以分解为两部分，一部分是dark knowledge term，包含了对非groundtruth的label的比较的信息；另一部分是对true label的一个rescaling，相当于teacher通过判断true label的confidence，对true label进行一个加权。

1. Snapshot Distillation: Teacher-Student Optimization in One Generation

### Data Distillation

1. [**Arxiv'18**] [Dataset Distillation](https://arxiv.org/abs/1811.10959), by Tongzhou Wang, Jun-Yan Zhu, Antonio Torralba, Alexei A. Efros. [**Facebook**]

1. [**CVPR'18**] [Data Distillation: Towards Omni-Supervised Learning](https://arxiv.org/pdf/1712.04440.pdf ) **[Facebook]**

   > 传统的半监督学习理论上最多只能达到全监督的效果，也即fully-supervised是一个上界，为了追求更高的性能，本文提出的方法，可以作为fully-supervised的下界，即可能达到比fully-supervised更好的效果。文中提出的方法需要labeled data和大量的un-labeled data，通过用labeled data先训练一个模型，然后用这个训练好的模型去预测un-labeled data以得到generated label，最后用labeled data + generated label data一起去训练模型以得到更好的效果。本文的主要创新在于如何得到generated label，如果是直接预测，作者认为可能无法包含有意义的信息，因此，作者在得到generated label前，将un labeled data进行了transform（rescaling，crops等等），然后再ensemble，作为某个样本的generated label。例如，样本A被transform成了A+, A-, A\*，最后A的generated label就是ensemble(T(A+), T(A-), T(A\*))。

### Data-free Distillation

1. [**ICML'19**] [Zero-Shot Knowledge Distillation in Deep Networks](https://arxiv.org/abs/1905.08114), by Gaurav Kumar Nayak, Konda Reddy Mopuri, Vaisakh Shaj, R. Venkatesh Babu, Anirban Chakraborty.

1. [**ICCV'19**] [DAFL: Data-Free Learning of Student Networks](https://arxiv.org/abs/1904.01186), by Hanting Chen, Yunhe Wang, Chang Xu, Zhaohui Yang, Chuanjian Liu, Boxin Shi, Chunjing Xu, Chao Xu, Qi Tian. [**Huawei**]

   > 本文希望解决因为隐私或安全问题无法获取原始数据下的蒸馏，在仅有trained teacher，而不得到用于训练teacher的数据的情况下，训练逼近teacher的student。  具体地，本文用GAN的思路，将训练好的teacher作为discriminator，训练一个generator。在得到generator之后，用generator生成虚拟的数据，然后用这些数据进行蒸馏。

1. [**NeurIPS'17** workshop] [Data-Free Knowledge Distillation for Deep Neural Networks](https://arxiv.org/abs/1710.07535), by Raphael Gontijo Lopes, Stefano Fenu, Thad Starner.

### Online Distillation

1. Large scale distributed neural network training through online distillation 【分布式在线蒸馏】

1. **[NAACL'19]** [Online Distilling from Checkpoints for Neural Machine Translation](https://www.aclweb.org/anthology/N19-1192.pdf) 【在线蒸馏】

    > 目前训练deep model的方法都是offline learning，即用一个dev set来验证训练的效果是否好，并且在表现好的地方存checkpoint，最后再ensemble这些checkpoint，以达到更好的表现。这样做有一个缺点，即在训练的过程中，后期的ensemble不会影响到training process，因此模型的性能就被原始的training process限制住了。作者提出了使用online的方法来影响这个training process，即在存checkpoint的时候，就把这个checkpoint当做teacher，下一步训练就同时向这个checkpoint和原始label学习。

1. Temporal Ensembling for Semi-Supervised Learning

1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [**Alibaba**]
  
    > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。
    
1. Knowledge Distillation by On-the-Fly Native Ensemble
### Ensemble Distillation
1. [**KDD'17**] [Learning from Multiple Teacher Networks](https://www.kdd.org/kdd2017/papers/view/learning-from-multiple-teacher-networks), by Shan You, Chang Xu, Chao Xu, Dacheng Tao

1. Knowledge Distillation by On-the-Fly Native Ensemble

1. [**ICLR'19**] [Multilingual Neural Machine Translation with Knowledge Distillation](https://arxiv.org/abs/1902.10461), by Xu Tan, Yi Ren, Di He, Tao Qin, Zhou Zhao, Tie-Yan Liu. [**Microsoft**]

   > 本文用KD来提升多语言翻译模型的准确性。多语言翻译模型通常是一个模型拥有翻译多pair语言的能力，作者发现一般情况下，针对同一pair语言，多语言翻译模型的效果不如单语言翻译模型。因此作者用单语言模型作为teacher，来针对性地教多语言模型的某个语言。可以理解为是一个多任务模型，每个任务都有一个老师来教。

1. FEED: Feature-level Ensemble Effect for knowledge Distillation

1. Distilled Person Re-identification: Towards a More Scalable System

1. ~~Unfolding and Shrinking Neural Machine Translation Ensembles~~

   > 本文提出了通过unfolding和shrinking来简化一个ensemble模型。以两个模型的ensemble为例，unfolding可以理解为两个模型共享同一个输入层，并且将隐藏层拼在一起，将两个小模型变成了一个大模型。这样做的好处是forward的时候将两次小矩阵乘法变成了一个大矩阵乘法，这样能充分发挥GPU的作用。另一个步骤是shrinking，即将网络中冗余的节点进行剪枝。

1. EnsembleNet: End-to-End Optimization of Multi-headed Models

1. Ensemble Distillation for Neural Machine Translation

1. Efficient Knowledge Distillation from an Ensemble of Teachers

1. [] Knowledge Distillation Across Ensembles of Multilingual Models for Low-resource Languages

1. [] Distilling Knowledge from Ensembles of Neural Networks for Speech Recognition

1. [] Robust Speech Recognition Using Generalized Distillation Framework

### Knowledge Amalgamation

1. **[IJCAI 2019]** [Knowledge Amalgamation from Heterogeneous Networks by Common Feature Learning](https://arxiv.org/PDF/1906.10546)

   > 很多研究者都会将自己在不同dataset上训练的模型公布，因此目前我们很容易得到很多异构的模型，作者提出通过knowledge amalgamation来聚合这些模型，以得到一个更小的，multi-talented的模型。具体地，作者先将不同teacher的最后一层取出来，与student的特征一起，映射到同一个向量空间，在这个向量空间缩小student与teacher的距离。特别地，作者还加了一个辅助loss，保证映射后的向量与映射前的向量之间能够reconstruction。

1. Customizing Student Networks From Heterogeneous Teachers via Adaptive Knowledge Amalgamation

1. Student Becoming the Master: Knowledge Amalgamation for Joint Scene Parsing, Depth Estimation, and More

1. Highlight Every Step: Knowledge Distillation via Collaborative Teaching

1. Amalgamating Filtered Knowledge: Learning Task-customized Student from Multi-task Teachers

1. Amalgamating knowledge towards comprehensive classification

1. **[Arxiv'17]** [Knowledge Concentration: Learning 100K Object Classifiers in a Single CNN](https://arxiv.org/pdf/1711.07607.pdf) **[Google]**

   > 对于图像分类问题，我们需要一个能够细粒度分类的模型，比如一个模型能够辨别100K个类别。通常的做法都是对某一个类别训练一个专家，但是这样做会导致极大的复杂性和高昂的inference时间。因此，作者通过使用KD来学一个能够handle大量类别（100K）的单一模型。此外，作者还提出了self-paced learning mechanism来自动的适应对不同teacher学习的程度；也提出了structurally connected layers，来避免最后一个输出层的参数太多（因为分类的数目很多）。

### Applications
+ **RL**
1. [**AISTATS'19**] [Distilling Policy Distillation](https://arxiv.org/pdf/1902.02186.pdf), by Wojciech Marian Czarnecki, Razvan Pascanu, Simon Osindero, Siddhant M. Jayakumar, Grzegorz Swirszcz, Max Jaderberg. [**DeepMind**]

+ **Learning from Noisy Labels**
1. **[NeurIPS'18]** [Learning from Noisy Labels with Distillation Co-teaching: Robust training of deep neural networks with extremely noisy labels](https://arxiv.org/abs/1804.06872)

  > 本文使用两个网络交替学习的方法来解决数据集中噪声较多的问题。深度网络拥有记忆数据的能力，通常在刚开始的几个epoch能够记忆非噪声的数据，随着训练的加深，在后期会记忆噪声。基于这个假设，作者用两个网络A,B来进行co-training，给一个batch，分别feed给A和B，这样就可以让A,B分别判断这个batch中每个样本的loss，根据loss进行排序，根据一个动态比例R筛选出loss最小的一部分样本。用A筛后，剩下的样本feed给B进行训练，B筛后的样本用于给A进行训练。比例R是动态的,在训练开始前的几个epoch较大,后期较小,因为网络更有可能在后期记忆噪声.

+ **Model Unification**
1. Unifying Heterogeneous Classifiers with Distillation
1. Unifying and Merging Well-trained Deep Neural Networks for Inference Stage

+ **Privileged Information**
1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 

1. **[Arxiv'19]** Privileged Features Distillation for E-Commerce Recommendations **[Alibaba]**

   > 在CTR预估场景中，privileged feature是只能在训练的时候获得，inference的时候无法获得的特征，比如dwell time，只有在用户点击之后才能得到。通常为了保证训练和inference时候的特征是对齐的，往往在训练的时候不使用privileged feature，但是这些feature的信息量是很大的，因此本文使用KD将privileged feature引入到inference阶段。具体地，在训练teacher的时候加入privileged feature，student则使用常规的feature，最后inference的时候只使用student model。这样做的好处在于student并没有引入更多的特征，但是在训练的时候就已经学到了privileged feature的信息。

1. Learning with Privileged Information via Adversarial Discriminative Modality Distillation

1. Learning to Rank Using Privileged Information

+ **Recommendation**
1. Adversarial Distillation for Efficient Recommendation with External Knowledge
1. [**Arxiv'19**] [Binarized Collaborative Filtering with Distilling Graph Convolutional Networks](https://arxiv.org/abs/1906.01829), by Haoyu Wang, Defu Lian, Yong Ge.

