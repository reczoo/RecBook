# NeuralIR
A curated list of awesome resources on neural information retrieval

+ [Surveys and Tutorials](./README.md#Surveys-and-Tutorials)
+ [Sponsored Search](./README.md#Sponsored-Search)
+ [Unbiased Learning to Rank](./README.md#Unbiased-Learning-to-Rank)
+ [Semantic Matching](./README.md#Semantic-Matching)

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