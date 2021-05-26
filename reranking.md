## Reranking in Recommendation


+ [**U-Rank**][**Huawei**] [U-rank: Utility-oriented Learning to Rank with Implicit Feedback](https://arxiv.org/pdf/2011.00550.pdf), by Xinyi Dai, Jiawei Hou, Qing Liu, Yunjia Xi, Ruiming Tang, Weinan Zhang, Xiuqiang He, Jun Wang, Yong Yu. *CIKM 2020*.
  > 本文提出utility-aware的重排模型，即先通过一个CTR模型f(x, position)训练得到position-aware的CTR预测值，然后利用pctr(p)\*bid预估出item在不同位置的utility。然后采用另一个模型f(x, bid)来学习排序分数，采用pairwise learning (BPR)的方法学习，并参考LambaLoss构建将delta_utility(即pair排错时带来的utility损失)作为每个pair的weight，训练完后直接用f(x, bid)进行最终排序。缺点是pairwise的训练速度很慢。

+ [**PRM**][**Alibaba**] [Personalized Re-ranking for Recommendation](https://arxiv.org/abs/1904.06813), by Changhua Pei, Yi Zhang, Yongfeng Zhang, Fei Sun, Xiao Lin, Hanxiao Sun, Jian Wu, Peng Jiang, Wenwu Ou. *RecSys 2019*.
  > 本文采用transformer构建K条样本之间的交互，最后通过softmax + BCE损失函数进行优化，相当于K-input-K-output的group打分函数。在构建训练样本时，通过曝光log取前K条样本与label进行训练。




