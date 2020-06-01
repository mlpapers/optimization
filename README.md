# Optimization ([Wiki](https://en.wikipedia.org/wiki/Mathematical_optimization))

- **Overview**
  - [An overview of gradient descent optimization algorithms](https://arxiv.org/pdf/1609.04747.pdf) (2017) *Sebastian Ruder*
  - [Derivative tests](https://en.wikipedia.org/wiki/Derivative_test#First-derivative_test)

### Linear programming
- **Simplex algorithm** ([Wiki](https://en.wikipedia.org/wiki/Simplex_algorithm))

### Gradient-based optimization
- **Batch gradient descent**
- **Stochastic gradient descent**
  - [An Alternative View:  When Does SGD Escape Local Minima?](https://arxiv.org/pdf/1802.06175.pdf) (2018) *Robert Kleinberg, Yuanzhi Li, Yang Yuan*
- **Mini-batch gradient descent**
- **Momentum**
- **Nesterov accelerated gradient**
- **Adagrad**
- **Adadelta**
- **RMSprop**
- **Adam, AdaMax**
  - [Adam: A Method for Stochastic Optimization](https://arxiv.org/pdf/1412.6980.pdf) (2017) *Diederik P. Kingma, Jimmy Ba*
- **TAdam**
  - [TAdam: A Robust Stochastic Gradient Optimizer](https://arxiv.org/pdf/2003.00179.pdf) (2020) *Wendyam Eric Lionel Ilboudo, Taisuke Kobayashi, Kenji Sugimoto*
- **Nadam**
- **AMSGrad**
- **LaProp** ([Code](https://github.com/Z-T-WANG/LaProp-Optimizer))
  - [LaProp: a Better Way to Combine Momentum with Adaptive Gradient](https://arxiv.org/pdf/2002.04839.pdf) (2020) *Liu Ziyin, Zhikang T.Wang, Masahito Ueda*

### Bayesian optimization
  - [A Tutorial on Bayesian Optimization of Expensive Cost Functions, with Application to Active User Modeling and Hierarchical Reinforcement Learning](https://arxiv.org/pdf/1012.2599.pdf) (2010) *Eric Brochu, Vlad M. Cora, Nando de Freitas*
  - [Practical Bayesian Optimization of Machine Learning Algorithms](https://arxiv.org/pdf/1206.2944.pdf) (2012) *Jasper Snoek, Hugo Larochelle, Ryan P. Adams*
  - [Taking the Human Out of the Loop: A Review of Bayesian Optimization](https://www.cs.ox.ac.uk/people/nando.defreitas/publications/BayesOptLoop.pdf) (2016) *Bobak Shahriari, Kevin Swersky, Ziyu Wang, Ryan P. Adams, Nando de Freitas*
- **REMBO** 
  - [Bayesian Optimization in High Dimensions via Random Embeddings](https://www.cs.ubc.ca/~hutter/papers/13-IJCAI-BO-highdim.pdf) (2013) *Ziyu Wang, Masrour Zoghi, Frank Hutter, David Matheson, Nando De Freitas*
  - [On the choice of the low-dimensional domain for globaloptimization via random embedding](https://arxiv.org/pdf/1704.05318.pdf) (2018) *Mickael Binois, David Ginsbourger, Olivier Roustant*
- **HeSBO**
  - [A Framework for Bayesian Optimization in Embedded Subspaces](http://proceedings.mlr.press/v97/nayebi19a/nayebi19a.pdf) (2019) *Alexander Munteanu, Amin Nayebi, Matthias Poloczek*
- **SIRBO**
  - [High Dimensional Bayesian Optimization via Supervised Dimension Reduction](https://arxiv.org/pdf/1907.08953.pdf) (2019) *Miao Zhang, Huiqi Li, Steven Su*
- **SI-BO**
- **SILBO**
  - [Semi-supervised Embedding Learning for High-dimensionalBayesian Optimization](https://arxiv.org/pdf/2005.14601.pdf) (2020) *Jingfan Chen, Guanghui Zhu, Rong Gu, Chunfeng Yuan, Yihua Huang*

### Evolutionary algorithms ([Wiki](https://en.wikipedia.org/wiki/Evolutionary_algorithm))
- Imitate some aspects of natural evolution
- **GA** Genetic algorithm ([Wiki](https://en.wikipedia.org/wiki/Genetic_algorithm))
- **MA** Memetic algorithm ([Wiki](https://en.wikipedia.org/wiki/Memetic_algorithm))
- **GP** Genetic programming
- **ES** Evolutionary strategies
- **EP** Evolutionary programming
- **LCS** Learning classifier systems
- **Harmony search**
- **PBT** Population-based Training
  - [Population Based Training of Neural Networks](https://arxiv.org/pdf/1711.09846.pdf) (2017) *Max Jaderberg, Valentin Dalibard, Simon Osindero, Wojciech M. Czarnecki, Jeff Donahue, Ali Razavi, Oriol Vinyals, Tim Green, Iain Dunning, Karen Simonyan, Chrisantha Fernando, Koray Kavukcuoglu*

### Trajectory-based algorithms
- **Simulated annealing**
  - [Approximate Solution of Certain Types of Constrained Optimization Problems](https://pubsonline.informs.org/doi/pdf/10.1287/opre.18.6.1225) (1970) *Martin Pincus*
  - [Optimization by Simulated Annealing](http://leonidzhukov.net/hse/2013/stochmod/papers/KirkpatrickGelattVecchi83.pdf) (1983) *S. Kirkpatrick, C. D. Gelatt, M. P. Vecchi*
- **Hill climbing**
- **b-Hill climbing**
- **Tabu search**
- **Variable neighborhood search**

### Swarm-based algorithms
- **Artificial bee colony**
- **Cuckoo search**
- **Firefly algorithm**
- **Particle swarm** ([Wiki](https://en.wikipedia.org/wiki/Particle_swarm_optimization))
  - [Particle Swarm Optimization](https://www.cs.tufts.edu/comp/150GA/homeworks/hw3/_reading6%201995%20particle%20swarming.pdf) (1995) *James Kennedy, Russell Eberhart*

### Multi-armed bandits ([Wiki](https://en.wikipedia.org/wiki/Multi-armed_bandit))
- [Some Aspects of the Sequential Design of Experiments](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.335.3232&rep=rep1&type=pdf) (1952) *Herbert Robbins*
- [Multi-armed Bandit Algorithmsand Empirical Evaluation](http://bandit.sourceforge.net/Vermorel2005poker.pdf) (2005) *Joannes Vermorel, Mehryar Mohri*
- [A modern Bayesian look at the multi-armed bandit](http://www.economics.uci.edu/~ivan/asmb.874.pdf) (2010) *Steven L. Scott*

### Heuristic algorithms

### Multimodel optimization

### Multiobjective optimization
  - [Pareto set](https://en.wikipedia.org/wiki/Pareto_efficiency#Use_in_engineering)

### Software
- **Python**
  - Sherpa ([Docs](https://parameter-sherpa.readthedocs.io/en/latest/), [Code](https://github.com/sherpa-ai/sherpa), [Paper](https://arxiv.org/pdf/2005.04048.pdf))
  - PyMOO ([Homepage](https://pymoo.org/), [Paper](https://arxiv.org/pdf/2002.04504.pdf))

- **C++**
  - Emsmallen ([Homepage](https://ensmallen.org/))
