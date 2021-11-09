# graph-defense-learning （2020）
## 论文1：Transferring Robustness for Graph Neural Network Against Poisoning Attacks（PA-GNN WSDM2020）
 论文思想：在被投毒的图中无法去区分对抗边和正常边，该工作提出利用干净的图，利用监督知识去训练（提高）检测对抗边的能力，通过惩罚聚合机制（给对抗边更低的注意力系数），简言之，该工作就是通过检测出对抗边，同时在邻居信息聚合过程中给对抗边的邻居更少的聚合权重。

**做法：**  

该算法设计一种元优化算法，即利用干净图和对抗图训练PA-GNN去惩罚扰动边，转移这种能力去提高PA-GNN在中毒图上的鲁棒性，即首先学习区分对抗边并减少他们的负面影响，然后**再将这种能力**转移到中毒图上的GNN。

**挑战:**  

(1)如何在数学上利用干净的图为GNN减少对抗性边缘负面影响的能力  

(2)如何有效地将在干净图上的这种能力迁移到投毒图上去

**贡献：**  

1、提出探索干净图的原理方法，用来学习针对目标图中中毒攻击的鲁棒GNN  

2、提出一个新的框架PA_GNN，通过设计惩罚聚合机制去消除对抗边的影响，并同时使用元优化算法去将这种能力迁移到投毒攻击上面  

**模型**  



**疑问：**  

1、在做防御的时候应该是不知道干净图的数据的，这里是怎么知道的？？  ，干净的原数据不知道，但是能找到M个与投毒图共享相似域的干净图。如，攻击的图是引文网数据图，那就去找其它引文网数据图的干净数据图M个（我觉得这里的设计是不是有点牵强！！）







**想法：**  

1、该工作提出现在没有好的方法去区分对抗边和扰动边，但若如果将异质边全部认为是扰动边，这样是不是可以检测出扰动边？？**（我现在的工作是不是可以从这个角度去说？还是从预处理图说这个工作）**  

2、文中也提出，添加连接两个社团的桥边可以影响许多节点的潜在表示 **（先验证mettack和nettack攻击后图图数据是否有这样的现象，如果有这样的现象，那我们是不是可以先进行社团划分，再删掉不同社团之间的边，这样看看是否能够提升鲁棒性）
