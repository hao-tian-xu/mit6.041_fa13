## 概念  

### 概念

- 样本空间 $\Omega$
  - 颗粒度：如天气是否影响掷骰子

- 条件概率：$\mathbf{P}(A \mid B)=\frac{\mathbf{P}(A \cap B)}{\mathbf{P}(B)}$
  - 全概率定理：$\mathbf{P}(B)= \sum\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(B \mid A_{i}\right)$
  - 贝叶斯定理：$\mathbf{P}\left(A_{i} \mid B\right) =\frac{\mathbf{P}\left(A_{i} \cap B\right)}{\mathbf{P}(B)} =\frac{\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(B \mid A_{i}\right)}{\mathbf{P}(B)} =\frac{\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(B \mid A_{i}\right)}{\sum_{j} \mathbf{P}\left(A_{j}\right) \mathbf{P}\left(B \mid A_{j}\right)}$
    - 概率分布变体
      - 离散：$\begin{cases}p_{X \mid Y}(x \mid y)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)}=\frac{p_{X}(x) p_{Y \mid X}(y \mid x)}{p_{Y}(y)} \\
        p_{Y}(y)=\sum_{x} p_{X}(x) p_{Y \mid X}(y \mid x) \end{cases}$
        - 例子：X - 飞机是否出现，Y - 雷达是否显示
      - 连续：$\begin{cases}f_{X \mid Y}(x \mid y) =\frac{f_{X, Y}(x, y)}{f_{Y}(y)}=\frac{f_{X}(x) f_{Y \mid X}(y \mid x)}{f_{Y}(y)} \\
        f_{Y}(y) =\int_{x} f_{X}(x) f_{Y \mid X}(y \mid x) d x\end{cases}$
        - 例子：X - 发射的信号，Y - 接收到的有噪音的信号，f~Y|X~(y|x) - 噪音信号模型
      - 离散X连续Y：$\begin{cases}p_{X \mid Y}(x \mid y)=\frac{p_{X}(x) f_{Y \mid X}(y \mid x)}{f_{Y}(y)} \\
        f_{Y}(y)=\sum_{x} p_{X}(x) f_{Y \mid X}(y \mid x) \end{cases}$
        - 例子：X - 发射的离散信号，Y - 接收到的有噪音的信号，f~Y|X~(y|x) - 噪音信号模型
      - 连续X离散Y：$\begin{cases}f_{X \mid Y}(x \mid y)=\frac{f_{X}(x) p_{Y \mid X}(y \mid x)}{p_{Y}(y)} \\
        p_{Y}(y)=\int_{x} f_{X}(x) p_{Y \mid X}(y \mid x) d x\end{cases}$
        - 例子：X - 发射的信号，Y - 接收到的离散信息，p~Y|X~(y|x) - 离散信息的模型
- 独立：$\mathbf{P}(B \mid A)=\mathbf{P}(B)$，$\mathbf{P}(A \cap B)=\mathbf{P}(A) \cdot \mathbf{P}(B)$
  - 条件独立：$\mathbf{P}(A \cap B \mid C) = \mathbf{P}(A \mid C) \cdot \mathbf{P}(B \mid C)$
- 组合：$\left(\begin{array}{l} n \\ k \end{array}\right)=\frac{n !}{k !(n-k) !}$
  - 离散型均匀分布：$\mathbf{P}(A)=\frac{\text { number of elements of } A}{\text { total number of sample points }}=\frac{|A|}{|\Omega|}$ （<u>Discrete Uniform Law</u>）
- 随机变量：为每个可能的结果分配一个值（数字）
  - 随机变量 $X$：函数 $\Omega\to \mathbb{R}$
  - 离散随机变量
  - 连续随机变量 $\mathbf{P} (a \leq X \leq b)=\int_{a}^{b} f_{X}(x) d x$
    - $\mathbf{P} (X = a)= 0$
