# ***Unit III: Random Processes***

# <u>**L13. Bernoulli Process**</u>

### Definition

- A sequence of independent Bernoulli trials
- At each trial, $i$ :
	- $\mathbf{P} \text { (success) }=\mathbf{P}\left(X_{i}=1\right)=p$
	- $\mathbf{P} \text { (failure) }=\mathbf{P}\left(X_{i}=0\right)=1-p$

## **Random processes**

- First view: sequence of random variables $X_1, X_2,...$
	- $\mathbf{E}\left[X_{t}\right]=p \cdot 1+(1-p) \cdot 0=p$
	- $\operatorname{Var}\left(X_{t}\right)=p(1-p)$
- Second view: what is the right sample space?
	- $\mathbf{P}\left(X_{t}=1\text{ for all } t\right)= 0$

## **Bernoulli Process**

### Binomial PMF

- Number of successes $S$ in $n$ time slots
	- $\mathbf{P}(S=k)=\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k}$ 
	- $\mathbf{E}[S]=np$ 
	- $\operatorname{Var}(S)=m p(1-p)$

### Geometric PMF

- $T_{1}$ : number of trials until first success
	- $\mathrm{P}\left(T_{1}=t\right)=(1-p)^{t-1} p$
	- $\mathrm{E}\left[T_{1}\right]=1 / p$
	- $\operatorname{Var}\left(T_{1}\right)=(1-p) / p^{2}$
- Memoryless property

### Pascal PMF

- Time of the $k$th arrival
	- Given that first arrival was at time $t$ i.e., $T_{1}=t$ : additional time, $T_{2}$, until next arrival
	- has the same (geometric) distribution
	- independent of $T_{1}$
- $Y_{k}:$ number of trials to $k$ th success $\rightarrow Y_k = T_1+T_2+\dots+T_k$
  - $\mathbf{E}\left[Y_{k}\right]={k\over p}$
  - $\operatorname{Var}\left(Y_{k}\right)=k(1-p)/p^2$
  - $\mathbf{P}\left(Y_{k}=t\right)= \left(\begin{array}{c}
    t-1 \\
    k-1
    \end{array}\right) p^{k}(1-p)^{t-k}$

$$
\begin{aligned}

\end{aligned}
$$

## *Thinking*

- 伯努利过程 Bernoulli Process
	- 无记忆性：解决问题时开始观察的时间点的选择至关重要
		- 例如：第一个失败序列的长度，要从第一个失败之后开始观察，若从第一个失败之前开始观察则观察的第一个实验不是伯努利实验 Bernoulli Trial

# <u>**L14. Poisson Process I**</u>

## **Definition**

- Time homogeneity:
$\mathbf{P}(k, \tau)=$ Prob. of $k$ arrivals in interval of duration $\tau$
- Numbers of arrivals in disjoint time intervals are independent
- $\lambda$ : "arrival rate" (or intensity)
$$
\lambda = \lim_{\delta\to 0} {\mathbf{P}(1,\delta)\over \delta} \\
\text{for very small time interval }\delta
$$

## **PMF of Number of Arrivals $N$**

- Finely discretize $[0, \tau]:$ approximately Bernoulli

	<img src="image.assets/Screen Shot 2021-11-13 at 09.56.07.png" alt="Screen Shot 2021-11-13 at 09.56.07" style="zoom:33%;" />
	$$
	n = {\tau\over \delta}\qquad p = \lambda\delta = {\lambda\tau\over n}\\
	\mathbf{P}(k\text{ arrivals}) = \left( \begin{array}{c}n\\k\end{array} \right)\left({\lambda\tau\over n}\right)^k \left(1-{\lambda\tau\over n}\right)^{n-k}
	$$
	
- $N_{\tau}$ (of discrete approximation): binomial

- Taking $\delta \rightarrow 0$ (or $n \rightarrow \infty$ ) gives:
  $$
  \mathbf{P}(k, \tau)=\frac{(\lambda \tau)^{k} e^{-\lambda \tau}}{k !}, \quad k=0,1, \ldots \\
  \text{for a fixed } \tau \text{, this is possion PMF}
  $$
  $$
  \mathbf{E}\left[N_{\tau}\right]=\lambda \tau, \quad \operatorname{var}\left(N_{\tau}\right)=\lambda \tau
  $$

