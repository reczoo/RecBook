# TopK Item Embedding Retrieval

+ [Two-Tower Networks](#Two-Tower-Networks)
+ [Sequential Recommendation](#Sequential-Recommendation)
+ [Graph-based Recommendation](#Graph-based-Recommendation)
+ End-to-End Retrieval
+ Lookalike Model

### Two-Tower Networks

+ [**EBR**][**Facebook**] [Embedding-based Retrieval in Facebook Search](https://arxiv.org/abs/2006.11632), by Jui-Ting Huang, Ashish Sharma, Shuying Sun, Li Xia, David Zhang, Philip Pronin, Janani Padmanabhan, Giuseppe Ottaviano, Linjun Yang. *KDD 2020*.
  > 本文介绍了Facebook的语义检索模型的工程实践经验，包括：1) 随机负采样比曝光未点击样本好 2) 采用triplet loss 3) ANN引擎加入了条件binary matching的过滤 4) retrieval阶段变了，ranking阶段也要跟着优化，考虑加入embedding做特征(query-doc的cosine效果好)和利用人工标注数据finetune embeddings 5) Online hard mining有效(选取相似度最大的negative)；100:1的easy:hard mixing效果最好 6) 双阶段retrieval效果也有提升

1. [**WSDM'19** Talk] [Deep Semantic Matching for Amazon Product Search](https://wsdm2019-dapa.github.io/slides/05-YiweiSong.pdf), by Yiwei Song. [**Amazon**]
    > 该talk讲述了如何利用semantic matching做语义召回，即根据query vector匹配最相邻的product vector，这样原有文本索引队列上加入语义召回队列，进而提升产品搜索。值得参考的点：1. 将doc划分点击、曝光、随机三种，利用分段式的loss函数来确保点击的query-doc pair相似度> 0.9, 随机的query-doc < 0.2, 曝光未点击的 < 0.55。这种pointwise学embedding的方式第一次见，值得借鉴，也需要与word2vec中的方式做比较。2. 分词上采用unigram, 2gram, 3gram, tri-letters多级融合的方式，并在大数据训练集上有较明显效果。3. 另外如何做快速的ANN向量查询也是一个工程化问题

1. [**WSDM'15** Talk] [Semantic Matching in App Search](http://www.wsdm-conference.org/2015/wp-content/uploads/2014/03/WSDM-TalkSemantic-Matching-in-App-Search.pdf), by Juchao Zhuo, Zeqian Huang, Yunfeng Liu, Zhanhui Kang, Xun Cao, Mingzhi Li, Long Jin. [**Tencent**]
    > 该talk是腾讯应用市场讲的关于app搜索的内容。重点包括：1) App搜索的指标Downloads/ QV (Query views)/ UV (User views)/ CTR/ ROP (Rate of Penetration)/ NDCG; 2) 88%的precise search, 12%的fuzzy search (Content/Category/Function related); 3) 提出用Term + Topic + Tag描述semantic, 用topic和tag补充query和app, 总共million apps用LDA找出1000+ topics; 4) query太短无法理解，用clicked apps做补充，在topic space计算query和app的相似度; 5) 与topic matching相比，tag提供more fine-grained semantics, tag依赖human editorial curation和自动提取两部分。挖倔了90K的tags, top100K的app平均有8.53 tags; 6) 使用LambdaMART训练排序，50+ features, 300K+ pairwise training, 3000+ test samples. 得到NDCG=0.9553, CTR在0.58~0.7。[[Read more...](http://www.cctime.com/html/2015-3-4/2015341455368944.htm)]


### Sequential Recommendation

1. [**CIKM'19**] [BERT4Rec: Sequential Recommendation with Bidirectional Encoder Representations from Transformer](https://arxiv.org/abs/1904.06690), by Fei Sun, Jun Liu, Jian Wu, Changhua Pei, Xiao Lin, Wenwu Ou, Peng Jiang. [**Alibaba**]


### Graph-based Recommendation
1. [**WWW'18**] [Beyond Keywords and Relevance: A Personalized Ad Retrieval Framework in E-Commerce Sponsored Search](https://arxiv.org/abs/1712.10110), by Su Yan, Wei Lin, Tianshu Wu, Daorui Xiao, Xu Zheng, Bo Wu, Kaipeng Liu. [**Alibaba**]
    > 本文提出了新的一种ad召回框架，传统的广告召回都靠bid keywords, 但是广告主并不能列举出所有的ad keywords，导致有些高度相关的ad却无法召回的情况。现有的召回框架一般用kewords和relevance的方法。相反，本文提出采用signal nodes--key nodes--ad nodes的异构网络的挖掘，包括query到key node的rewriting边和key node到ad的ad-selecting边。最后对这些边建立index，用于快速的召回查询。与纯文本召回相比，该方法引入了用户历史点击行为，更偏向CTR的优化。[[Read more...](https://kuaibao.qq.com/s/20180410A0QPVP00?refer=spider)]

### End-to-End Retrieval

1. Han Zhu, Xiang Li, Pengye Zhang, Guozheng Li, Jie He, Han Li, Kun Gai. [Learning Tree-based Deep Model for Recommender Systems](https://arxiv.org/abs/1801.02294), **KDD**, 2018

3. [**NeurIPS'19**] [Joint Optimization of Tree-based Index and Deep Model for Recommender Systems](https://arxiv.org/abs/1902.07565), by Han Zhu, Daqing Chang, Ziru Xu, Pengye Zhang, Xiang Li, Jie He, Han Li, Jian Xu, Kun Gai. [**Alibaba**]


### Lookalike Model
1. [**KDD'19**] [Real-time Attention Based Look-alike Model for Recommender System](https://arxiv.org/abs/1906.05022), by Yudan Liu, Kaikai Ge, Xu Zhang, Leyu Lin. [**Tencent**]





### News Recommendation

1. [**Arxiv'19] [Learning Cross-Domain Representation with Multi-Graph Neural Network](https://arxiv.org/abs/1905.10095), by Yi Ouyang, Bin Guo, Xing Tang, Xiuqiang He, Jian Xiong, Zhiwen Yu. [**Tencent**]

1. [**IJCAI'19**] [DARec: Deep Domain Adaptation for Cross-Domain Recommendation via Transferring Rating Patterns](https://arxiv.org/abs/1905.10760), by Feng Yuan, Lina Yao, Boualem Benatallah. 

1. [**KDD'19**] [NPA: Neural News Recommendation with Personalized Attention](https://arxiv.org/pdf/1907.05559.pdf), by Chuhan Wu, Fangzhao Wu, Mingxiao An, Jianqiang Huang, Yongfeng Huang, Xing Xie. [**Google**]

1. [**ACL'19**] [Neural News Recommendation with Long- and Short-term User Representations](https://www.aclweb.org/anthology/P19-1033), by Mingxiao An, Fangzhao Wu, Chuhan Wu, Kun Zhang, Zheng Liu, Xing Xie. [**Microsoft**]

### Cross-Domain Recommendation
1. [**WWW'19**] [Cross-domain Recommendation Without Sharing User-relevant Data](https://dl.acm.org/citation.cfm?id=3313538), by Chen Gao, Xiangning Chen, Fuli Feng, Kai Zhao, Xiangnan He, Yong Li, Depeng Jin.

1. [**KDD'18**] [Learning and Transferring IDs Representation in E-commerce](https://arxiv.org/abs/1712.08289), by Kui Zhao, Yuechuan Li, Zhaoqian Shuai, Cheng Yang. [**Alibaba**]

1. [**IJCAI'17**] [Cross-Domain Recommendation: An Embedding and Mapping Approach](https://www.ijcai.org/proceedings/2017/0343.pdf), by Tong Man, Huawei Shen, Xiaolong Jin, Xueqi Cheng. 

### Interactive Recommendation
1. [**KDD'18**] [Q&R: A Two-Stage Approach Toward Interactive Recommendation](http://alexbeutel.com/papers/q-and-r-kdd2018.pdf), by Konstantina Christakopoulou, Alex Beutel, Rui Li, Sagar Jain, Ed H. Chi. [**Google**]



### Explainable Recommendation

1. [**SIGIR'19**] [A Capsule Network for Recommendation and Explaining What You Like and Dislike](), by Chenliang Li, Cong Quan, Li Peng, Yunwei Qi, Yuming Deng, Libing Wu. [**Alibaba**]


