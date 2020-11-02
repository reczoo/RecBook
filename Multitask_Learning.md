# Multitask Learning

1. [**CoRR'19**] [Deep Bayesian Multi-Target Learning for Recommender Systems](https://arxiv.org/abs/1902.09154), by Qi Wang, Zhihui Ji, Huasheng Liu, Binqiang Zhao. [**Alibaba**]

1. [**KDD'19**] [Predicting Different Types of Conversions with Multi-Task Learning in Online Advertising](https://arxiv.org/abs/1907.10235), by Junwei Pan, Yizhi Mao, Alfonso Lobos Ruiz, Yu Sun, Aaron Flores. [**Verizon Media**, **Indeed**]

1. [**KDD'18**] [Perceive Your Users in Depth: Learning Universal User Representations from Multiple E-commerce Tasks](https://arxiv.org/abs/1805.10727), by Yabo Ni, Dan Ou, Shichen Liu, Xiang Li, Wenwu Ou, Anxiang Zeng, Luo Si. [**Alibaba**]

1. [**SIGIR'18**] Xiao Ma, Liqin Zhao, Guan Huang, Zhi Wang, Zelin Hu, Xiaoqiang Zhu, Kun Gai. [Entire Space Multi-Task Model: An Effective Approach for Estimating Post-Click Conversion Rate](https://arxiv.org/pdf/1804.07931), *SIGIR*, 2018. [**Alibaba**]
   > 本文提出了基于multi-task learning的框架ESMM首次将CTR和CVR两个task进行关联学习，CTR和CVR满足pCTCVR = pCTR * pCVR。 pCVR一般是表示在点击后产生转化的概率，之前的模型都使用clicked samples进行训练，又在预测时却在all impression samples来做预测，产生sample selection bias问题。同时CVR的正样本数据要远小于CTR数据，所以两个任务的共享可优化特征表征。宏观上，CVR能使用中间步骤CTR标签，充分利用了数据特性。[[Read more...](https://zhuanlan.zhihu.com/p/37562283)]