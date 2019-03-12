# Recommender Systems
A curated list of awesome papers on recommender systems

+ [Surveys and Tutorials](#Surveys-and-Tutorials)
+ [Collaborative Filtering](#Collaborative Filtering)
+ [Sequential Recommendation](#Sequential Recommendation)
+ [News Recommendation](#News Recommendation)
+ [Interactive Recommendation](#Interactive Recommendation)
+ [Item Embedding](#Item Embedding)

### Surveys and Tutorials
+ [**CSUR'19**] [Deep Learning based Recommender System: A Survey and New Perspectives](https://arxiv.org/pdf/1707.07435.pdf), by Shuai Zhang, Lina Yao, Aixin Sun, Yi Tay.

### Collaborative Filtering

1. Han Zhu, Xiang Li, Pengye Zhang, Guozheng Li, Jie He, Han Li, Kun Gai. [Learning Tree-based Deep Model for Recommender Systems](https://arxiv.org/abs/1801.02294), **KDD**, 2018

1. Hong-Jian Xue, Xin-Yu Dai, Jianbing Zhang, Shujian Huang, Jiajun Chen. [Deep Matrix factorization Models for Recommender System](http://static.ijcai.org/proceedings-2017/0447.pdf), **IJCAI**, 2017.
   > 本文提出了基于[DSSM框架(Deep Structured Semantic Model)](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/cikm2013_DSSM_fullversion.pdf)匹配query-document的方法来匹配user-item, 就是通过MLP将user/item的one-hot向量映射到一个公共的低维空间，然后利用cosine来预测user-item之间的交互值（explicit ratings/implicit prefernces）。

1. Hao Wang, Naiyan Wang, Dit-Yan Yeung. [Collaborative Deep Learning for Recommender Systems](https://arxiv.org/pdf/1409.2944v2.pdf), **KDD**, 2015.

1. Suvash Sedhain, Aditya Krishna Menon, Scott Sanner, Lexing Xie. [AutoRec: Autoencoders Meet Collaborative Filtering](http://users.cecs.anu.edu.au/~u5098633/papers/www15.pdf), **WWW**, 2015.
   > 本文基于Autoencoder的思想来解决CF问题。CF矩阵的每一行或者每一列都可以看作是一个样本（特征为rating值向量），Autoencoder的应用就是将样本的特征向量通过一个网络映射到latent space, 再通过另一个网络进行还原。改进点就是这里的网络映射考虑rating里的缺失值，BP传播只处理observed value。实验中，基于物品维度的映射(I-AutoRec)比基于用户维度的映射(U-AutoRec)效果更好。


### Sequential Recommendation
1. [**AAAI'14**] Yuyu Zhang, Hanjun Dai, Chang Xu, Jun Feng, Taifeng Wang, Jiang Bian, Bin Wang, Tie-Yan Liu. [Sequential Click Prediction for Sponsored Search with Recurrent Neural Networks](http://www.aaai.org/ocs/index.php/AAAI/AAAI14/paper/download/8529/8581), *AAAI*, 2014.

### News Recommendation

### Interactive Recommendation
1. [**KDD'18**] [Q&R: A Two-Stage Approach Toward Interactive Recommendation](http://alexbeutel.com/papers/q-and-r-kdd2018.pdf), by Konstantina Christakopoulou, Alex Beutel, Rui Li, Sagar Jain, Ed H. Chi. [**Google**]


### Item Embedding
1. [**KDD'18**] [Billion-scale Commodity Embedding for E-commerce Recommendation in Alibaba](https://arxiv.org/abs/1803.02349), Jizhe Wang, Pipei Huang, Huan Zhao, Zhibo Zhang, Binqiang Zhao, Dik Lun Lee. [**Alibaba**]