- 概率质量函数PMF：离散随机变量的概率分布 $p_{X}(x) = \mathbf{P}(X=x) = \mathbf{P}(\{\omega \in \Omega \text { s.t. } X(\omega)=x\})$
  - 条件PMF：$p_{X \mid A}(x)=\mathbf{P}(X=x \mid A)$
    - （全概率质量函数）：$p_{X}(x)=\mathbf{P}\left(A_{1}\right) p_{X \mid A_{1}}(x)+\cdots+\mathbf{P}\left(A_{n}\right) p_{X \mid A_{n}}(x)$
  - 联合PMF：$p_{X, Y}(x, y)=\mathbf{P}(X=x\text{ and }Y=y)$
    - $p_{X \mid Y}(x \mid y)=\mathbf{P}(X=x \mid Y=y)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)}$

  - 边缘PMF：多维随机变量中，只包含其中部分变量的PMF  $p_{X}(x)=\sum_{y} p_{X, Y}(x, y)$
- 概率密度函数PDF：连续随机变量的概率分布 $f_X(x) = \lim_{\delta \to 0} {\mathbf{P}(x\leq X\leq x+\delta)\over \delta}$
  - ​	<img src="image.assets/Screen Shot 2021-11-10 at 11.55.11.png" alt="Screen Shot 2021-11-10 at 11.55.11" style="zoom: 33%;" />
  - 联合PDF：$\mathbf{P}((X, Y) \in S)=\iint_{S} f_{X, Y}(x, y) d x d y$
  - 边缘PDF：$f_{X}(x)=\int_{-\infty}^{\infty} f_{X, Y}(x, y) d y$
  - 条件PDF：$f_{X \mid Y}(x \mid y)=\frac{f_{X, Y}(x, y)}{f_{Y}(y)} \quad \text { if } f_{Y}(y)>0$
- 累计分布函数CDF：$F_{X}(x)=\mathrm{P}(X \leq x)$
  - 离散：$\begin{cases}F_{X}(x)=\mathrm{P}(X \leq x)=\int_{-\infty}^{x} f_{X}(t) d t \\
    \frac{d F_{X}}{d x}(x)=f_{X}(x) \end{cases}$
  - 连续：$\begin{cases}F_{X}(x)=\mathbf{P}(X \leq x)=\sum_{k \leq x} p_{X}(k)\\
    p_{X}(k)=F_{X}(k)-F_{X}(k-1) \end{cases}$
