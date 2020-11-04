# News Recommendation

1. [ACL'2020] Fine-grained Interest Matching for Neural News Recommendation

1. [ACL'2020] Graph Neural News Recommendation with Unsupervised Preference Disentanglement

1. [WWW'2020] Graph Enhanced Representation Learning for News Recommendation

1. [IJCAI'2020] User Modeling with Click Preference and Reading Satisfaction for News Recommendation

1. [RecSys'2020] KRED: Knowledge-Aware Document Representation for News Recommendations

1. [EMNLP'2019] Neural News Recommendation with Multi-Head Self-Attention

1. [EMNLP'2019] Neural News Recommendation with Heterogeneous User Behavior

1. [KDD'2019] NPA: Neural News Recommendation with Personalized Attention
  > 简介：本文在新闻推荐场景下，提出personalized attention机制，第一步首先根据转换后的user emb作为query向量聚合news下的words为新闻表征r，在此基础上再次以转换后的user emb为query向量聚合历史点击的news序列为新的用户表征向量u，最后以u和r的内积作为预测值，目标函数类似DSSM取sampled softmax，作为排序任务。评价指标为AUC和NDCG。
