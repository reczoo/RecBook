# Candidate Item Matching

+ [Two-Tower Networks](#Two-Tower-Networks)
+ [Path-based Networks](#Path-based-Networks)
+ [Multi-Interest Recommendation](#Multi-Interest-Recommendation)
+ [Sequential Recommendation](#Sequential-Recommendation)
+ [Graph-based Recommendation](#Graph-based-Recommendation)
+ [End-to-End Retrieval](#End-to-End-Retrieval)
+ [Lookalike Model](#Lookalike-Model)
+ [Cross-Domain Recommendation](#Cross-Domain-Recommendation)
+ [Interactive Recommendation](#Interactive-Recommendation)

### Two-Tower Networks

+ [**EBR**][**Facebook**] [Embedding-based Retrieval in Facebook Search](https://arxiv.org/abs/2006.11632), by Jui-Ting Huang, Ashish Sharma, Shuying Sun, Li Xia, David Zhang, Philip Pronin, Janani Padmanabhan, Giuseppe Ottaviano, Linjun Yang. *KDD 2020*.
  > 本文介绍了Facebook的语义检索模型的工程实践经验，包括：1) 随机负采样比曝光未点击样本好 2) 采用triplet loss 3) ANN引擎加入了条件binary matching的过滤 4) retrieval阶段变了，ranking阶段也要跟着优化，考虑加入embedding做特征(query-doc的cosine效果好)和利用人工标注数据finetune embeddings 5) Online hard mining有效(选取相似度最大的negative)；100:1的easy:hard mixing效果最好 6) 双阶段retrieval效果也有提升

### Path-based Networks
+ [**PDN**][**Alibaba**] *SIGIR 2021*.
  > 本文利用U2I和I2I的三部图来进行分数计算，user和target的分数分为U2I(用户与交互过的item之间)和I2I(交互过的item与target item)的乘积之和。分别由TriggerNet和SimNet两个网络进行学习。

### Multi-Interest Recommendation
+ [**PinnerSage**][**Pinterest**] PinnerSage: Multi-Modal User Embedding Framework for Recommendations at Pinterest, *KDD 2020*.
  > 本文介绍了Pinterest的多兴趣召回方案，先采用PinSage学习item embedding，作为输入采用Ward聚类方法对历史用户序列(90天)进行聚类，Ward类似hierarchical clustering，聚类数是不定的。然后获取聚类的的中心作为兴趣表征，同时根据类别的大小及行为时间定义了类别的importance，召回时根据importance选取多个兴趣进行召回。同时，从系统上考虑了batch inference和online update来获取实时用户行为更新聚类中心。与单兴趣(single embedding)召回相比，线上效果显著。

+ [**ComiRec**][**Alibaba**] [Controllable Multi-Interest Framework for Recommendation](https://arxiv.org/abs/2005.09347), by Yukuo Cen, Jianwei Zhang, Xu Zou, Chang Zhou, Hongxia Yang, Jie Tang. *KDD 2020*.

+ [**MIND**][**Alibaba**] [Multi-Interest Network with Dynamic Routing for Recommendation at Tmall](), by Chao Li, Zhiyuan Liu, Mengmeng Wu, Yuchi Xu, Pipei Huang, Huan Zhao, Guoliang Kang, Qiwei Chen, Wei Li, Dik Lun Lee. *CIKM 2019*
> dfd


### Sequential Recommendation

1. [**CIKM'19**] [BERT4Rec: Sequential Recommendation with Bidirectional Encoder Representations from Transformer](https://arxiv.org/abs/1904.06690), by Fei Sun, Jun Liu, Jian Wu, Changhua Pei, Xiao Lin, Wenwu Ou, Peng Jiang. [**Alibaba**]


### Graph-based Recommendation
1. [**Alibaba**] [Beyond Keywords and Relevance: A Personalized Ad Retrieval Framework in E-Commerce Sponsored Search](https://arxiv.org/abs/1712.10110), by Su Yan, Wei Lin, Tianshu Wu, Daorui Xiao, Xu Zheng, Bo Wu, Kaipeng Liu. *WWW 2018*.
    > 本文提出了新的一种ad召回框架，传统的广告召回都靠bid keywords, 但是广告主并不能列举出所有的ad keywords，导致有些高度相关的ad却无法召回的情况。现有的召回框架一般用kewords和relevance的方法。相反，本文提出采用signal nodes--key nodes--ad nodes的异构网络的挖掘，包括query到key node的rewriting边和key node到ad的ad-selecting边。最后对这些边建立index，用于快速的召回查询。与纯文本召回相比，该方法引入了用户历史点击行为，更偏向CTR的优化。[[Read more...](https://kuaibao.qq.com/s/20180410A0QPVP00?refer=spider)]

### End-to-End Retrieval

1. [**Alibaba**] [Joint Optimization of Tree-based Index and Deep Model for Recommender Systems](https://arxiv.org/abs/1902.07565), by Han Zhu, Daqing Chang, Ziru Xu, Pengye Zhang, Xiang Li, Jie He, Han Li, Jian Xu, Kun Gai. *NeurIPS 2019*.

1. [**TDM**][**Alibaba**] Han Zhu, Xiang Li, Pengye Zhang, Guozheng Li, Jie He, Han Li, Kun Gai. [Learning Tree-based Deep Model for Recommender Systems](https://arxiv.org/abs/1801.02294), *KDD 2018*.



### Lookalike Model
1. [**Tencent**][**RALM**] [Real-time Attention Based Look-alike Model for Recommender System](https://arxiv.org/abs/1906.05022), by Yudan Liu, Kaikai Ge, Xu Zhang, Leyu Lin. *KDD 2019*.



### Cross-Domain Recommendation

1. [**KDD'18**] [Learning and Transferring IDs Representation in E-commerce](https://arxiv.org/abs/1712.08289), by Kui Zhao, Yuechuan Li, Zhaoqian Shuai, Cheng Yang. [**Alibaba**]


### Interactive Recommendation
1. [**Google**][**KDD'18**] [Q&R: A Two-Stage Approach Toward Interactive Recommendation](http://alexbeutel.com/papers/q-and-r-kdd2018.pdf), by Konstantina Christakopoulou, Alex Beutel, Rui Li, Sagar Jain, Ed H. Chi. 