- 导出分布Derived Distribution
  - 导出函数 $g$ 的导数：若 $Y=g(X)$ ，且 $g$ 是严格单调的，则 $f_Y(y) = {1\over g'(x)}f_X(x)$
- 期望值：$\mathbf{E}[X]=\sum_{x} x p_{X}(x)\quad /\quad \int x f_{X}(x) d x$
  - $\mathbf{E}[g(X)]=\sum_{x} g(x) p_{X}(x)\quad /\quad \int_{-\infty}^{\infty} g(x) f_{X}(x) d x$
  - 条件期望值：$\mathbf{E}[X \mid A]=\sum_{x} x p_{X \mid A}(x)$
    - 全期望值定理：$\mathbf{E}[X]=\sum_{y} \mathrm{E}[X \mid Y=y] p_Y(y)\quad / \quad \int_{-\infty}^{\infty} E[X \mid Y=y] f_{Y}(y) d y$
    - $\mathbf{E}[X \mid Y=y]=\sum_{x} x p_{X \mid Y}(x \mid y)$ -->
      $\mathbf{E}[X|Y]$ 是以 $y$ 为参数的函数 -->
      重叠期望值定理：$\mathbf{E}[\mathbf{E}[X \mid Y]]=\sum_{y} \mathbf{E}[X \mid Y=y] p_{Y}(y)=\mathbf{E}[X]$
- 方差：$\operatorname{var}(X)=\mathbf{E}\left[(X-\mathbf{E}[X])^{2}\right]
  =\sum_{x}(x-\mathbf{E}[X])^{2} p_{X}(x)\quad / \quad \int (x-\mathbf{E}[X])^{2} f_{X}(x) d x
  =\mathbf{E}\left[X^{2}\right]-(\mathbf{E}[X])^{2}$
  - 全方差定理：$\operatorname{var}(X)=\mathrm{E}[\operatorname{var}(X \mid Y)]+\operatorname{var}(\mathrm{E}[X \mid Y])$
  - 标准差：$\sigma_{X}=\sqrt{\operatorname{var}(X)}$ （单位与随机变量相同）

- 协方差：$\operatorname{cov}(X, Y)=\mathbf{E}[(X-\mathbf{E}[X]) \cdot(Y-\mathbf{E}[Y])]$ （衡量两个随机变量的联合变化程度）
  - 相关系数：$\rho =\mathbf{E}\left[\frac{(X-\mathbf{E}[X])}{\sigma_{X}} \cdot \frac{(Y-\mathbf{E}[Y])}{\sigma_{Y}}\right] =\frac{\operatorname{cov}(X, Y)}{\sigma_{X} \sigma_{Y}}\quad \in[-1,1]$ （标准化的两个随机变量之间的关系，无单位）
  - $\operatorname{var}\left(\sum_{i=1}^{n} X_{i}\right)=\sum_{i=1}^{n} \operatorname{var}\left(X_{i}\right)+ \sum_{(i, j): i \neq j} \operatorname{cov}\left(X_{i}, X_{j}\right)$


### 概念Constellation

$$
\begin{array}{rcl}
p_{X}(x) &\text{PMF | PDF}& f_{X}(x) \\
p_{X, Y}(x, y) &\text{joint}& f_{X, Y}(x, y) \\
p_{X \mid Y}(x \mid y)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)} &\text{conditional}& f_{X \mid Y}(x \mid y)=\frac{f_{X, Y}(x, y)}{f_{Y}(y)} \\
p_{X}(x)=\sum_{y} p_{X, Y}(x, y) &\text{marginal}& f_{X}(x)=\int_{-\infty}^{\infty} f_{X, Y}(x, y) d y \\
& F_{X}(x)=\mathbf{P}(X \leq x) & \\
\sum_{x} x p_{X}(x) & \mathbf{E}[X] & \int x f_{X}(x) d x \\
\sum_x (x-\mathbf{E}[X])^{2} f_{X}(x) & \operatorname{var}(X) & \int (x-\mathbf{E}[X])^{2} f_{X}(x) d x
\end{array}
$$

## 概率分布（概率函数）

### 离散分布

|                                | $X$                                                          | $p_X(k)$                                                     | $\mathbf{E}[X]$ | $\operatorname{Var}(X)$ |
| ------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | --------------- | ----------------------- |
| Bernoulli                      | $\begin{cases}1 & \text { success } \\ 0 & \text { failure }\end{cases}$ | $\begin{cases}p & k=1 \\ 1-p & k=0\end{cases}$               | $p$             | $p(1-p)$                |
| Binomial                       | Number of successes <br/>in $n$ Bernoulli trials             | $\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k}$<br/>$k=0,1, \ldots, n$ | $np$            | $np(1-p)$               |
| Geometric                      | Number of trials <br/>until first success                    | $(1-p)^{k-1} p$<br/>$k=1,2, \ldots$                          | $1 \over p$     | $1-p \over p^2$         |
| Pascal<br/>(Negative Binomial) | Number of trials <br/>until $n$-th success                   | $\left(\begin{array}{c}k+n-1 \\ n-1\end{array}\right)(1-p)^{k-n} p^{n}$<br/>$k=n,n+1, \ldots$ | $k\over p$      | $k(1-p)/p^2$            |
| Uniform                        | An integer in <br/>the interval $[a,b]$                      | $\begin{cases}\frac{1}{b-a+1} & k=a, \ldots, b \\ 0 & \text { otherwise }\end{cases}$ | $a+b \over 2$   | $(b-a)(b-a+2) \over 12$ |
| Poisson                        | Number of arrivals<br/>during $[0, \tau]$<br/>w/ arrival rate $\lambda$ | $\frac{(\lambda \tau)^{k} e^{-\lambda \tau}}{k !}$<br/>$k=0,1, \ldots$ | $\lambda\tau$   | $\lambda\tau$           |

