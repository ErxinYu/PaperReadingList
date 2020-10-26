# Paper Reading List


## Conference Website

[Conference DeadLine](https://jackietseng.github.io/conference_call_for_paper/conferences.html)

|               | 2020           | 2019           | 2018             |
|---------------|----------------|----------------|------------------|
|ACL            |                                                                                                                             |[ACL 2019](http://www.acl2019.org/EN/program.xhtml)|                                                          
|EMNLP          |                                                                                                                             |[EMNLP 2019](https://www.emnlp-ijcnlp2019.org/program/accepted/)                                                             |[EMNLP2018](https://www.aclweb.org/anthology/events/emnlp-2018/#d18-1)|                                                          
|NAACL          |                                                                                                                             |[NAACL 2019](https://naacl2019.org/program/accepted/)                                                                         |
|COLING         |                                                                                                                             |                                                                                                                             |[COLING 2018](https://coling2018.org/index.html%3Fp=1556.html)|                                                                                
|AAAI           |[AAAI2020](https://aaai.org/Conferences/AAAI-20/wp-content/uploads/2020/01/AAAI-20-Accepted-Paper-List.pdf)                   |[AAAI2019](https://aaai.org/Conferences/AAAI-19/wp-content/uploads/2018/11/AAAI-19_Accepted_Papers.pdf)|                                                                                  
|IJCAI          |                                                                                                                             |[IJCAI2019](https://www.ijcai19.org/accepted-papers.html)                                                                     |



## Distantly Relation Extraction


- **Self-Attention Enhanced Selective Gate with Entity-Aware Embedding for Distantly Supervised Relation Extraction.** *Yang Li, Guodong Long, Tao Shen, Tianyi Zhou, Lina Yao, Huan Huo, Jing Jiang.* AAAI 2020. [paper](https://arxiv.org/pdf/1911.11899.pdf)
  >   提出了三个机制: 1.entity-aware embedding 在训练的过程中 动态的加强实体(位置)的权重,这个好像很有效果。2.提出self
      -attention 补充PCNN 在捕捉long-term上的不足，对已经embedding好的做self_attention。3.提出Selective Gate,为了弥补att机制在one-           sentence bag问题上的不足，实验证明确实有效果。
      总结:这篇效果不错，在570K的数据集上测试，在0.4@recall的基础上可以达到 0.65 在没有利用额外信息的情况下达到了SOTA效果,有可以借鉴的地方，但是
      没有代码。这篇中提到PCNN+HATT的效果 AUC是0.42，PCNN_ATT 是在one_sentence上比的 AUC达到0.35 ACC有78%(保持怀疑)
      

- **Are Noisy Sentences Useless for Distant Supervised Relation Extraction?.** *Yu-Ming Shang, He-Yan Huang, Xian-Ling Mao, Xin Sun1,Wei Wei.* AAAI 2020. [paper](https://aaai.org/Papers/AAAI/2020GB/AAAI-ShangY.133.pdf)
  >   motivation是针对很多正例样本中的噪声，之前如果标错了就用att或者remove掉，现在用无监督的方法为这些label重新标一下(但是还没有明确标完之后怎么       处理) 中这里只针对正样例的标签改。 Noise Detector 判断哪些是Noisy、Valid、Ignore,根据bag_present的阈值。 Label Generator 根据聚类改       变标签。
      总结: 效果比PCNN_ATT高一点，且在PR图上表示。

- **Improving Neural Relation Extraction with Positive and Unlabeled Learning.** *Zhengqiu He and Wenliang Chen and Yuyi Wang
Wei Zhang and Guanchun Wang and Min Zhang.* AAAI 2020. [paper](https://arxiv.org/pdf/1911.12556.pdf)
  >  用强化学习 挑出句子中的噪声, 然后带噪声的句子标成Unlabeled, 结合Positive的句子的representation和unlabeled句子的representation。跟之前      强化学习比不同的是没有改变数据集分布。
     总结: 效果相当不错。0.4@recall的基础上可以达到 0.5+。

- **Fine-tuning pre-Train Transformer Language Models to Distantly Supervised Relation Etraction.** *Christoph Alt, Marc Hübner, Leonhard Hennig.* ACL 2019. [paper](https://www.aclweb.org/anthology/P19-1134) [code](https://github.com/DFKI-NLP/DISTRE)
   >  利用transformer 模型进行编码 接上PCNN+ATT 结果有个特点就是召回率高的情况下下 准确率下降的慢，但是一开始的准确率不高。PCNN+ATT的auc在这篇文       章中是0.34左右。

- **DIAG-NRE: A Neural pattern Diagnosis Framwork for Distantly Supervised Neural Relation Extraction.**  ACL 2019. [paper](https://pdfs.semanticscholar.org/96b4/f3633d9544593aa6c50949e345d4016c8b48.pdf?_ga=2.234154974.1922655975.1565091217-775842260.1562830956)

- **ARNOR: Attention Regularization based Noise Reduction for Distant Supervision Relation Classification.**  ** *Wei Jia, Dai Dai, Xinyan Xiao and Hua Wu.* ACL 2019. [paper](https://www.aclweb.org/anthology/P19-1135.pdf)

- **Uncover the Ground-Truth Relations in Distant Supervision: A Neural Expectation Maximization Framework.** *Junfan Chen, Richong Zhang, Yongyi Mao, Hongyu Guo and Jie Xu.* EMNLP 2019. [paper](https://arxiv.org/pdf/1909.05448.pdf)

- **Self-Attention Enhanced CNNs and Collaborative Curriculum Learning for Distantly Supervised Relation Extraction.** *Yuyun Huang and Jinhua Du.* EMNLP 2019. [paper](https://www.aclweb.org/anthology/D19-1037.pdf)

- **Looking Beyond Label Noise: Shifted Label Distribution Matters in Distantly Supervised Relation Extraction.** *Linmei Hu, Luhao Zhang, Chuan Shi, Liqiang Nie, Weili Guan and Cheng Yang.* EMNLP 2019. [paper](https://arxiv.org/pdf/1904.09331.pdf)

- **Improving Distantly-Supervised Relation Extraction with Joint Label Embedding.** *Qinyuan Ye, Liyuan Liu, Maosen Zhang and Xiang Ren.* EMNLP 2019. [paper](https://www.aclweb.org/anthology/D19-1395.pdf)

- **Leveraging 2-hop Distant Supervision from Table Entity Pairs for Relation Extraction.** *xiang deng and Huan Sun.* EMNLP 2019. [paper](https://arxiv.org/pdf/1909.06007.pdf)

- **Long-tail Relation Extraction via Knowledge Graph Embeddings and Graph Convolutino Networks.** *Ningyu Zhang, Shumin Deng, Zhanlin Sun, Guanying Wang, Xi Chen, Wei Zhang, Huajun Chen.* NAACL 2019. [paper](https://www.aclweb.org/anthology/N19-1306)

- **Distant Supervision Relation Extraction with Intra-Bag and Inter-Bag Attentions.** NAACL 2019. [paper](https://pdfs.semanticscholar.org/d037/67e0d40d257165bc3faff9c7fa68cdc93035.pdf?_ga=2.239529667.1922655975.1565091217-775842260.1562830956)

- **Exploiting Noisy Data in Distant Supervison Relation Classification.** NAACL 2019. [paper](https://www.aclweb.org/anthology/N19-1325)
  > Paper With Redistributed Dataset  

- **GAN driven Semi-distant Supervison for Relation Extraction.** NAACL 2019. [paper](https://www.aclweb.org/anthology/N19-1307)
  > Paper With Redistributed Dataset  

- **Cross-relation Cross-bag Attention for Distantly-supervised Relation Extraction.** AAAI 2019. [paper](https://arxiv.org/pdf/1812.10604.pdf)

- **Relation Extraction Using Supervision from Topic Knowledge of Relation Labels.** *Haiyun Jiang, Li Cui, Zhe Xu, Deqing Yang, Jindong Chen, Chenguang Li, Jingping Liu, Jiaqing Liang, Chao Wang, Yanghua Xiao, Wei Wang IJCAI 2019.* [paper](https://www.ijcai.org/Proceedings/2019/0698.pdf)

- **Robust Distant Supervision Relation Extraction via Deep Reinforcement Learning.** ACL 2018.  [paper](https://www.aclweb.org/anthology/P18-1199)
  >Paper With Redistributed Dataset  

- **DSGAN: Generative Adversarial Training for Distant Supervision Relation Extraction.** ACL 2018.  [paper](https://www.aclweb.org/anthology/P18-1046)
  > Paper With Redistributed Dataset  

- **Attention-Based Capsule Networks with Dynamic Routing for Relation Extraction.** *Ningyu Zhang.* ACL 2018(short paper).  [paper](https://www.aclweb.org/anthology/D18-1120.pdf)

- **Label-Free Distant Supervision for Relation Extraction via Knowledge Graph Embedding.** EMNLP 2018. [paper](https://www.aclweb.org/anthology/D18-1248)
  > Paper With Redistributed Dataset  
  
- **RESIDE: Improving Distantly-Supervised Neural Relation Extraction using Side Information.** EMNLP 2018. [paper](https://www.aclweb.org/anthology/D18-1157.pdf)

- **Hierarchical Relation Extraction with Coarse-to-Fine Grained Attention.** *Xu Han, Pengfei Yu, Zhiyuan Liu, Maosong Sun, Peng Li.* EMNLP 2018. [paper](https://www.aclweb.org/anthology/D18-1247.pdf)

- **Multi-Level Structured Self-Attentions for Distantly Supervised Relation Extraction.** *Jinhua Du, Jingguang Han, Andy Way, Dadong Wan.* EMNLP 2018. [paper](https://www.aclweb.org/anthology/D18-1245.pdf)

- **Cooperative Denoising for Distantly Supervised Relation Extraction.** *Kai Lei, Daoyuan Chen, Yaliang Li, Nan Du, Min Yang, Wei Fan, Ying Shen.* COLING 2018. [paper](https://www.aclweb.org/anthology/C18-1036.pdf)

- **Large Scaled Relation Extraction with Reinforcement Learning.** AAAI 2018.  [paper](http://www.nlpr.ia.ac.cn/cip/~liukang/liukangPageFile/zeng_aaai2018.pdf)

- **Reinforcement Learning for Relation Classification from Noisy Data.** AAAI 2018. [paper](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/viewPaper/17151)
  > Paper With Redistributed Dataset  

- **Exploring Encoder-Decoder Model for Distant Supervised Relation Extraction.** IJCAI 2018. [paper](https://www.ijcai.org/proceedings/2018/0610.pdf)

- **Neural Relation Extraction with Selective Attention over Instances.** *Yankai Lin, Shiqi Shen, Zhiyuan Liu,, Huanbo Luan
, Maosong Sun.*  ACL 2016. [paper](https://www.aclweb.org/anthology/P16-1200v2.pdf)

- **Relation Extraction with Multi-instance Multi-label Convolutional Neural Networks. COLING 2016.** [paper](https://pdfs.semanticscholar.org/8731/369a707046f3f8dd463d1fd107de31d40a24.pdf)

- **Distant Supervision for Relation Extraction via Piecewise Convolutional Neural Networks.** EMNLP 2015. [paper](http://www.emnlp2015.org/proceedings/EMNLP/pdf/EMNLP203.pdf) 

- **Multi-Task Transfer Learning for Weakly-Supervised Relation Extraction.** ACL2010. [paper](https://www.aclweb.org/anthology/P09-1114)

## Other Relation Rxtraction (Supervied, few-shot, document-level, etc.)

- **Integrating Relation Constraints with Neural Relation Extractors.** *ZYuan Ye, Yansong Feng, Bingfeng Luo, Yuxuan Lai, Dongyan Zhao.* AAAI 2020. [paper](https://arxiv.org/pdf/1911.11493.pdf) 

- **Distilling Knowledge from Well-informed Soft Labels.** *Zhenyu Zhang, Xiaobo Shu, Bowen Yu, Tingwen Liu, Jiapeng Zhao, Quangang Li, Li Guo.* AAAI 2020. [paper](https://aaai.org/Papers/AAAI/2020GB/AAAI-ZhangZ.7408.pdf) 

- **Relation Extraction Exploiting Full Dependency Forests.** *Lifeng Jin, Linfeng Song, Yue Zhang, Kun Xu, Wei-yun Ma and Dong Yu.* AAAI 2020. [paper](https://freesunshine0316.github.io/files/RE_parser_joint__AAAI_2020_.pdf) 

- **NERO: A Neural Rule Grounding Framework for Label-Efficient Relation Extraction.** *Wenxuan Zhou, Hongtao Lin, Bill Yuchen Lin, Ziqi Wang, Junyi Du, Leonardo Neves, Xiang Ren.* WWW 2020. [paper](https://arxiv.org/pdf/1909.02177.pdf) 

- **Exploiting Entity BIO Tag Embeddings and Multi-task Learning for Relation Extraction with Imbalanced Data.** 
*Wei Ye, Bo Li, Rui Xie, Zhonghao Sheng, Long Chen, Shikun Zhang.* ACL 2019. [paper](https://www.aclweb.org/anthology/P19-1130.pdf) 

- **Exploiting Entity BIO Tag Embeddings and Multi-task Learning for Relation Extraction with Imbalanced Data.** 
*Wei Ye, Bo Li, Rui Xie, Zhonghao Sheng, Long Chen, Shikun Zhang.* ACL 2019. [paper](https://www.aclweb.org/anthology/P19-1130.pdf) 

- **Fine-Grained Temporal Relation Extraction .** 
*Siddharth Vashishtha -University of Rochester* . [paper](https://www.aclweb.org/anthology/P19-1280.pdf) 

## Multi-label classification
Multi-Label Learning with Global and Local Label Correlation  
Exploring Correlation between Labels to improve Multi-Label Classification  
Multi-Label Learning by Exploiting Label Correlations Locally  
SGM: Sequence Generation Model for Multi-label Classification  
Deep Learning with a Rethinking Structure for Multi-label Classification

## Avaiable Tecnology

- **Hierarchical Entity Typing via Multi-level Learning to Rank.** ACL2020. [paper](https://arxiv.org/pdf/2004.02286.pdf)

- **A Deep Reinforced Sequence-to-Set Model for Multi-Label Text Classification.** AAAI2019. [paper](https://arxiv.org/pdf/1809.03118.pdf)

-  **Representation Learning of Knowledge Graphs with Hierarchical Types.** IJCAI 2016.[paper](http://nlp.csai.tsinghua.edu.cn/~lzy/publications/ijcai2016_tkrl.pdf)

-  **Multi-Label Zero-Shot Learning with Structured Knowledge Graphs. CVPR.** [paper](http://openaccess.thecvf.com/content_cvpr_2018/papers/Lee_Multi-Label_Zero-Shot_Learning_CVPR_2018_paper.pdf)


## Hierarchical Classification
- **Hierarchical Text Classification with Reinforced Label Assignment.** EMNLP2019. [paper](https://arxiv.org/pdf/1908.10419.pdf)

- **A survey of hierarchical classification across different application domains.** 2012. [paper](https://link.springer.com/content/pdf/10.1007/s10618-010-0175-9.pdf)
- Top-down Strategies for Hierarchical Classification of Transposable Elements with Neural Networks.

- **大规模分类任务的分层学习** *胡清华* [paper](http://121.194.63.124/Slides/Huqinghua-MLA2017.pdf)

## Label Embedding, Label-Specific 

- **Label Embedding for Zero-shot Fine-grained Named Entity Typing** *Yukun Ma, Erik Cambria, Sa Gao.* COLING 2016. [paper](https://sentic.net/label-embedding-for-zero-shot-named-entity-typing.pdf) 

- **Description-Based Zero-shot Fine-Grained Entity Typing** *Rasha Obeidat, Xiaoli Fern, Hamed Shahbazi and Prasad Tadepalli.* NAACL 2019. [paper](https://www.aclweb.org/anthology/N19-1087.pdf)

- **Employing the Correspondence of Relations and Connectives to Identify Implicit Discourse Relations via Label Embeddings** *Linh The Nguyen,Linh Van Ngo†,Khoat Than† and Thien Huu Nguyen.* ACL 2019. [short paper](https://www.aclweb.org/anthology/P19-1411.pdf)

- **Label-Specific Document Representation for Multi-Label Text Classification** *Xiao, Lin and Huang, Xin and Chen, Boli and Jing, Liping.* EMNLPL 2019. [long paper](https://www.aclweb.org/anthology/D19-1044.pdf) [code](https://github.com/EMNLP2019LSAN/LSAN)

- **Hierarchically-Refined Label Attention Network for Sequence Labeling** *Leyang Cui
and Yue Zhang.* EMNLPL 2019. [long paper](https://www.aclweb.org/anthology/D19-1422.pdf)

- **Rethinking Self-Attention: Towards Interpretability in Neural Parsing** *Khalil Mrini, Franck Dernoncourt, Trung Bui, Walter Chang, Ndapa Nakashole.*  [long paper](https://arxiv.org/pdf/1911.03875.pdf)
- Multi-Task Label Embedding for Text Classification

## Resources
[funNLP](https://github.com/fighting41love/funNLP)

[OpenNRE](https://github.com/thunlp/OpenNRE/tree/old_version)




