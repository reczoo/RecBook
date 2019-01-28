# Papers

A list of papers on CTR/CVR prediction in online advertising, recommendation, and sponsored search.
+ [Categorical Representation Learning](#Categorical-Representation-Learning)
   + [2019](#2019) | [2018](#2018) | [2017](#2017) | [2016](#2016) | [2015](#2015) | [2014](#2014) | [2013](#2013) | [2010](#2010) | [2007](#2007) 
+ [User Behavior Modeling](#User-Behavior-Modeling)
+ [Sponsored Search](#Sponsored-Search)
+ [Sequential Recommendation](#Sequential-Recommendation)
+ [Multimodal Representation Learning](#Multimodal-Representation-Learning)
+ [Reinforcement/Online Learning](#Reinforcement/Online-Learning)
+ [Others](#Others)

## Categorical Representation Learning
### 2019

1. [**AAAI'19**] Accurate and Interpretable Factorization Machines

### 2018

1. [**CSUR'18**] Shuai Zhang, Lina Yao, Aixin Sun, Yi Tay. [Deep Learning based Recommender System: A Survey and New Perspectives](https://arxiv.org/pdf/1707.07435.pdf), *CSUR*, 2018.

1. [**WWW'18**] Junwei Pan, Jian Xu, Alfonso Lobos Ruiz, Wenliang Zhao, Shengjun Pan, Yu Sun, Quan Lu. [Field-weighted Factorization Machines for Click-Through Rate Prediction in Display Advertising](https://arxiv.org/pdf/1806.03514.pdf), *WWW*, 2018. [**Oath**, **TouchPal**, **LinkedIn**, **Ablibaba**]

1. [**WWW'18**] Surabhi Punjabi, Priyanka Bhatt. [Robust Factorization Machines for User Response Prediction](http://wnzhang.net/share/rtb-papers/rfm-www.pdf), *WWW*, 2018. [**WalmartLabs**]

1. [**KDD'18**] Jianxun Lian, Xiaohuan Zhou, Fuzheng Zhang, Zhongxia Chen, Xing Xie, Guangzhong Sun. [xDeepFM: Combining Explicit and Implicit Feature Interactions for Recommender Systems](https://arxiv.org/pdf/1803.05170.pdf), *KDD*, 2018. [**Microsoft**]

1. [**KDD'18**] Guorui Zhou, Chengru Song, Xiaoqiang Zhu, Ying Fan, Han Zhu, Xiao Ma, Yanghui Yan, Junqi Jin, Han Li, Kun Gai. [Deep Interest Network for Click-Through Rate Prediction](https://arxiv.org/pdf/1706.06978.pdf), *KDD*, 2018. [**Alibaba**]

1. [**IJCAI'18**] Patrick P. K. Chan, Xian Hu, Lili Zhao, Daniel S. Yeung, Dapeng Liu, Lei Xiao. [Convolutional Neural Networks based Click-Through Rate Prediction with Multiple Feature Sequences](https://www.ijcai.org/proceedings/2018/0277.pdf), *IJCAI*, 2018.

1. [**RecSys'18**] Weiwen Liu, Ruiming Tang, Jiajin Li, Jinkai Yu, Huifeng Guo, Xiuqiang He, Shengyu Zhang. [Field-aware Probabilistic Embedding Neural Network for CTR Prediction](https://dl.acm.org/citation.cfm?id=3240396), *RecSys*, 2018. [**Huawei**]

1. [**TOIS'18**] Yanru Qu, Bohui Fang, Weinan Zhang, Ruiming Tang, Minzhe Niu, Huifeng Guo, Yong Yu, Xiuqiang He. [Product-based Neural Networks for User Response Prediction over Multi-field Categorical Data](https://arxiv.org/abs/1807.00311), *TOIS*, 2018. [**Huawei**, **Tencent**]

1. [**CoRR**] Mehul Parsana, Krishna Poola, Yajun Wang, Zhiguang Wang. [Improving Native Ads CTR Prediction by Large Scale Event Embedding and Recurrent Networks](https://arxiv.org/abs/1804.09133), *arXiv:1804.09133*, 2018. [**Microsoft**]

1. [**CoRR**] [AutoInt: Automatic Feature Interaction Learning via Self-Attentive Neural Networks](), 

### 2017

1. [**IJCAI'17**] Huifeng Guo, Ruiming Tang, Yunming Ye, Zhenguo Li, Xiuqiang He. [DeepFM: A Factorization-Machine based Neural Network for CTR Prediction](https://arxiv.org/abs/1703.04247), *IJCAI*, 2017. [**Huawei**]

1. [**IJCAI'17**] Jun Xiao, Hao Ye, Xiangnan He, Hanwang Zhang, Fei Wu, Tat-Seng Chua. [Attentional Factorization Machines: Learning the Weight of Feature Interactions via Attention Networks](http://www.ijcai.org/proceedings/2017/0435.pdf), *IJCAI*, 2017.
   
1. [**SIGIR'17**] Xiangnan He, Tat-Seng Chua. [Neural Factorization Machines for Sparse Predictive Analytics](https://dl.acm.org/citation.cfm?id=3080777), *SIGIR*, 2017.

1. [**ADKDD'17**] Ruoxi Wang, Bin Fu, Gang Fu, Mingliang Wang. [Deep & Cross Network for Ad Click Predictions](https://arxiv.org/abs/1708.05123), *ADKDD*, 2017. [**Google**]

1. [**WWW'17**] Yuchin Juan, Damien Lefortier, Olivier Chapelle. [Field-aware Factorization Machines in a Real-world Online Advertising System](https://arxiv.org/pdf/1701.04099.pdf), *WWW*, 2017. [**Criteo**, **Facebook**, **Google**]

1. [**WWW'17**] Huifeng Guo, 	Ruiming Tang, Yunming Ye, 	Xiuqiang He. [Holistic Neural Network for CTR Prediction](https://dl.acm.org/citation.cfm?doid=3041021.3054208), *WWW*, 2017. [**Huawei**]
   > 本文提出了一个Holistic Neural Network框架，就是在网络架构上把所有输入层和中间层representation vector也传递到output layer做concat, 最后通过softmax做分类，这样能在最终分类器层同时利用low-order和high-order表征，有点类似Wide&Deep的思路。


### 2016

1. [**RecSys'16**] Paul Covington, Jay Adams, Emre Sargin. [Deep Neural Networks for YouTube Recommendations](http://art.yale.edu/file_columns/0001/1132/covington.pdf), *RecSys*, 2016. [**Google**]

1. [**RecSys'16**] Yuchin Juan, Yong Zhuang, Wei-Sheng Chin, Chih-Jen Lin. [Field-aware Factorization Machines for CTR Prediction](https://dl.acm.org/citation.cfm?id=2959134), *RecSys*, 2016. [**Criteo**]

1. [**DLRS'16**] Heng-Tze Cheng, Levent Koc, Jeremiah Harmsen, Tal Shaked, Tushar Chandra, Hrishi Aradhye, Glen Anderson, Greg Corrado, Wei Chai, Mustafa Ispir, Rohan Anil, Zakaria Haque, Lichan Hong, Vihan Jain, Xiaobing Liu, Hemal Shah. [Wide & Deep Learning for Recommender Systems](https://arxiv.org/pdf/1606.07792.pdf), *DLRS*, 2016. [**Google**]

1. [**ICDM'16**] Yanru Qu, Han Cai, Kan Ren, Weinan Zhang, Yong Yu, Ying Wen, Jun Wang. [Product-based Neural Networks for User Response Prediction](https://arxiv.org/pdf/1611.00144.pdf), *ICDM*, 2016.
   
1. [**ECIR'2016**] Weinan Zhang, Tianming Du, Jun Wang. [Deep Learning over Multi-field Categorical Data: A Case Study on User Response Prediction](https://arxiv.org/abs/1601.02376), *ECIR*, 2016. [**RayCloud**]

1. [**MM'16**] Junxuan Chen, Baigui Sun, Hao Li, Hongtao Lu, Xian-Sheng Hua. [Deep CTR Prediction in Display Advertising](https://dl.acm.org/citation.cfm?id=2964325), *MM*, 2016. [**Alibaba**]  
   

### 2015

+ [**CIKM'15**] Qiang Liu, Feng Yu, Shu Wu, Liang Wang. [A Convolutional Click Prediction Model](http://www.escience.cn/system/download/73676), *CIKM*, 2015.

+ [**TIST'15**] Simple and Scalable Response Prediction for Display Advertising, *TIST*, 2015.

### 2014
   
1. [**ADKDD'14**] Xinran He, Junfeng Pan, Ou Jin, Tianbing Xu, Bo Liu, Tao Xu, Yanxin Shi, Antoine Atallah, Ralf Herbrich, Stuart Bowers, Joaquin Quiñonero Candela. [Practical Lessons from Predicting Clicks on Ads at Facebook](https://dl.acm.org/citation.cfm?id=2648589), *ADKDD*, 2014. [**Facebook**]


### 2013
+ [**KDD'13**] H. Brendan McMahan, Gary Holt, David Sculley, Michael Young, Dietmar Ebner, Julian Grady, Lan Nie, Todd Phillips, Eugene Davydov, Daniel Golovin, Sharat Chikkerur, Dan Liu, Martin Wattenberg, Arnar Mar Hrafnkelsson, Tom Boulos, Jeremy Kubica. [Ad Click Prediction: a View from the Trenches](https://www.researchgate.net/publication/262412214_Ad_click_prediction_a_view_from_the_trenches), *KDD*, 2013. [**Google**]


### 2010
+ [**ICDM'10**] Steffen Rendle. [Factorization Machines](https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf), *ICDM*, 2010.


### 2007   
+ [**WWW'07**] Matthew Richardson, Ewa Dominowska, Robert Ragno. [Predicting Clicks: Estimating the Click-Through Rate for New Ads](https://dl.acm.org/citation.cfm?id=1242643), *WWW*, 2007. [**Microsoft**]
   > 本文是比较早做广告CTR预估的文章，采用最经典的LR模型来预测新广告的CTR。本文的CTR是统计意义上的点击率，并与query无关。模型利用了bid term CTR, related term CTR, ad quality, order相关的特征做线性回归，以cross-entropy loss作为regression模型预测CTR的概率。 在数值特征上，采用了x, log(1 + x), x^2的组合，以及对query frequency划分bin方式。实验表明，广告在100次以上view的情况下CTR的预估能逼近真实值。本文支出query相关的CTR预估是重要的方向。

## User Behavior Modeling

## Sponsored Search
1. [**CoRR**] Jelena Gligorijevic, Djordje Gligorijevic, Ivan Stojkovic, Xiao Bai, Amit Goyal, Zoran Obradovic. [Deeply Supervised Semantic Model for Click-Through Rate Prediction in Sponsored Search](https://arxiv.org/abs/1803.10739), *arXiv:1803.10739*, 2018. [**Yahoo**, **Criteo**]

## Sequential Recommendation
1. [**AAAI'14**] Yuyu Zhang, Hanjun Dai, Chang Xu, Jun Feng, Taifeng Wang, Jiang Bian, Bin Wang, Tie-Yan Liu. [Sequential Click Prediction for Sponsored Search with Recurrent Neural Networks](http://www.aaai.org/ocs/index.php/AAAI/AAAI14/paper/download/8529/8581), *AAAI*, 2014.

## Multitask Learning
1. [**SIGIR'18**] Xiao Ma, Liqin Zhao, Guan Huang, Zhi Wang, Zelin Hu, Xiaoqiang Zhu, Kun Gai. [Entire Space Multi-Task Model: An Effective Approach for Estimating Post-Click Conversion Rate](https://arxiv.org/pdf/1804.07931), *SIGIR*, 2018. [**Alibaba**]
   > 本文提出了基于multi-task learning的框架ESMM首次将CTR和CVR两个task进行关联学习，CTR和CVR满足pCTCVR = pCTR * pCVR。 pCVR一般是表示在点击后产生转化的概率，之前的模型都使用clicked samples进行训练，又在预测时却在all impression samples来做预测，产生sample selection bias问题。同时CVR的正样本数据要远小于CTR数据，所以两个任务的共享可优化特征表征。宏观上，CVR能使用中间步骤CTR标签，充分利用了数据特性。[[Read more...](https://zhuanlan.zhihu.com/p/37562283)]

## Multimodal Representation Learning

+ [**IJCAI'15**] Kaixiang Mo, Bo Liu, Lei Xiao, Yong Li, Jie Jiang. [Image Feature Learning for Cold Start Problem in Display Advertising](https://www.ijcai.org/Proceedings/15/Papers/524.pdf), *IJCAI*, 2015. [**Tencent**]