### 连续分布

|                    | $X$                                                 | $f_X(x)$                                                     | $\mathbf{E}[X]$  | $\operatorname{Var}(X)$ |
| ------------------ | --------------------------------------------------- | ------------------------------------------------------------ | ---------------- | ----------------------- |
| Standard Normal    | $\mathcal{N}(0,1)$                                  | $\frac{1}{\sqrt{2 \pi}} e^{-x^{2} / 2}$                      | $0$              | $1$                     |
| Normal             | $\mathcal{N}\left(\mu, \sigma^{2}\right)$           | $\frac{1}{\sigma \sqrt{2 \pi}} e^{-(x-\mu)^{2} / 2 \sigma^{2}}$ | $\mu$            | $\sigma^2$              |
| Exponential        | Time of first arrival<br/>w/ arrival rate $\lambda$ | $\lambda e^{-\lambda x}$                                     | $1\over \lambda$ | $1\over {\lambda^2}$    |
| Erlang<br/>(Gamma) | time of $k$ th arrival                              | $\frac{\lambda^{k} x^{k-1} e^{-\lambda x}}{(k-1) !}, \quad x \geq 0$ | $k\over \lambda$ | $k\over {\lambda^2}$    |
|                    |                                                     |                                                              |                  |                         |

- 正态分布累计分布函数 Normal CDF
  - 标准正态分布：查表
  - 正态分布：$\begin{cases}
    X \sim N\left(\mu, \sigma^{2}\right) \Leftrightarrow \frac{X-\mu}{\sigma} \sim N(0,1) \\
    P(X \leq x)=P\left(\frac{X-\mu}{\sigma} \leq \frac{x-\mu}{\sigma}\right)=\Phi\left(\frac{x-\mu}{\sigma}\right)
    \end{cases}$

## 随机过程

### 伯努利过程 / 泊松过程

| PROCESS                 | POISSON             | BERNOULLI     |
| ----------------------- | ------------------- | ------------- |
| Times of Arrival        | Continuous          | Discrete      |
| Arrival Rate            | $\lambda$/unit time | $p$/per trial |
| PMF of # of Arrivals    | Poisson             | Binomial      |
| Interarrival Time Dist. | Exponential         | Geometric     |
| Time to $k$-th arrival  | Erlang              | Pascal        |

### 马尔可夫链

- $n$ 步后为状态 $j$ 的概率
  - 给定起始状态 $i$：$r_{i j}(n)=\mathbf{P}\left(X_{n}=j \mid X_{0}=i\right) = \sum_{k=1}^{m} r_{i k}(n-1) p_{k j}\quad \forall\ i,j$
  - 随机起始状态：$\mathbf{P}\left(X_{n}=j\right)=\sum_{i=1}^{m} \mathbf{P}\left(X_{0}=i\right) r_{i j}(n)$
- 稳态：$\pi_{j} = \lim_{n\to \infty}r_{ij}(n) = \lim_{n\to\infty} \sum_{k} r_{i k}(n-1) p_{k j}= \sum_{k} \pi_{k} p_{k j}, \quad \forall j$
  - 条件：非周期性单一循环类
  - $\sum_{j} \pi_{j}=1$

## 收敛

- 切比雪夫不等式：$\mathbf{P}(|X-\mu| \geq c) \leq \frac{\sigma^{2}}{c^{2}}$
- 弱大数定律：$\mathbf{P}\left(\left|M_{n}-\mu\right| \geq \epsilon\right) \leq \frac{\operatorname{Var}\left(M_{n}\right)}{\epsilon^{2}}=\frac{\sigma^{2}}{n \epsilon^{2}}$
  - 其中：$\begin{cases} X_{1}, X_{2}, \ldots \text { i.i.d. w/ finite mean } \mu \text { and variance } \sigma^{2} \\ 
    M_{n}=\frac{X_{1}+\cdots+X_{n}}{n} \end{cases}$
