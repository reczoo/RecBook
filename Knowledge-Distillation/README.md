# Knowledge Distillation

### Understanding KD
1. [**ICML'19**] [Towards Understanding Knowledge Distillation](http://proceedings.mlr.press/v97/phuong19a.html), by Mary Phuong, Christoph Lampert. 

1. [**Arxiv'18**] [Training Deep Neural Networks in Generations: A More Tolerant Teacher Educates Better Students
](https://arxiv.org/abs/1805.05551), by Chenglin Yang, Lingxi Xie, Siyuan Qiao, Alan Yuille.

### Knowledge Type
1. [**CVPR'19**] [Relational Knowledge Distillation](http://openaccess.thecvf.com/content_CVPR_2019/html/Park_Relational_Knowledge_Distillation_CVPR_2019_paper.html), by Wonpyo Park, Dongju Kim, Yan Lu, Minsu Cho.

1. Triplet Distillation for Deep Face Recognition

1. Knowledge Representing: Efficient, Sparse Representation of Prior Knowledge for Knowledge Distillation

1. Graph Distillation for Action Detection with Privileged Modalities

1. [**Arxiv'15**] [Distilling the Knowledge in a Neural Network](https://arxiv.org/pdf/1503.02531), by Geoffrey Hinton, Oriol Vinyals, Jeff Dean. 
    > Hinton首先提出了Knowledge Distillation (KD)的概念，通过teacher-student架构将复杂网络的知识transfer到简单sudent网络中，提升student的效果。与直接用teacher网络的output作为label学习不同，KD采用了一个temperature的技巧，将softmax的输出进行了转化，能够提供更细节的label。但本质来说，KD利用的是label之间的相关性，相当于把原始one-hot的label变成了连续分布，这样student网络也能更好的学习。也是因为这样，KD在二分类的效果一般。同时，KD相当于对student加了一个regularizer，所以和dropout的效果会相互抵消。[[Read more...](https://www.zhihu.com/question/50519680)]

### Transfer Scheme
1. [ICLR'19] Knowledge Flow: Improve Upon Your Teachers

1. [**Arxiv'19**] [Improved Knowledge Distillation via Teacher Assistant: Bridging the Gap Between Student and Teacher](https://arxiv.org/abs/1902.03393), by Seyed-Iman Mirzadeh, Mehrdad Farajtabar, Ang Li, Hassan Ghasemzadeh. [**DeepMind**]

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

1. Snapshot Distillation: Teacher-Student Optimization in One Generation

### Data Distillation

1. [**Arxiv'18**] [Dataset Distillation](https://arxiv.org/abs/1811.10959), by Tongzhou Wang, Jun-Yan Zhu, Antonio Torralba, Alexei A. Efros. [**Facebook**]

1. Data Distillation: Towards Omni-Supervised Learning

### Data-free Distillation

1. [**ICML'19**] [Zero-Shot Knowledge Distillation in Deep Networks](https://arxiv.org/abs/1905.08114), by Gaurav Kumar Nayak, Konda Reddy Mopuri, Vaisakh Shaj, R. Venkatesh Babu, Anirban Chakraborty.

1. [**ICCV'19**] [DAFL: Data-Free Learning of Student Networks](https://arxiv.org/abs/1904.01186), by Hanting Chen, Yunhe Wang, Chang Xu, Zhaohui Yang, Chuanjian Liu, Boxin Shi, Chunjing Xu, Chao Xu, Qi Tian. [**Huawei**]

1. [**NeurIPS'17** workshop] [Data-Free Knowledge Distillation for Deep Neural Networks](https://arxiv.org/abs/1710.07535), by Raphael Gontijo Lopes, Stefano Fenu, Thad Starner.

### Online Distillation

1. Large scale distributed neural network training through online distillation 【分布式在线蒸馏】
1. Online Distilling from Checkpoints for Neural Machine Translation 【在线蒸馏】

1. Temporal Ensembling for Semi-Supervised Learning

1. [**AAAI'18**] [Rocket Launching: A Universal and Efficient Framework for Training Well-performing Light Net](https://arxiv.org/pdf/1708.04106), by Guorui Zhou, Ying Fan, Runpeng Cui, Weijie Bian, Xiaoqiang Zhu, Kun Gai. [**Alibaba**]
    > 该框架Rocket Launching借鉴Teacher-Student网络架构，设计了一个复杂的booster和一个简单的rocket net，复杂网络准确度高但速度慢，简单网络速度快但学习能力有限。本文以复杂网络为teacher来教student网络的学习，构建了cross-encropy和hint loss两个损失函数，最后联合优化。 与传统teacher-student网络的学习不同，本文的training是同时更新teacher和student，保证student在学习路径上也保持与teacher一致。但是反向传播使用了gradient block，也就是hint loss只对student起作用，但是不要影响teacher本身的学习。这点与cross-view training一致。
    
### Ensemble Distillation
1. [**KDD'17**] [Learning from Multiple Teacher Networks](https://www.kdd.org/kdd2017/papers/view/learning-from-multiple-teacher-networks), by Shan You, Chang Xu, Chao Xu, Dacheng Tao

1. Knowledge Distillation by On-the-Fly Native Ensemble
1. [**ICLR'19**] [Multilingual Neural Machine Translation with Knowledge Distillation](https://arxiv.org/abs/1902.10461), by Xu Tan, Yi Ren, Di He, Tao Qin, Zhou Zhao, Tie-Yan Liu. [**Microsoft**]
1. FEED: Feature-level Ensemble Effect for knowledge Distillation
1. Distilled Person Re-identification: Towards a More Scalable System
1. Unfolding and Shrinking Neural Machine Translation Ensembles
1. EnsembleNet: End-to-End Optimization of Multi-headed Models
1. Ensemble Distillation for Neural Machine Translation
1. Efficient Knowledge Distillation from an Ensemble of Teachers
1. [] Knowledge Distillation Across Ensembles of Multilingual Models for Low-resource Languages

1. [] Distilling Knowledge from Ensembles of Neural Networks for Speech Recognition

1. [] Robust Speech Recognition Using Generalized Distillation Framework

### Knowledge Amalgamation

1.Knowledge Amalgamation from Heterogeneous Networks by Common Feature Learning
1. Customizing Student Networks From Heterogeneous Teachers via Adaptive Knowledge Amalgamation
1. Student Becoming the Master: Knowledge Amalgamation for Joint Scene Parsing, Depth Estimation, and More
1. Highlight Every Step: Knowledge Distillation via Collaborative Teaching
1. Amalgamating Filtered Knowledge: Learning Task-customized Student from Multi-task Teachers
1. Amalgamating knowledge towards comprehensive classification
1. Knowledge Concentration: Learning 100K Object Classifiers in a Single CNN

### Applications
+ **RL**
1. [**AISTATS'19**] [Distilling Policy Distillation](https://arxiv.org/pdf/1902.02186.pdf), by Wojciech Marian Czarnecki, Razvan Pascanu, Simon Osindero, Siddhant M. Jayakumar, Grzegorz Swirszcz, Max Jaderberg. [**DeepMind**]

+ **Learning from Noisy Labels**
1. Learning from Noisy Labels with Distillation
Co-teaching: Robust training of deep neural networks with extremely noisy labels

+ **Model Unification**
1. Unifying Heterogeneous Classifiers with Distillation
1. Unifying and Merging Well-trained Deep Neural Networks for Inference Stage

+ **Privileged Information**
1. [**ICLR'16**] [Unifying Distillation and Privileged Information](https://arxiv.org/pdf/1511.03643.pdf), by David Lopez-Paz, Léon Bottou, Bernhard Schölkopf, Vladimir Vapnik. 
1. Privileged Features Distillation for E-Commerce Recommendations
1. Learning with Pprivileged Information via Adversarial Discriminative Modality Distillation
1. Learning to Rank Using Privileged Information

+ **Recommendation**
1. Adversarial Distillation for Efficient Recommendation with External Knowledge
1. [**Arxiv'19**] [Binarized Collaborative Filtering with Distilling Graph Convolutional Networks](https://arxiv.org/abs/1906.01829), by Haoyu Wang, Defu Lian, Yong Ge.

