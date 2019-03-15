# NLP Papers

+ [Text Classification](#Text-Classification)
+ [Word Embedding](#Word-Embedding)
+ [Keyphrase Generation](#Keyphrase-Generation)
+ [Language Understanding](#Language-Understanding)

### Text Classification
1. [**ACL'18**] [Joint Embedding of Words and Labels for Text Classification](http://people.ee.duke.edu/~lcarin/acl2018_Guoyin.pdf), by Guoyin Wang, Chunyuan Li, Wenlin Wang, Yizhe Zhang, Dinghan Shen, Xinyuan Zhang, Ricardo Henao, Lawrence Carin. 
1. [**ICLR'18**] [Multi-Task Label Embedding for Text Classification](https://arxiv.org/abs/1710.07210), by Honglun Zhang, Liqiang Xiao, Wenqing Chen, Yongkun Wang, Yaohui Jin. 

### Word Embedding
1. [**NeurIPS**] [FRAGE: Frequency-Agnostic Word Representation](https://arxiv.org/abs/1809.06858), by Chengyue Gong, Di He, Xu Tan, Tao Qin, Liwei Wang, Tie-Yan Liu. [**Microsoft**]
    > 一般来说，Word embedding在popular words上的效果好，在rare words上的效果比较差。本文提出了一种基于对抗学习的方法：一方面学习传统的language model或者word2vec，一方面学习一个discriminator来判别word是popular/rare。通过对抗学习让word embedding对词的频率做到无区别化，从而去除了frequency bias，更多的保留semantic信息，从另一个角度讲，通过co-training可以增强embedding的泛化能力。

### Keyphrase Generation
1. [**AAAI'19**] [Title-Guided Encoding for Keyphrase Generation](https://arxiv.org/abs/1808.08575), by Wang Chen, Yifan Gao, Jiani Zhang, Irwin King, Michael R. Lyu.
1. [**EMNLP'18**] [Semi-Supervised Learning for Neural Keyphrase Generation](https://arxiv.org/abs/1808.06773), by Hai Ye, Lu Wang.
1. [**EMNLP'18**] [Keyphrase Generation with Correlation Constraints](https://arxiv.org/abs/1808.07185), by Jun Chen, Xiaoming Zhang, Yu Wu, Zhao Yan, Zhoujun Li.
1. [**ACL'17**] [Deep Keyphrase Generation](https://arxiv.org/abs/1704.06879), by Rui Meng, Sanqiang Zhao, Shuguang Han, Daqing He, Peter Brusilovsky, Yu Chi.

### Language Understanding
1. [**NIPS'17**] [Attention Is All You Need](https://arxiv.org/abs/1706.03762), by Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, Illia Polosukhin. [**Google**]
    > 本文提出了NLP中的经典Transformer模型，完全基于self-attention的叠加来做sentence encoding和decoding。虽然attention weight的计算方法比较多，但这里的self-attention的计算同时使用了三个matrices，query matrix (Q), key matrix (K), value matrix (V). Q为中心位置使用，K为其他位置使用，V为其他位置使用，所有矩阵都是通过一层线性映射得到，维度也比word vector要低。同时在attention过softmax之前经过了scale的处理，值得借鉴。另外Transformer也引入了positional embedding和residual connection的使用。[[Read more](http://jalammar.github.io/illustrated-transformer/)][[Read more 2](https://zhuanlan.zhihu.com/p/48508221)]