## **Interarrival Times**

- $Y_{k}$ time of $k$ th arrival
	$$
	\begin{array}{ll}
	f_{Y_{k}}(t) \delta&=\mathbf{P}\left(t \leqslant Y_{k} \leqslant t+\delta\right) \\
	&=\mathbf{P}(k-1 \text { arrivals in }[0, t]) \cdot \lambda \delta \\
	&=\frac{(\lambda t)^{k-1}}{(k-1) !} e^{-\lambda t} \cdot \lambda \delta
	\end{array}
	$$
- Erlang distribution: 
  (sum of $k$ independent exponentials)
  $$
  f_{Y_{k}}(y)=\frac{\lambda^{k} y^{k-1} e^{-\lambda y}}{(k-1) !}, \quad y \geq 0
  $$
  <img src="image.assets/Screen Shot 2021-11-13 at 10.16.08.png" alt="Screen Shot 2021-11-13 at 10.16.08" style="zoom:33%;" />
- Time of first arrival $(k=1)$ :
	Exponential distribution: 
	$$
	\quad f_{Y_{1}}(y)=\lambda e^{-\lambda y}, \quad y \geq 0
	$$
- Memoryless property: The time to the next arrival is independent of the past

## **Bernoulli/Poisson Relation**

| PROCESS                 | POISSON             | BERNOULLI     |
| ----------------------- | ------------------- | ------------- |
| Times of Arrival        | Continuous          | Discrete      |
| Arrival Rate            | $\lambda$/unit time | $p$/per trial |
| PMF of # of Arrivals    | Poisson             | Binomial      |
| Interarrival Time Dist. | Exponential         | Geometric     |
| Time to $k$-th arrival  | Erlang              | Pascal        |

## *Thinking*

