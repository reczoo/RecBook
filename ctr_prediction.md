# Papers

A list of industrial papers on CTR/CVR prediction for online advertising, recommendation, and sponsored search.

+ [Feature Interactions](#Feature-Interactions)
+ [Behaviour Sequence Modeling](#Behavior-Sequence-Modeling)

## Feature Interactions
+ :star: [**DCN_V2**][**Google**] [DCN V2: Improved Deep & Cross Network and Practical Lessons for Web-scale Learning to Rank Systems](https://arxiv.org/abs/2008.13535), by Ruoxi Wang, Rakesh Shivanna, Derek Z. Cheng, Sagar Jain, Dong Lin, Lichan Hong, Ed H. Chi. *Arixv 2020*.

+ [**InterHAt**][**NEC Labs**] [Interpretable Click-Through Rate Prediction through Hierarchical Attention](https://dl.acm.org/doi/10.1145/3336191.3371785), by Zeyu Li, Wei Cheng, Yang Che, Haifeng Che, Wei Wang. *WSDM 2020*.
  > 本文借鉴了hierarchical attention network的思想，在field间和不同order间进行两层attentional aggregation，进行CTR预测。首先本文采用multi-head transformer计算1st-order feature X1，然后利用attentional aggregation聚合得到向量u1，然后利用u1与X1的hadmard product产生更高阶的特征，依次循环得到k阶特征。最后将所有u1, u2...uk进行attentional aggregation得到最终的向量，过MLP进行分类。

+ [**TFNet**][**Tencent**] [TFNet: Multi-Semantic Feature Interaction for CTR Prediction](https://arxiv.org/abs/2006.15939), by Shu Wu, Feng Yu, Xueli Yu, Qiang Liu, Liang Wang, Tieniu Tan, Jie Shao, Fan Huang. *SIGIR 2020*.
  > 本文是腾讯在App推荐场景的工作。针对inner produc交互层加入了一个operation tensor，即vi*vj变为vi*T*vj，其中T的size为dxmxd，代表m个semantic space。此外，T还引入gate机制将vi_vj pair的T动态调整，即vi*Tij*vj.

+ [**FAT-DeepFFM**][**Sina Weibo**] [FAT-DeepFFM: Field Attentive Deep Field-aware Factorization Machine](https://arxiv.org/abs/1905.06336), by Junlin Zhang, Tongwen Huang, Zhiqi Zhang. *ICDM 2019*.

+ [**FiBiNET**][**Sina Weibo**] [FiBiNET: Combining Feature Importance and Bilinear feature Interaction for Click-Through Rate Prediction](https://arxiv.org/abs/1905.09433), by Tongwen Huang, Zhiqi Zhang, Junlin Zhang. *RecSys 2019*. 

+ [**AutoInt**] [AutoInt: Automatic Feature Interaction Learning via Self-Attentive Neural Networks](https://arxiv.org/abs/1810.11921), by Weiping Song, Chence Shi, Zhiping Xiao, Zhijian Duan, Yewen Xu, Ming Zhang, Jian Tang. *CIKM 2019*.

+ [**FGCNN**][**Huawei**] [Feature Generation by Convolutional Neural Network for Click-Through Rate Prediction](https://arxiv.org/abs/1904.04447), by Bin Liu, Ruiming Tang, Yingzhi Chen, Jinkai Yu, Huifeng Guo, Yuzhou Zhang. *WWW 2019*.

+ [**FwFM**][**Yahoo & TouchPal & LinkedIn & Ablibaba**] [Field-weighted Factorization Machines for Click-Through Rate Prediction in Display Advertising](https://arxiv.org/pdf/1806.03514.pdf), by Junwei Pan, Jian Xu, Alfonso Lobos Ruiz, Wenliang Zhao, Shengjun Pan, Yu Sun, Quan Lu. *WWW, 2018*. 

+ [**RFM**][**WalmartLabs**] [Robust Factorization Machines for User Response Prediction](http://wnzhang.net/share/rtb-papers/rfm-www.pdf), by Surabhi Punjabi, Priyanka Bhatt. *WWW, 2018*.

+ :star: [**xDeepFM**][**Microsoft**] [xDeepFM: Combining Explicit and Implicit Feature Interactions for Recommender Systems](https://arxiv.org/pdf/1803.05170.pdf), by Jianxun Lian, Xiaohuan Zhou, Fuzheng Zhang, Zhongxia Chen, Xing Xie, Guangzhong Sun. *KDD, 2018*.

+ :star: [**DeepFM**][**Huawei**] [DeepFM: A Factorization-Machine based Neural Network for CTR Prediction](https://arxiv.org/abs/1703.04247), by Huifeng Guo, Ruiming Tang, Yunming Ye, Zhenguo Li, Xiuqiang He. *IJCAI, 2017*.

+ :star: [**DCN**][**Google**] [Deep & Cross Network for Ad Click Predictions](https://arxiv.org/abs/1708.05123), by Ruoxi Wang, Bin Fu, Gang Fu, Mingliang Wang. *ADKDD, 2017*. 

+ [**FFM**][**Criteo & Facebook & Google**] [Field-aware Factorization Machines in a Real-world Online Advertising System](https://arxiv.org/pdf/1701.04099.pdf), by Yuchin Juan, Damien Lefortier, Olivier Chapelle. *WWW, 2017*. 

+ :star: [**YoutubeNet**][**Google**] [Deep Neural Networks for YouTube Recommendations](http://art.yale.edu/file_columns/0001/1132/covington.pdf), by Paul Covington, Jay Adams, Emre Sargin. *RecSys, 2016*.

+ :star: [**FFM**][**Criteo**] [Field-aware Factorization Machines for CTR Prediction](https://dl.acm.org/citation.cfm?id=2959134), by Yuchin Juan, Yong Zhuang, Wei-Sheng Chin, Chih-Jen Lin. *RecSys, 2016*.

+ :star: [**WideDeep**][**Google**] [Wide & Deep Learning for Recommender Systems](https://arxiv.org/pdf/1606.07792.pdf), by Heng-Tze Cheng, Levent Koc, Jeremiah Harmsen, Tal Shaked, Tushar Chandra, Hrishi Aradhye, Glen Anderson, Greg Corrado, Wei Chai, Mustafa Ispir, Rohan Anil, Zakaria Haque, Lichan Hong, Vihan Jain, Xiaobing Liu, Hemal Shah. *DLRS, 2016*.

+ [**PNN**] [Product-based Neural Networks for User Response Prediction](https://arxiv.org/pdf/1611.00144.pdf), by Yanru Qu, Han Cai, Kan Ren, Weinan Zhang, Yong Yu, Ying Wen, Jun Wang. *ICDM, 2016*.
 
+ [**DeepCTR**][**Alibaba**] [Deep CTR Prediction in Display Advertising](https://dl.acm.org/citation.cfm?id=2964325), by Junxuan Chen, Baigui Sun, Hao Li, Hongtao Lu, Xian-Sheng Hua. *MM, 2016*.
   
+ [**GBDT+LR**][**Facebook**] [Practical Lessons from Predicting Clicks on Ads at Facebook](https://dl.acm.org/citation.cfm?id=2648589), by Xinran He, Junfeng Pan, Ou Jin, Tianbing Xu, Bo Liu, Tao Xu, Yanxin Shi, Antoine Atallah, Ralf Herbrich, Stuart Bowers, Joaquin Quiñonero Candela. *ADKDD, 2014*. 

+ :star: [**FTRL**][**Google**] [Ad Click Prediction: a View from the Trenches](https://www.researchgate.net/publication/262412214_Ad_click_prediction_a_view_from_the_trenches), by H. Brendan McMahan, Gary Holt, David Sculley, Michael Young, Dietmar Ebner, Julian Grady, Lan Nie, Todd Phillips, Eugene Davydov, Daniel Golovin, Sharat Chikkerur, Dan Liu, Martin Wattenberg, Arnar Mar Hrafnkelsson, Tom Boulos, Jeremy Kubica. *KDD, 2013*.

+ :star: [**FM**] [Factorization Machines](https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf), by Steffen Rendle. *ICDM, 2010*.

+ [**LR**][**Microsoft**] [Predicting Clicks: Estimating the Click-Through Rate for New Ads](https://dl.acm.org/citation.cfm?id=1242643), by Matthew Richardson, Ewa Dominowska, Robert Ragno. *WWW*, 2007.
   > 本文是比较早做广告CTR预估的文章，采用最经典的LR模型来预测新广告的CTR。本文的CTR是统计意义上的点击率，并与query无关。模型利用了bid term CTR, related term CTR, ad quality, order相关的特征做线性回归，以cross-entropy loss作为regression模型预测CTR的概率。 在数值特征上，采用了x, log(1 + x), x^2的组合，以及对query frequency划分bin方式。实验表明，广告在100次以上view的情况下CTR的预估能逼近真实值。本文支出query相关的CTR预估是重要的方向。
  

## Behaviour Sequence Modeling

+ [**DMR**][**Alibaba**] Deep Match to Rank Model for Personalized Click-Through Rate Prediction](https://ojs.aaai.org//index.php/AAAI/article/view/5346), by Ze Lyu, Yu Dong, Chengfu Huo, Weijun Ren. *AAAI 2020*.
  > 本位主要考虑了behavior sequence的用法，传统有两种：1. 纯self-attention聚合 2. 利用DIN根据target item聚合。本文正好结合了这两种分别叫做user-to-item network和item-to-item network。另外在学user-to-item时，最后使用aggregated user representation和target embeddding做inner product作为relevance，相当于一个matching网络，所以加入了一个matching的auxiliary loss辅助训练。数据使用了Taobao的点击数据，这组数据可以复现。

+ :star: [**SIM**][**Alibaba**] [Search-based User Interest Modeling with Lifelong Sequential Behavior Data for Click-Through Rate Prediction](https://arxiv.org/abs/2006.05639), by Pi Qi, Xiaoqiang Zhu, Guorui Zhou, Yujing Zhang, Zhe Wang, Lejian Ren, Ying Fan, Kun Gai. *CIKM 2020*.
  > 本文是阿里妈妈在用户兴趣建模的新作，之前的DIN和DIEN都只能建模用户短期兴趣(比如200个点击序列)，本文考虑使用更长的用户序列建模长期兴趣(比如180天)，提出了两种item搜索策略，包含soft-search和hard-search，soft-search利用dot values取topk，需要LSH技术支持；hard-search直接取与目标ad相同category的items。soft-search与hard-search相比，准确度更高但系统实现更负杂。最后线上使用的是hard-search，得到的sub-sequence再输入DIN/DIEN进行用户兴趣学习。此外，在DIN模型输入时，同时考虑了长期sequence（180天）和短期sequence(最近两周)，离线AUC提升1个百分点，CTR提升7.1%。

+ [**DHAN**][**Alibaba**] [Deep Interest with Hierarchical Attention Network for Click-Through Rate Prediction](https://arxiv.org/abs/2005.12981), by Weinan Xu, Hengxu He, Minshi Tan, Yunming Li, Jun Lang, Dongbai Guo. *SIGIR 2020*.
  > 本文将user behaviors进行分层表示，即在item层先用DIN算出item-level的interest vector, 然后将items根据category聚合为N个cluster，计算出cluster表征sequence，再用DIN方法计算category层面的interest vector，最后将各个level的向量concate作为最后的输出。

+ [**HPMN**][**Alibaba**] [Lifelong Sequential Modeling with Personalized Memorization for User Response Prediction](https://arxiv.org/abs/1905.00758), by Kan Ren, Jiarui Qin, Yuchen Fang, Weinan Zhang, Lei Zheng, Weijie Bian, Guorui Zhou, Jian Xu, Yong Yu, Xiaoqiang Zhu, Kun Gai. *SIGIR 2019*.

+ [**MIMN**][**Alibaba**] [Practice on Long Sequential User Behavior Modeling for Click-Through Rate Prediction](https://arxiv.org/abs/1905.09248), by Qi Pi, Weijie Bian, Guorui Zhou, Xiaoqiang Zhu, Kun Gai. *KDD 2019*.

+ [**DSTN**][**Alibaba**] [Deep Spatio-Temporal Neural Networks for Click-Through Rate Prediction](https://arxiv.org/abs/1906.03776), by Wentao Ouyang, Xiuwu Zhang, Li Li, Heng Zou, Xin Xing, Zhaojie Liu, Yanlong Du. *KDD 2019*.
  > 本文在DIN的基础上，除了使用clicked item sequence之外，还引入了unclicked ad sequence和contexual ad sequence, 其中contextual ad定义为在同一个session中target ad之前展示的ad, 在实现时取的时预测结果Top1的ad。本文提出了三种聚合方法，即sum-pooling, self-attention, 和DIN-like atttion (效果在同一level、略微递增), 然后进行Concate + MLP。预测时分两个步骤，先预测一遍取Top1的contexual ad，再输入模型预测第二遍取Top2之后的ad。

+ [**BST**][**Alibaba**] [Behavior Sequence Transformer for E-commerce Recommendation in Alibaba](https://arxiv.org/abs/1905.06874), by Qiwei Chen, Huan Zhao, Wei Li, Pipei Huang, Wenwu Ou. *Arxiv 2019*.

+ :star: [**DSIN**][**Alibaba**] [Deep Session Interest Network for Click-Through Rate Prediction](https://arxiv.org/abs/1905.06482), by Yufei Feng, Fuyu Lv, Weichen Shen, Menghan Wang, Fei Sun, Yu Zhu, Keping Yang. *IJCAI 2019*.
  > 本文建模user click sequence (200 per sample)，将sequence按30min划分session，每个session内部的item-subset用单层transformer建模，然后averaging pooling构建跨session sequence，用Bi-LSTM建模session interest交互，最后利用target item进行类DIN的attention aggregation，和其他特征拼接后过MLP做CTR预估。主要创新点是将sequence划分session，然后构建了双层sequence建模。
  
+ [**DIEN**][**Alibaba**] [Deep Interest Evolution Network for Click-Through Rate Prediction](https://arxiv.org/abs/1809.03672), by Guorui Zhou, Na Mou, Ying Fan, Qi Pi, Weijie Bian, Chang Zhou, Xiaoqiang Zhu, Kun Gai. *AAAI 2019*.

+ :star: [**DIN**][**Alibaba**] [Deep Interest Network for Click-Through Rate Prediction](https://arxiv.org/pdf/1706.06978.pdf), by Guorui Zhou, Chengru Song, Xiaoqiang Zhu, Ying Fan, Han Zhu, Xiao Ma, Yanghui Yan, Junqi Jin, Han Li, Kun Gai. *KDD 2018*.

## Multi-Scenarios & Cross-Domain
+ [**MiNet**][**Alibaba**] [MiNet: Mixed Interest Network for Cross-Domain Click-Through Rate Prediction](https://arxiv.org/abs/2008.02974), by Wentao Ouyang, Xiuwu Zhang, Lei Zhao, Jinmei Luo, Yu Zhang, Heng Zou, Zhaojie Liu, Yanlong Du. *CIKM 2020*.
  > 本文介绍阿里新闻广告CTR广告预估任务中利用用户在新闻内容的行为进行cross-domain学习，即主任务为广告CTR预估，辅助任务为新闻数据上的行为建模(双塔模型)，最后将学到的长期用户兴趣向量和短期新闻点击历史作为特征输入到主任务。效果在前一版模型DSTN上提升CTR 4%左右。

## Multi-Tasks & Multi-Objectives

+ [**DeepMCP**][**Alibaba**] [Representation Learning-Assisted Click-Through Rate Prediction](https://arxiv.org/abs/1906.04365), by Wentao Ouyang, Xiuwu Zhang, Shukui Ren, Chao Qi, Zhaojie Liu, Yanlong Du. *IJCAI *.
  > 本文在CTR预测模型(P)之外，增加了两个子网络：Matching Net (M)和Correlation Net (C)。其中Matching Net建模user+query与ad的匹配关系（与DSSM类似），并且相似度由dot+sigmoid函数计算，训练数据与P模块相同。Correlation模块建模同一用户的点击ad序列相关性，即用skip-gram loss来建模。实验表明，P+M比P+C的提升更显著。

+ [**DSM**][**Yahoo & Criteo**] [Deeply Supervised Semantic Model for Click-Through Rate Prediction in Sponsored Search](https://arxiv.org/abs/1803.10739), by Jelena Gligorijevic, Djordje Gligorijevic, Ivan Stojkovic, Xiao Bai, Amit Goyal, Zoran Obradovic. *Arxiv 2019*.

## Graph-enhanced Modeling
+ [**ATBRG**][**Alibaba**] [ATBRG: Adaptive Target-Behavior Relational Graph Network for Effective Recommendation](https://arxiv.org/abs/2005.12002), by Yufei Feng, Binbin Hu, Fuyu Lv, Qingwen Liu, Zhiqiang Zhang, Wenwu Ou. *SIGIR 2020*.
  > 本文可以看作在DIN基础上的改进。DIN只考虑用户历史交互的item sequence的聚合，本文提出以KG的方式构建历史item sequence和targe item之间的关系图(target-behavior relational graph), 然后利用GNN聚合每个item周围节点信息，并将多层GNN的输出concate一起。之后，采用DIN的方式聚合item sequence及MLP输出。

+ [**GIN**][**Alibaba**] [Graph Intention Network for Click-through Rate Prediction in Sponsored Search](https://dl.acm.org/citation.cfm?id=3331283), by Feng Li, Zhenrui Chen, Pengjie Wang, Yi Ren, Di Zhang and Xiaoyu Zhu. *SIGIR 2019*.



