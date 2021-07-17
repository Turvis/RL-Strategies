##  在算法交易问题中使用RL

###  概述
强化学习已经被应用在了很多的领域， 包括算法交易。 在本文中，交易被理解为马尔可夫定理的游戏， 他们包括了状态， 行动以及奖励。 本文的交易策略可以达到66%的年化交易率


### 导论
本文旨在设计一个能够在证券交易所买卖固定数量的金融工具的控制系统。 该算法旨在最大限度上的利益最大化。 作为金融工具， 我们在项目中考虑RTS指数期货， 饰演的部分数据是从俄罗斯大型交易所获得的。 佣金考虑改交易所期货交易的价格考虑的， 算法的设计基于<strong>强化学习</strong>， 因为这是最适合的延迟奖励的方法。 相比较监督学习， 强化学习不需要创建规则，这些规则必须要含有一定的权重。 我们使用修改后的异步算法， 作为近似函数， 研究了集中人工神经网络结构。 我们发现对网络深度和参数的数量变化以及引入LSTM

今天， 有很多的强化学习算法， 其中一部分已经被应用于算法交易， 例如 Q-Learning ， 深度学习以及反复强化学习的方法中。 然而这个领域正在快速稳定的发展中。 在这项工作中， 我们构建了一个典型的强化学习的环境， 包括状态， 行动以及奖励的功能。 此外我们假设这一进程拥有马尔可夫定理。 作为学习方法， 我们应用A3C的方法， 这个算法在很多的数据集上展现了效率。作为学习方法， 我们在算法操作的过程中进行了改良，在基本方法上搜索人工智能网络架构。

### 强化学习在交易问题的组成
我们更加细致的考虑交易过程。 让我们修复金融工具以及每次成交量， 让我们统一量子系统决定每次卖出以及买入的量。 我们的系统需要在每一步去选择一个Action。Long： Natural 以及 Short

我们用马尔可夫决策过程来形容这个环境， M =   {S, A , P, Gamma , R },  
 - s:  观察状态的空间， 每一步， 交换代理的系统都在S中。   $S_t$ 作为当前出嫁的聚合或者LSTM的内存单元的内部状态
 - A： 动作的空间。 在每一个交易问题中， 动作是 ： Long ，Nautral Short
 - 在每一个步中， 我们选择从已经构建好的Politics 中选择Action， 因此， 从S中选择A的概率
 - P（S‘｜S， a） ： 马尔可夫过程的Transition Probability 
 - R（s，a）： Reward ， 在每一步， Agent 依赖于reward， 不仅是现在的Reward 也包括之前的Action的Reward
 - gammga ： Decay multiplier ，

### 实现
-  The Training of the Neural network is perfomed bevery Nsteps = 200Steps. 
-  Nworker. The number of parallel processes which was fixed in this work equal 10 
-  Each epoch of training was conducted on the tree month data contining 50k one minutes steps 
-  
