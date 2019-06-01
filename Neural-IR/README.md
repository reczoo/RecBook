# Neural IR
A curated list of awesome resources on neural information retrieval

+ [Surveys and Tutorials](#Surveys-and-Tutorials)
+ [Sponsored Search](#Sponsored-Search)
+ [Unbiased Learning to Rank](#Unbiased-Learning-to-Rank)
+ [Semantic Matching ](#Semantic-Matching)
+ [Query Suggestion](#Query-Suggestion)


### Surveys and Tutorials
+ [**SIGIR'18**] [Deep Learning for Matching in Search and Recommendation](https://www.comp.nus.edu.sg/~xiangnan/sigir18-deep.pdf)


### Sponsored Search
+ [**SIGIR'18**] [Turning Clicks into Purchases: Revenue Optimization for Product Search in E-Commerce](http://www.public.asu.edu/~liangwu1/turning-clicks-purchases.pdf), by Liang Wu, Diane Hu, Liangjie Hong, Huan Liu. [**Etsy**]
+ [**SIGIR'16**] [Scalable Semantic Matching of Queries to Ads in Sponsored Search Advertising](https://arxiv.org/pdf/1607.01869.pdf), by Mihajlo Grbovic, Nemanja Djuric, Vladan Radosavljevic, Fabrizio Silvestri, Ricardo Baeza-Yates, Andrew Feng, Erik Ordentlich, Lee Yang, Gavin Owens. [**Yahoo**]
+ [**SIGIR'09**] [Optimizing Search Engine Revenue in Sponsored Search](https://dl.acm.org/citation.cfm?id=1572042), by Yunzhang Zhu, Gang Wang, Junli Yang, Dakan Wang, Jun Yan, Jian Hu, Zheng Chen. [**Microsoft**]

### Unbiased Learning to Rank
+ [**SIGIR'18**] [Unbiased Learning to Rank with Unbiased Propensity Estimation](https://arxiv.org/abs/1804.05938), by Qingyao Ai, Keping Bi, Cheng Luo, Jiafeng Guo, W. Bruce Croft.
+ [**Arxiv'18**] [A Novel Algorithm for Unbiased Learning to Rank](https://arxiv.org/abs/1809.05818), by Ziniu Hu, Yang Wang, Qu Peng, Hang Li. [**ByteDance**]
+ [**IJCAI'18**] [Unbiased Learning-to-Rank with Biased Feedback](https://www.ijcai.org/proceedings/2018/0738.pdf), by Thorsten Joachims, Adith Swaminathan, Tobias Schnabel. [**Microsoft**]
+ [**CIKM'18 Tutorial**] [Unbiased Learning to Rank: Theory and Practice](http://www.cikm2018.units.it/tutorial8.html), by Qingyao Ai, Jiaxin Mao, Yiqun Liu, W. Bruce Croft.
+ [**CIKM'18**] [Differentiable Unbiased Online Learning to Rank](https://staff.fnwi.uva.nl/m.derijke/wp-content/papercite-data/pdf/oosterhuis-differentiable-2018.pdf), by Harrie Oosterhuis, Maarten de Rijke. 

+ [**WSDM'18**] [Position Bias Estimation for Unbiased Learning to Rank in Personal Search](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/46485.pdf), by Xuanhui Wang, Nadav Golbandi, Michael Bendersky, Donald Metzler, Marc Najork. [**Google**]


### Semantic Matching
1. [**WSDM'19 Talk**] [Deep Semantic Matching for Amazon Product Search](https://wsdm2019-dapa.github.io/#section-invitedtalk), by Yiwei Song. [**Amazon**]
    > 该talk讲述了如何利用semantic matching做语义召回，即根据query vector匹配最相邻的product vector，这样原有文本索引队列上加入语义召回队列，进而提升产品搜索。值得参考的点：1. 将doc划分点击、曝光、随机三种，利用分段式的loss函数来确保点击的query-doc pair相似度> 0.9, 随机的query-doc < 0.2, 曝光未点击的 < 0.55。这种pointwise学embedding的方式第一次见，值得借鉴，也需要与word2vec中的方式做比较。2. 分词上采用unigram, 2gram, 3gram, tri-letters多级融合的方式，并在大数据训练集上有较明显效果。3. 另外如何做快速的ANN向量查询也是一个工程化问题

1. [**WWW'18**] [Beyond Keywords and Relevance: A Personalized Ad Retrieval Framework in E-Commerce Sponsored Search](https://arxiv.org/abs/1712.10110), by Su Yan, Wei Lin, Tianshu Wu, Daorui Xiao, Xu Zheng, Bo Wu, Kaipeng Liu. [**Alibaba**]
    > 本文提出了新的一种ad召回框架，传统的广告召回都靠bid keywords, 但是广告主并不能列举出所有的ad keywords，导致有些高度相关的ad却无法召回的情况。现有的召回框架一般用kewords和relevance的方法。相反，本文提出采用signal nodes--key nodes--ad nodes的异构网络的挖掘，包括query到key node的rewriting边和key node到ad的ad-selecting边。最后对这些边建立index，用于快速的召回查询。与纯文本召回相比，该方法引入了用户历史点击行为，更偏向CTR的优化。[[Read more...](https://kuaibao.qq.com/s/20180410A0QPVP00?refer=spider)]
    
1. [**WSDM'15 Talk**] [Semantic Matching in App Search](http://www.wsdm-conference.org/2015/wp-content/uploads/2014/03/WSDM-TalkSemantic-Matching-in-App-Search.pdf), by Juchao Zhuo, Zeqian Huang, Yunfeng Liu, Zhanhui Kang, Xun Cao, Mingzhi Li, Long Jin. [**Tencent**]
    > 该talk是腾讯应用市场讲的关于app搜索的内容。重点包括：1) App搜索的指标Downloads/ QV (Query views)/ UV (User views)/ CTR/ ROP (Rate of Penetration)/ NDCG; 2) 88%的precise search, 12%的fuzzy search (Content/Category/Function related); 3) 提出用Term + Topic + Tag描述semantic, 用topic和tag补充query和app, 总共million apps用LDA找出1000+ topics; 4) query太短无法理解，用clicked apps做补充，在topic space计算query和app的相似度; 5) 与topic matching相比，tag提供more fine-grained semantics, tag依赖human editorial curation和自动提取两部分。挖倔了90K的tags, top100K的app平均有8.53 tags; 6) 使用LambdaMART训练排序，50+ features, 300K+ pairwise training, 3000+ test samples. 得到NDCG=0.9553, CTR在0.58~0.7。[[Read more...](http://www.cctime.com/html/2015-3-4/2015341455368944.htm)]
    
    
### Query Suggestion
1. [**SIGIR'19**] Context Attentive Document Ranking and Query Suggestion

1. [**SIGIR'18**] [Attention-based Hierarchical Neural Query Suggestion](https://arxiv.org/abs/1805.02816), by Wanyu Chen, Fei Cai, Honghui Chen, Maarten de Rijke. 

1. [**ICLR'18**] [Multi-Task Learning for Document Ranking and Query Suggestion](https://openreview.net/pdf?id=SJ1nzBeA-), by Wasi Ahmad, Kai-Wei Chang, Hongning Wang.

1. [**IJCAI'18**] [Improving Entity Recommendation with Search Log and Multi-Task Learning](https://www.ijcai.org/proceedings/2018/0571.pdf), by Jizhou Huang, Wei Zhang, Yaming Sun, Haifeng Wang, Ting Liu. [**Baidu**]

1. [**WWW'18**] [Query Suggestion with Feedback Memory Network](https://dl.acm.org/citation.cfm?doid=3178876.3186068), by Bin Wu, Chenyan Xiong, Maosong Sun, Zhiyuan Liu.

1. [**CIKM'18**] [RIN: Reformulation Inference Network for Context-Aware Query Suggestion](https://jyunyu.csie.org/docs/pubs/cikm2018paper.pdf), by Jyun-Yu Jiang and Wei Wang.





    
