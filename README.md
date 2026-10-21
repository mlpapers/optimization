# Optimization

## Foundations and constrained optimization

- **[Convex optimization](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)** — 2004. Convex objectives and feasible sets make local optima global. Covers duality, optimality conditions, and numerical algorithms; convexity must be established for the actual formulation.
- **[Linear programming](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)** — 2004. Optimizes a linear objective under linear equality and inequality constraints. Simplex and interior-point methods address this structured problem class.
- **[KKT conditions](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)** — 2004. Combines feasibility, stationarity, and complementary slackness. These conditions are sufficient for convex problems; necessity requires appropriate regularity or strong duality.
- **[Newton and interior-point methods](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)** — 2004. Newton steps use local quadratic models. Interior-point methods solve constrained convex problems through a sequence of smooth subproblems.
- **[Proximal algorithms](https://web.stanford.edu/~boyd/papers/pdf/prox_algs.pdf)** — 2013. Handles nonsmooth penalties and constraints through proximal subproblems, generalizing projection. Includes proximal gradient, acceleration, and splitting methods.
- **[Frank–Wolfe / conditional gradients](https://proceedings.mlr.press/v28/jaggi13.html)** — 2013. Uses linear minimization over a convex feasible set instead of Euclidean projection. Jaggi gives primal–dual certificates and sparse-update analysis; the advantage depends on having a tractable linear oracle.
- **[Mirror descent](https://arxiv.org/abs/1405.4980)** — 2014/2015. Uses a distance induced by a convex mirror map to adapt optimization to non-Euclidean geometry. Bubeck’s analysis connects the map and norm to convergence; Euclidean gradient descent is one geometry choice.
- **[ADMM](https://web.stanford.edu/~boyd/papers/pdf/admm_distr_stats.pdf)** — 2011. Splits structured optimization into coupled subproblems. The review covers distributed convex learning, convergence conditions, and implementation; nonconvex extensions need separate analysis.
- **[Coordinate descent](https://arxiv.org/abs/1502.04759)** — 2015. Approximately minimizes along individual coordinates or blocks. Reviews convergence, acceleration, and parallel variants, mainly for convex objectives.
- **[L-BFGS](https://link.springer.com/article/10.1007/BF01589116)** — 1989. A limited-memory quasi-Newton method for large nonlinear optimization. Approximates curvature without storing a full dense Hessian.

## Gradient methods and adaptive updates

- **[Gradient descent variants](https://arxiv.org/abs/1609.04747)** — 2016. Contrasts full-batch, stochastic, and mini-batch gradients; surveys momentum, adaptive learning rates, optimization difficulties, and parallel training.
- **[Large-scale stochastic optimization](https://arxiv.org/abs/1606.04838)** — 2016. Connects stochastic-gradient theory to practical machine learning, including noise reduction and approximate second-order methods.
- **[Initialization and momentum](https://proceedings.mlr.press/v28/sutskever13.html)** — 2013. Studies how initialization and the momentum schedule affect training deep and recurrent networks. Poor initialization can defeat otherwise effective momentum settings.
- **[Nesterov acceleration](https://hengshuaiyao.github.io/papers/nesterov83.pdf)** — 1983. Combines gradient steps with extrapolation. Establishes an O(1/k²) objective-gap rate for smooth convex minimization under the paper's assumptions, not arbitrary neural-network training.
- **[AdaGrad](https://jmlr.org/papers/v12/duchi11a.html)** — 2011. Adapts optimization geometry to observed gradients, with online regret guarantees. Useful when informative features occur at different frequencies.
- **[AdaDelta](https://arxiv.org/abs/1212.5701)** — 2012. Adapts learning rates per dimension using first-order information. Proposed to address AdaGrad's diminishing learning rates and sensitivity to a manually chosen global rate.
- **[RMSprop](https://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf)** — Hinton’s lecture 6e describes scaling each gradient by a running root-mean-square of recent gradients. Exponential averaging emphasizes recent magnitudes, unlike AdaGrad’s cumulative sum.
- **[Adam and AdaMax](https://arxiv.org/abs/1412.6980)** — 2014. Adam combines first- and second-moment gradient estimates with bias correction; AdaMax uses an infinity-norm variant. Later convergence analyses qualify the original guarantees.
- **[Nadam](https://openreview.net/pdf?id=OM0jvwB8jIp57ZJjtNEZ)** — 2016. Modifies Adam's momentum component using Nesterov-style acceleration. The workshop paper reports preliminary empirical evidence, not a universal improvement over Adam.
- **[AMSGrad](https://arxiv.org/abs/1904.09237)** — 2018. Exhibits a convex counterexample to Adam convergence and introduces longer-term gradient memory. Corrects weaknesses in the original analysis under specified optimization assumptions.
- **[AdamW](https://arxiv.org/abs/1711.05101)** — 2017. Decouples weight decay from the adaptive gradient update. L2 regularization and multiplicative weight decay are generally not equivalent in adaptive optimizers.
- **[TAdam](https://arxiv.org/abs/2003.00179)** — 2020. Uses a Student-t-based update to reduce sensitivity to gradient outliers. Robust gradient estimation is the motivation; the paper does not establish superiority on every task.
- **[LaProp](https://arxiv.org/abs/2002.04839)** — 2020. Separates momentum from adaptive gradient normalization. Studies instability caused by coupling these components and proposes a different update order.
- **[Adafactor](https://arxiv.org/abs/1804.04235)** — 2018. Factors second-moment statistics into row and column estimates for matrix parameters, reducing optimizer-state memory. Also studies update clipping and learning-rate choices.
- **[Shampoo](https://arxiv.org/abs/1802.09568)** — 2018. Uses tensor-structured matrix preconditioners to capture gradient geometry beyond coordinatewise scaling. Provides regret analysis in the online convex setting.
- **[Lion](https://arxiv.org/abs/2302.06675)** — 2023. An optimizer discovered through program search, using momentum and sign-based updates. Its learning-rate scale differs from Adam's, so comparisons require separate tuning.
- **[Sophia](https://arxiv.org/abs/2305.14342)** — 2023. Combines momentum with an intermittently estimated diagonal Hessian and clipping. Designed for language-model pretraining; curvature estimation adds its own cost and choices.
- **[Muon for language-model training](https://arxiv.org/abs/2502.16982)** — 2025. Studies matrix-orthogonalized updates at scale, including weight decay, update scaling, and distributed implementation. Reported efficiency depends on the training setup.
- **[SAM](https://arxiv.org/abs/2010.01412)** — 2020. Minimizes loss over a neighborhood of parameter values to seek solutions with low loss and low local sharpness. This changes the training objective and gradient computation.
- **[When SGD escapes local minima](https://arxiv.org/abs/1802.06175)** — 2018. Interprets SGD through a smoothed objective. Escape and convergence results rely on assumptions about that objective and the noise; they are not general guarantees for all loss surfaces.
- **[SAGA](https://arxiv.org/abs/1407.0202)** — 2014. Caches component gradients and uses their average to correct stochastic updates, reducing gradient variance for finite-sum objectives; supports proximal updates for nonsmooth regularization.
- **[D-Adaptation](https://arxiv.org/abs/2301.07733)** — 2023. Adapts step sizes without specifying an initial learning rate; distinguishes convex Lipschitz convergence guarantees from empirical SGD and Adam variants for deep learning.

## Bayesian optimization

- **[Bayesian optimization foundations](https://arxiv.org/abs/1012.2599)** — 2010. Uses a probabilistic surrogate and an acquisition function to choose expensive evaluations. Balances learning about uncertain regions against exploiting promising ones.
- **[Practical Bayesian optimization](https://arxiv.org/abs/1206.2944)** — 2012. Studies Gaussian-process choices for hyperparameter tuning, including acquisition functions, evaluation costs, and parallel evaluations.
- **[Bayesian optimization review](https://www.cs.ox.ac.uk/people/nando.defreitas/publications/BayesOptLoop.pdf)** — 2016. Reviews surrogate models, acquisition strategies, and extensions for automated design and machine learning. Useful for locating assumptions behind a particular BO setup.
- **[REMBO](https://www.cs.ubc.ca/~hutter/papers/13-IJCAI-BO-highdim.pdf)** — 2013. Uses random embeddings to search high-dimensional objectives with low effective dimensionality. Ambient dimension alone does not determine whether this reduction is suitable.
- **[Choosing an embedding domain](https://arxiv.org/abs/1704.05318)** — 2017. Examines the search bounds used with random embeddings. Small domains can exclude useful solutions; large domains can waste evaluations and weaken the dimensionality advantage.
- **[HeSBO](https://proceedings.mlr.press/v97/nayebi19a.html)** — 2019. Uses hashing-based embeddings for Bayesian optimization in lower-dimensional subspaces. Analyzes approximation behavior and evaluates the method on high-dimensional problems.
- **[SIRBO](https://arxiv.org/abs/1907.08953)** — 2019. Learns an objective-relevant subspace through supervised dimension reduction, including sliced inverse regression. The embedding is informed by observed objective values.
- **[SILBO](https://arxiv.org/abs/2005.14601)** — 2020. Combines evaluated points with unlabeled acquisition candidates to learn an embedding for high-dimensional Bayesian optimization; includes a randomized projection strategy.
- **[BOHB](https://proceedings.mlr.press/v80/falkner18a.html)** — 2018. Combines model-based configuration proposals with Hyperband's allocation of evaluation budgets. Intended for tuning when lower-budget runs provide useful information.
- **[TuRBO](https://arxiv.org/abs/1910.01739)** — 2019. Fits local probabilistic models within adaptive trust regions and allocates evaluations across regions, targeting expensive black-box optimization beyond a single global surrogate.

## Perturbation-based gradient estimation

- **[SPSA](https://www.jhuapl.edu/spsa/pdf-spsa/spall_tac92.pdf)** - 1992. Estimates a gradient from two noisy loss evaluations with simultaneous random perturbations of all coordinates. Evaluation count per estimate is independent of dimension; convergence still requires noise, smoothness and step-size assumptions.
- **[Neural credit assignment](https://mlpapers.org/neural-nets/#credit-assignment-and-alternatives-to-backpropagation)** - Perturbation estimators, random feedback, local losses and forward-mode autodiff provide different learning signals. These methods differ in derivative use, objectives and compute costs; see the neural-network comparisons.

## Evolutionary and population-based search

- **[Evolutionary computation](https://www.nature.com/articles/35076523)** — 2001. Reviews search through populations, selection, and variation, including genetic algorithms and evolving programs. These methods optimize a supplied fitness criterion.
- **[CMA-ES](https://arxiv.org/abs/1604.00772)** — 2016. Covariance-matrix adaptation for stochastic optimization of nonlinear, nonconvex functions over continuous parameters. The tutorial derives the search strategy and its design choices.
- **[Differential evolution](https://link.springer.com/article/10.1023/A:1008202821328)** — 1997. A population-based heuristic for continuous global optimization, including nondifferentiable objectives. Empirical comparisons in the original paper do not imply general dominance.
- **[Memetic algorithms](https://www.sciencedirect.com/science/article/pii/S2210650211000691)** — 2012. Combines evolutionary search with local search components. Reviews discrete, continuous, constrained, multiobjective, and uncertain problems, emphasizing coordination between operators.
- **[Learning classifier systems](https://doi.org/10.1155/2009/736398)** — 2009. Reviews rule-based learning systems and their evolutionary components. Different implementations address classification, robotics, knowledge discovery, and modeling.
- **[Population Based Training](https://arxiv.org/abs/1711.09846)** — 2017. Jointly trains a population of models and adapts their hyperparameter schedules. Combines asynchronous training with selection and exploration across population members.
- **[Harmony search](https://doi.org/10.1177/003754970107600201)** — 2001. A heuristic inspired by musical improvisation, illustrated on traveling-salesman and engineering-design problems. Its metaphor does not establish general optimization guarantees.

## Local search and swarm methods

- **[Metropolis-based optimization](https://doi.org/10.1287/opre.18.6.1225)** — 1970. Approximates a constrained minimum using integral representations and Metropolis sampling. The analysis assumes a closed bounded domain and a unique minimizer.
- **[Simulated annealing](https://doi.org/10.1126/science.220.4598.671)** — 1983. Connects optimization to thermal annealing: randomized moves can accept worse states, with acceptance controlled by temperature. Cooling schedule and finite evaluation budget matter.
- **[Tabu search](https://doi.org/10.1287/inte.20.4.74)** — 1990. Uses search memory, tabu restrictions, and aspiration criteria to guide local search. Intensification and diversification control revisiting promising regions and exploring new ones.
- **[Variable neighborhood search](https://link.springer.com/article/10.1007/s13675-016-0075-x)** — 2017. Systematically changes neighborhoods during descent and perturbation. Reviews basic schemes, parallel implementations, and hybrids for escaping local-search traps.
- **[Artificial bee colony](https://abc.erciyes.edu.tr/pub/tr06_2005.pdf)** — 2005. A numerical optimization heuristic based on honey-bee foraging, with employed, onlooker, and scout roles balancing exploitation of food sources and exploration.
- **[Cuckoo search](https://arxiv.org/abs/1003.1594)** — 2010. Combines a brood-parasitism-inspired search scheme with Lévy flights for global optimization. The cited work evaluates numerical test functions.
- **[Firefly algorithm](https://arxiv.org/abs/1003.1409)** — 2010. Applies the heuristic to nonlinear design optimization and introduces stochastic or singular test functions with known optima. Evidence is restricted to the tested problems.
- **[Particle swarm optimization](https://www.cs.tufts.edu/comp/150GA/homeworks/hw3/_reading6%201995%20particle%20swarming.pdf)** — 1995. Moves candidate solutions using velocities influenced by each particle's best position and the swarm's best position. A derivative-free population heuristic for continuous search.

## Bandits and sequential allocation

- **[Sequential experimental design](https://projecteuclid.org/journals/bulletin-of-the-american-mathematical-society/volume-58/issue-5/Some-aspects-of-the-sequential-design-of-experiments/bams/1183517370.pdf)** — 1952. Studies experiments whose sampling decisions depend on earlier observations. Also explains why optional stopping can invalidate tests designed for fixed sample sizes.
- **[Finite-time bandit analysis](https://link.springer.com/article/10.1023/A:1013689704352)** — 2002. Analyzes exploration–exploitation policies with logarithmic regret uniformly over time for bounded reward distributions. Guarantees concern the stated stochastic bandit setting.
- **[Empirical bandit comparison](https://bandit.sourceforge.net/Vermorel2005poker.pdf)** — 2005. Compares multi-armed bandit algorithms and introduces the POKER strategy. Results on the paper's reward settings are not a universal ranking of exploration policies.
- **[Bayesian probability matching](https://www.economics.uci.edu/files/docs/micro/s11/Scott.pdf)** — 2010. Allocates observations according to posterior probabilities that each arm is optimal. Connects Bayesian computation, adaptive experimental design, and bandit heuristics.
- **[Bandit regret survey](https://arxiv.org/abs/1204.5721)** — 2012. Covers stochastic and adversarial payoffs, finite actions, and contextual extensions. Regret bounds depend on the feedback model and assumptions about rewards.
- **[Thompson sampling](https://arxiv.org/abs/1707.02038)** — 2017. Reviews posterior-sampling approaches to sequential decisions, applications with shared information across actions, and settings where the method is or is not effective.

## Multiple objectives and evaluation

- **[NSGA-II](https://doi.org/10.1109/4235.996017)** — 2002. Combines nondominated sorting with elitist selection from parents and offspring, balancing fitness and spread. Approximates a set of trade-offs instead of choosing a single objective weighting.
- **[AlgoPerf](https://arxiv.org/abs/2306.07179)** — 2023. Benchmarks time to a target result across neural-network workloads on fixed hardware. Controls tuning protocols and workload variants to distinguish optimizer gains from evaluation artifacts.

## Software

- **[SciPy optimize](https://docs.scipy.org/doc/scipy/reference/optimize.html)** — Python solvers for local and global optimization, constraints, linear programming, least squares, root finding, and curve fitting. Solver choice depends on problem structure.
- **[CVXPY](https://www.cvxpy.org/)** — Python modeling language for expressing optimization problems and passing them to numerical solvers. Supports convex modeling and additional structured problem classes.
- **[HiGHS](https://highs.dev/)** — Open-source solvers for sparse linear, mixed-integer, and quadratic programming. Provides a C++ library, command-line executable, and language interfaces.
- **[Optax](https://optax.readthedocs.io/en/latest/)** — Composable gradient transformations and optimization algorithms for JAX. Supports assembling custom optimizers from smaller update components.
- **[Sherpa](https://arxiv.org/abs/2005.04048)** — 2020. Python hyperparameter optimization for expensive iterative models, with local or cluster execution and a visualization dashboard.
- **[pymoo](https://arxiv.org/abs/2002.04504)** — 2020. Python framework for single- and multiobjective optimization, with constraints, customizable operators, parallel evaluation, and visualization.
- **[ensmallen](https://ensmallen.org/)** — C++ numerical optimization library built around Armadillo. Includes gradient-based and derivative-free optimizers, with callbacks for monitoring and control.

## Related Topics

- [Neural Networks](https://mlpapers.org/neural-nets/)
- [AutoML](https://mlpapers.org/automl/)
- [Bayesian Inference](https://mlpapers.org/bayesian-inference/)
- [Reinforcement Learning](https://mlpapers.org/reinforcement-learning/)
