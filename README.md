# Social-Network

总结了一下几种社会网络的构建方法

1. 规则网络 （每个节点与k个节点相连接，即每个节点度相同） regular network
2. 随机图 random network
   
   * ER模型、——Selected Models for Agent-based Simulation of Social Network
   
     构造方法：任意一对节点之间以概率P构建link
   
   * a random power law graph——A Random Graph Model for Power Law Graphs
3. 小世界网络 small-world network
   
   特性：较短的平均路径长度和较大的聚类系数
   
   * WS
   
   * 改进的WS（初始结构为2D grid 的规则网）
   
   * 改进的WS（初始为K-dimension mesh的结构）——（Selected Models for Agent-based Simulation of Social Network）
   
     构造方法： 在规则网络的基础上（一般 K = 4），每个节点以概率P与较远的节点重连
4. 无标度网络 （基于PA） free-scale-network

   特性：度分布服从幂指数分布
   
   * BA模型（没有高聚类系数）
   
     构造方法：开始与较少的节点m0，每次新增一个带有m条边的节点，进行择优连接，且连接到节点i的概率与节点i的度数相关。若m = 1，则在选择接节点时先随机选择网络中一条边
     再从该link的两个末端节点中随机选择一个。
     一般，P(k) ~ K^-3
   * 混合PA步骤和TC步骤（提高聚类系数）
   
     TC过程：随机选择一个节点，在它的partners中随机选择两个，如果这两个点之间没有link则构建新的link。如果随机选择的节点，它的partners少于两个，则从它自身引出一个link到
     任意一个随机的节点；第二步是随机选择一个节点，以概率P删除该节点和从该节点引出的所有links，然后引入一个新的节点，连接到任意一个随机的节点上。
   
   * biased preferential attachment、transitive linking（类似PA+TC）——Emergence of a Small World from Local Interactions: Modeling Acquaintance Networks
5. group 模型 （Selected Models for Agent-based Simulation of Social Network）

   此类模型并不是用于生成一个网络，但是可以用来在网络导航上增加捷径。
6. Evolutionary network——（The effect of structural disparities on knowledge diffusion in networks: an agent-based simulation model）
   
   过程分为两步：1、将partners 的partners作为候选连接对象，如果数量小于某阈值，再随机添加其他的节点到候选中。2，从候选中选择度最高的与它相连接 。
   （该过程只会产生新连接，没有删除连接的过程）
   
7. 初始时没有连接，在交互过程中不断构建连接。——Agent-Based Creation and Simulation of Artificial Social Networks and the Analysis of Their Properties
   
