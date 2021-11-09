# graph-defense-learning
## 论文1：Transferring Robustness for Graph Neural Network Against Poisoning Attacks（PA-GNN WSDM2020）
### 论文思想：在被投毒的图中无法去区分对抗边和正常边，该工作提出利用干净的图，利用监督知识去训练（提高）检测对抗边的能力，通过惩罚聚合机制（给对抗边更低的注意力系数），简言之，该工作就是通过检测出对抗边，同时在邻居信息聚合过程中给对抗边的邻居更少的聚合权重。