- 中心极限定理：一定条件下,大量i.i.d.随机变量之和（标准化后）的CDF收敛为正态分布的CDF
  - 标准化：$\begin{cases} S_{n}=X_{1}+\cdots+X_{n} \\ Z_{n}=\frac{S_{n}-\mathbf{E}\left[S_{n}\right]}{\sigma_{S_{n}}}=\frac{S_{n}-n \mathbf{E}[X]}{\sqrt{n} \sigma} \end{cases}$
  - 定理：$\begin{cases} Z: \text{ 标准正态分布} \\ \mathbf{P}\left(Z_{n} \leq c\right) \rightarrow \mathbf{P}(Z \leq c) \end{cases}$

## 推断

- 贝叶斯推断
  - 假设检验
    - 离散数据：$p_{\Theta \mid X}(\theta \mid x)=\frac{p_{\Theta}(\theta) p_{X \mid \Theta}(x \mid \theta)}{p_{X}(x)}$
    - 连续数据：$p_{\Theta \mid X}(\theta \mid x)=\frac{p_{\Theta}(\theta) f_{X \mid \Theta}(x \mid \theta)}{f_{X}(x)}$
  - 估计量
    - 最大后验 MAP：$p_{\Theta \mid X}\left(\theta^{*} \mid x\right)=\max _{\theta} p_{\Theta \mid X}(\theta \mid x)\quad / \quad f_{\Theta \mid X}\left(\theta^{*} \mid x\right)=\max _{\theta} f_{\Theta \mid X}(\theta \mid x)$ 
      - 均方误差较大
    - 最小均方误差 LMS：$\mathbf{E}[\Theta \mid X]$
      - 多个数据较难计算
    - 线性最小均方误差：最小化 $\mathbf{E}\left[(\Theta-a X-b)^{2}\right] \quad\to\quad \hat{\Theta}_{L}=\mathbf{E}[\Theta]+\frac{\operatorname{Cov}(X, \Theta)}{\operatorname{var}(X)}(X-\mathbf{E}[X])$
      - 多个数据：最小化 $\mathbf{E}\left[\left(a_{1} X_{1}+\cdots+a_{n} X_{n}+b-\Theta\right)^{2}\right]$
- 经典推断
  - 最大似然估计 MLE：$\widehat{\theta}_{\mathrm{ML}}=\arg \max _{\theta} p_{X}(x ; \theta)$
    - 样本均值：$\frac{X_{1}+\cdots+X_{n}}{n}$ （一般即位最大似然估计）
  - 置信区间 CI：$\mathbf{P}\left(\hat{\Theta}_{n}-\frac{z \sigma}{\sqrt{n}} \leq \theta \leq \widehat{\Theta}_{n}+\frac{z \sigma}{\sqrt{n}}\right) \approx 1-\alpha$    （ $\Phi(z)=1-\alpha / 2$ ）



## *Thinking*

- 可能是最接近日常生活的一门数学，但又是最不像数学的一门数学。
- 使用大量符号系统去精确描述日常事件：掷骰子的各种数据，柜台排队的长短，公交车到达时间，医学仪器检测的精确度等等。
- 由于精确的描述使得系统设计得到逻辑依据，而不是依靠常识
- 主要有几个部分
  - 第一二单元介绍了基本概念，从离散系统开始扩展到连续系统
    - 随机变量的概率函数（<u>分布</u>）：期望值、方差等
    - 贝叶斯定理
  - 第三单元介绍随机过程及其相关<u>分布</u>
  - 第四单元介绍推断，及相关的大数定理
    - 推断：使用数据分析来推断基础概率分布的属性的过程