- 泊松过程 Poisson Process
	- 在连续时间内发生一系列抵达率/强度相同的独立事件的过程
	- 固定时间的抵达数目的PMF为泊松分布（对应离散的二项分布）
		- 这两个分布都和正态分布有一定关联
	- 抵达时间间隔的指数分布（对应离散的几何分布）
		- 似乎通过[韦伯分布（Weibull）](https://zh.wikipedia.org/wiki/%E9%9F%A6%E4%BC%AF%E5%88%86%E5%B8%83)建立紧密关联
	- 第k次抵达时间的爱尔朗分布（对应离散的帕斯卡分布）

# <u>**L15. Poisson Process II**</u>

## **Random incidence for Poisson**

- Poisson process that has been running forever
- Show up at some “random time”
	(really means “arbitrary time”)
- What is the distribution of the length of the chosen interarrival interval?

## **Random incidence in “renewal processes”**

- Series of successive arrivals
	- i.i.d. interarrival times
		(but not necessarily exponential)
		- i.i.d.: Independent and identically distributed random variables
	- e.g. Bus interarrival times are equally likely to be 5 or 10 min

## *Thinking*

- 泊松过程的随机发生率
	- 选择观察事件的切入点至关重要：
		- 如公交车的间隔问题，选择随机事件进行观察和选择随机车辆进行观察得到的结果完全不同，选择随机时间则会有更大概率选到间隔时间长的车辆
		- 如蛋糕上的巧克力碎片数量，选择蛋糕和选择巧克力碎片进行观察得到的结果完全不同，选择巧克力碎片则会有更大概率选到巧克力碎片数量多的蛋糕



# <u>**L16. Markov Chains I**</u>

- evolution of some variable with some noise that is a bit random

$$
\text{new state} = f(\text{old state}, \text{ noise})
$$

### Checkout counter model

<img src="image.assets/Screen Shot 2021-11-13 at 13.50.32.png" alt="Screen Shot 2021-11-13 at 13.50.32" style="zoom:33%;" />

- Discrete time $n=0,1, \ldots$
- Customer arrivals: Bernoulli $(p)$
	- geometric interarrival times
- Customer service times: geometric $(q)$
- "State" $X_{n}:$ number of customers at time $n$

## **Finite state Markov chains**

- $X_{n}$ : state after $n$ transitions
	- belongs to a finite set, e.g., $\{1, \ldots, m\}$
	- $X_{0}$ is either given or random
- Markov property/assumption: 
	(given current state, the past does not matter)
$$
\begin{aligned}
p_{i j} &=\mathbf{P}\left(X_{n+1}=j \mid X_{n}=i\right) \\
&=\mathbf{P}\left(X_{n+1}=j \mid X_{n}=i, X_{n-1}, \ldots, X_{0}\right)
\end{aligned}
$$
- Model specification:
	- identify the possible states
	- identify the possible transitions
	- identify the transition probabilities

### $n$-step transition probabilities

- State occupancy probabilities, given initial state $i$ :
  $$
  r_{i j}(n)=\mathbf{P}\left(X_{n}=j \mid X_{0}=i\right)
  $$
  <img src="image.assets/Screen Shot 2021-11-13 at 14.03.04.png" alt="Screen Shot 2021-11-13 at 14.03.04" style="zoom:33%;" />
  
  - Key recursion:
    $$
    r_{i j}(n)=\sum_{k=1}^{m} r_{i k}(n-1) p_{k j}\quad \forall\ i,j
    $$
  
  - With random initial state:
    $$
    \mathbf{P}\left(X_{n}=j\right)=\sum_{i=1}^{m} \mathbf{P}\left(X_{0}=i\right) r_{i j}(n)
    $$

### Generic convergence questions

- Does $r_{ij}(n)$ converge to something?
	- periodicity
- Does the limit depend on initial state?

## **Recurrent and transient states**

- State $i$ is recurrent if: starting from $i$, and from wherever you can go, there is a way of returning to $i$
- If not recurrent, called transient
	- $i$ transient:
    $$
    \mathbf{P}\left(X_{n}=i\right) \rightarrow 0
    $$
    $i$ visited finite number of times
- Recurrent class: collection of recurrent states that "communicate" with each other and with no other state

## *Thinking*

- [马尔可夫链](https://zh.wikipedia.org/wiki/%E9%A9%AC%E5%B0%94%E5%8F%AF%E5%A4%AB%E9%93%BE)
	- 定义
		- “为状态空间中经过从一个状态到另一个状态的转换的随机过程”
		- “该过程要求具备‘无记忆’的性质：下一状态的概率分布只能由当前状态决定，在时间序列中它前面的事件均与之无关”
	- 分治：$r_{i j}(n)=\sum_{k=1}^{m} r_{i k}(n-1) p_{k j}\quad \forall\ i,j$
	- 有限状态机
	- 收敛问题
		- 是否收敛：周期性
		- 初始状态的影响
			- 循环态和临时态
			- 循环类：循环态的集合，它们彼此‘交流’但不和其他态‘交流’

# <u>**L17. Markov Chains II**</u>

## **Steady-State Probabilities**

- Do the $r_{i j}(n)$ converge to some $\pi_{j} ?$ (independent of the initial state $i$ )
- Yes, if:
	- recurrent states are all in a single class, and
	- single recurrent class is not periodic
- Assuming "yes," start from key recursion
  $$
  r_{i j}(n)=\sum_{k} r_{i k}(n-1) p_{k j}
  $$
  - take the limit as $n \rightarrow \infty$
    $$
    \pi_{j}=\sum_{k} \pi_{k} p_{k j}, \quad \text { for all } j
    $$
  - Additional equation:
    $$
    \sum_{j} \pi_{j}=1
    $$

### Visit frequency interpretation

- (Long run) frequency of being in $j: \pi_{j}$
- Frequency of transitions $k \rightarrow j: \pi_{k} p_{k j}$
- Frequency of transitions into $j: \quad \sum_{k} \pi_{k} p_{k j}$

## **Birth-death processes**

<img src="image.assets/Screen Shot 2021-11-20 at 10.16.54.png" alt="Screen Shot 2021-11-20 at 10.16.54" style="zoom:45%;" />

- Special case: $p_{i}=p$ and $q_{i}=q$ for all $i$ $\rho=p / q=$ load factor
  $$
  \begin{gathered}
  \pi_{i+1}=\pi_{i} \frac{p}{q}=\pi_{i} \rho \\
  \pi_{i}=\pi_{0} \rho^{i}, \quad i=0,1, \ldots, m
  \end{gathered}
  $$

- Assume $p<q$ and $m \approx \infty$
  $$
  \begin{array}
  \pi_{0}=1-\rho \\
  \mathbf{E}\left[X_{n}\right]=\frac{\rho}{1-\rho} \quad \text { (in steady-state) }
  \end{array}
  $$

## *Thinking*

- 马尔可夫链 II
	- 稳态概率 $\pi_{j}=\sum_{k} \pi_{k} p_{k j}, \quad \text { for all } j$
		- 访问频率解读
	- 出生死亡过程
		- 利用访问频率解读的简化算法 $\pi_{i} p_{i}=\pi_{i+1} q_{i+1}$

# <u>**L18. Markov Chains III**</u>

## **Example: The phone company problem**

- Calls originate as a Poisson process, rate $\lambda$

	- Each call duration is exponentially distributed (parameter $\mu$ )
	- $B$ lines available

- Discrete time intervals of (small) length $\delta$

	<img src="../../../../Application Support/typora-user-images/Screen Shot 2021-11-20 at 17.11.54.png" alt="Screen Shot 2021-11-20 at 17.11.54" style="zoom:33%;" />

- Balance equations: 
	$$
	\lambda \pi_{i-1}=i \mu \pi_{i}
	$$
	
	$$
	\pi_{i}=\pi_{0} \frac{\lambda^{i}}{\mu^{i} i !} \quad \pi_{0}=1 / \sum_{i=0}^{B} \frac{\lambda^{i}}{\mu^{i} i !}
	$$
	

## **Absorption**

### Probability

- What is the probability $a_{i}$ that: process eventually settles in state 4 , given that the initial state is $i$ ?

<img src="image.assets/Screen Shot 2021-11-21 at 10.10.49.png" alt="Screen Shot 2021-11-21 at 10.10.49" style="zoom:33%;" />
$$
\text{For }i=4, a_{i}=1\\
\text{For }i=5, a_{i}=0\\
a_{i}=\sum_{j} p_{i j} a_{j}, \quad \text { for all other } i
$$

### Expected time

- Find expected number of transitions $\mu_{i}$, until reaching the absorbing state, given that the initial state is $i$ ?

<img src="image.assets/Screen Shot 2021-11-21 at 10.13.23.png" alt="Screen Shot 2021-11-21 at 10.13.23" style="zoom:33%;" />
$$
\mu_{i}=0 \text { for } i=4 \\

\text{For all other i: }\mu_{i}=1+\sum_{j} p_{i j} \mu_{j}
$$
## **Mean first passage and recurrence times**

- Chain with one recurrent class; 
	fix $s$ recurrent
- Mean first passage time from $i$ to $s$:
  $$
	t_{i}=\mathbf{E}\left[\min \left\{n \geq 0 \text { such that } X_{n}=s\right\} \mid X_{0}=i\right]
	$$
- $t_{1}, t_{2}, \ldots, t_{m}$ are the unique solution to
  $$
  \begin{aligned}
  t_{s} &=0 \\
  t_{i} &=1+\sum_{j} p_{i j} t_{j}, \quad \text { for all } i \neq s
  \end{aligned}
  $$
- Mean recurrence time of $s$: 
	$$
	t_{s}^{*}=\mathbf{E}\left[\min \left\{n \geq 1 \text { such that } X_{n}=s\right\} \mid X_{0}=s\right]\\\\
	t_{s}^{*}=1+\sum_{j} p_{s j} t_{j}
	$$

## *Thinking*

- 马尔可夫链的例子
	- 电话公司问题
	- 吸收（absorption）到循环类（recurrent class）的概率和期望时间
	- 第一次经过和循环的期望/平均时间





