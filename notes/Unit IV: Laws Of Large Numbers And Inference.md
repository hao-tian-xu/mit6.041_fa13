# ***Unit IV: Laws Of Large Numbers And Inference***

# <u>**L19. Weak Law of Large Numbers**</u>

## **Chebyshev’s inequality**

- Random variable $X$
(with finite mean $\mu$ and variance $\sigma^{2}$ )
$$
\begin{aligned}
\sigma^{2} &=\int(x-\mu)^{2} f_{X}(x) d x \\
& \geq \int_{-\infty}^{-c}(x-\mu)^{2} f_{X}(x) d x+\int_{c}^{\infty}(x-\mu)^{2} f_{X}(x) d x \\
& \geq c^{2} \cdot \mathbf{P}(|X-\mu| \geq c)
\end{aligned}
$$
$$
\mathbf{P}(|X-\mu| \geq c) \leq \frac{\sigma^{2}}{c^{2}}
$$
$$
\mathbf{P}(|X-\mu| \geq k \sigma) \leq \frac{1}{k^{2}}
$$

## **Limit**

### Deterministic limits

- Sequence $a_{n}$
Number $a$
- $a_{n}$ converges to $a$
  $$
  \lim _{n \rightarrow \infty} a_{n}=a
  $$
  $a_{n}$ eventually gets and stays (arbitrarily) close to $a$
- For every $\epsilon>0$, there exists $n_{0}$
such that for every $n \geq n_{0}$, we have $\left|a_{n}-a\right| \leq \epsilon$

### Convergence “in probability”

- Sequence of random variables $Y_{n}$
- converges in probability to a number $a$ : "(almost all) of the PMF/PDF of $Y_{n}$, eventually gets concentrated (arbitrarily) close to $a$ "
- For every $\epsilon>0$,
  $$
  \lim _{n \rightarrow \infty} \mathbf{P}\left(\left|Y_{n}-a\right| \geq \epsilon\right)=0
  $$

## **The sample mean**

### Weak law of large numbers

- $X_{1}, X_{2}, \ldots$ i.i.d.
finite mean $\mu$ and variance $\sigma^{2}$
$$
M_{n}=\frac{X_{1}+\cdots+X_{n}}{n}
$$
- $E\left[M_{n}\right]=\frac{E[X_1]+\cdots+E[X_M]}{n}=\frac{\mu n}{n}=\mu$
- $\operatorname{var}\left(M_{n}\right)=\frac{n \sigma^{2}}{n^{2}}=\sigma^{2} / n$
$$
\mathbf{P}\left(\left|M_{n}-\mu\right| \geq \epsilon\right) \leq \frac{\operatorname{Var}\left(M_{n}\right)}{\epsilon^{2}}=\frac{\sigma^{2}}{n \epsilon^{2}}
$$
- $M_{n}$ converges in probability to $\mu$

### Example: The pollster’s problem

- $f:$ fraction of population that "..."
- $i$th (randomly selected) person polled:
  $$
  X_{i}= \begin{cases}1, & \text { if yes } \\ 0, & \text { if no. }\end{cases}
  $$
- $M_{n}=\left(X_{1}+\cdots+X_{n}\right) / n$ fraction of "yes" in our sample
- Goal: $95 \%$ confidence of $\leq 1 \%$ error
  $$
  \mathbf{P}\left(\left|M_{n}-f\right| \geq .01\right) \leq .05
  $$
- Use Chebyshev's inequality:
  $$
  \begin{aligned}
  \mathbf{P}\left(\left|M_{n}-f\right| \geq .01\right) & \leq \frac{\sigma_{M_{n}}^{2}}{(0.01)^{2}} \\
  &=\frac{\sigma_{x}^{2}}{n(0.01)^{2}} \leq \frac{1}{4 n(0.01)^{2}}
  \end{aligned}
  $$
- If $n=50,000$ then $\mathbf{P}\left(\left|M_{n}-f\right| \geq .01\right) \leq .05$ (conservative)

## **The central limit theorem**

- "**Standardized**" $S_{n}=X_{1}+\cdots+X_{n}:$
  $$
  Z_{n}=\frac{S_{n}-\mathbf{E}\left[S_{n}\right]}{\sigma_{S_{n}}}=\frac{S_{n}-n \mathbf{E}[X]}{\sqrt{n} \sigma}
  $$
  - zero mean
  - unit variance
- Let $Z$ be a standard normal r.v. (zero mean, unit variance)
- **Theorem**: For every $c$ :
  $$
  \mathbf{P}\left(Z_{n} \leq c\right) \rightarrow \mathbf{P}(Z \leq c)
  $$
- $\mathbf{P}(Z \leq c)$ is the standard normal CDF, $\Phi(c)$, available from the normal tables

## *Thinking*

- 极限（调查的准确度概率）

	- 极限的数学定义
	- 切比雪夫不等式 Chebyshev's Inequality：$\mathbf{P}(|X-\mu| \geq k \sigma) \leq \frac{1}{k^{2}}$

	- 样本均值 Sample Mean：$M_{n}=\frac{X_{1}+\cdots+X_{n}}{n}$
		- $\mathbf{P}\left(\left|M_{n}-\mu\right| \geq \epsilon\right) \leq \frac{\operatorname{Var}\left(M_{n}\right)}{\epsilon^{2}}=\frac{\sigma^{2}}{n \epsilon^{2}}$
	- 中心极限定理 Central Limint Theorem
		- 切比雪夫不等式比较疏松，寻找更紧致的不等式：将样本和标准化



# <u>**L20. Central Limit Theorem**</u>

### Usefulness

- universal; only means, variances matter
- accurate computational shortcut
- justification of normal models

### What exactly does it say?

- CDF of $Z_{n}$ converges to normal CDF
	- not a statement about convergence of PDFs or PMFs

### Normal approximation

- Treat $Z_{n}$ as if normal
	- also treat $S_{n}$ as if normal

### Can we use it when $n$ is "moderate"?

- Yes, but no nice theorems to this effect
- Symmetry helps a lot

### Symmetric vs. Asymmetric

- Symmetric
	- ​	<img src="image.assets/Screen Shot 2021-11-22 at 10.26.12.png" alt="Screen Shot 2021-11-22 at 10.26.12" style="zoom:33%;" />
- Asymmetric
	- ​	<img src="image.assets/Screen Shot 2021-11-22 at 10.26.34.png" alt="Screen Shot 2021-11-22 at 10.26.34" style="zoom:33%;" />

## **Example: The pollster’s problem using the CLT**

- $f:$ fraction of population that " ".."
- $i$th (randomly selected) person polled:
$$
X_{i}= \begin{cases}1, & \text { if yes } \\ 0, & \text { if no }\end{cases}
$$
- $M_{n}=\left(X_{1}+\cdots+X_{n}\right) / n$
- Suppose we want:
$$
\mathbf{P}\left(\left|M_{n}-f\right| \geq .01\right) \leq .05
$$
- Event of interest: $\left|M_{n}-f\right| \geq .01$

$$
\begin{gathered}
\left|\frac{X_{1}+\cdots+X_{n}-n f}{n}\right| \geq .01 \\\\
\left|\frac{X_{1}+\cdots+X_{n}-n f}{\sqrt{n} \sigma}\right| \geq \frac{.01 \sqrt{n}}{\sigma} \\\\
\mathbf{P}\left(\left|M_{n}-f\right| \geq .01\right) \approx \mathbf{P}(|Z| \geq .01 \sqrt{n} / \sigma)
\leq \mathbf{P}(|Z| \geq .02 \sqrt{n})
\end{gathered}
$$

## **Apply to binomial**

- Fix $p$, where $0<p<1$
- $X_{i}$ : Bernoulli $(p)$
- $S_{n}=X_{1}+\cdots+X_{n}: \operatorname{Binomial}(n, p)$
	- mean $n p$, variance $n p(1-p)$
- CDF of $\frac{S_{n}-n p}{\sqrt{n p(1-p)}} \longrightarrow$ standard normal

### Example

- $n=36, p=0.5$; find $\mathbf{P}\left(S_{n} \leq 21\right)$
- Exact answer:

$$
\sum_{k=0}^{21}\left(\begin{array}{c}
36 \\
k
\end{array}\right)\left(\frac{1}{2}\right)^{36}=0.8785
$$

### The 1/2 correction for binomial approximation

- $\mathbf{P}\left(S_{n} \leq 21\right)=\mathbf{P}\left(S_{n}<22\right)$ because $S_{n}$ is integer
- Compromise: consider $\mathbf{P}\left(S_{n} \leq 21.5\right)$

### De Moivre–Laplace CLT (for binomial)

- When the $1 / 2$ correction is used, CLT can also approximate the binomial p.m.f. (not just the binomial CDF)

$$
\begin{gathered}
\mathbf{P}\left(S_{n}=19\right)=\mathbf{P}\left(18.5 \leq S_{n} \leq 19.5\right) \\\\
18.5 \leq S_{n} \leq 19.5 \quad \Longleftrightarrow \\\\
\frac{18.5-18}{3} \leq \frac{S_{n}-18}{3} \leq \frac{19.5-18}{3} \Longleftrightarrow \\\\
0.17 \leq Z_{n} \leq 0.5
\end{gathered}
$$

### Poisson vs. normal approximations of the binomial

- Binomial $(n, p)$
- $p$ fixed, $n \rightarrow \infty:$ normal
- $n p$ fixed, $n \rightarrow \infty, p \rightarrow 0:$ Poisson
- $p=1 / 100, n=100:$ Poisson
- $p=1 / 10, n=500:$ normal

## *Thinking*

- 中心极限定理 Central Limit Theorem （CLT）
	- 一定条件下，大量随机变量之和近似服从正态分布
		- 条件：$X_{1}, \ldots, X_{n}$ i.i.d. 独立同分布，有限方差 $\sigma^{2}$
			- 二项分布中，$p$ 不随 $n$ 改变
	- 例子：
		- 布朗运动：河流中粒子的运动，由大量粒子的随机碰撞决定
		- 金融市场



# <u>**L21. Bayesian Statistical Inference I**</u>

### Types of Inference models/approaches

- Model building versus inferring unknown variables. E.g., assume $X=a S+W$
	- Model building:
	  know "signal" $S$, observe $X$, infer $a$
	- Estimation in the presence of noise: know $a$, observe $X$, estimate $S$.
- Discrete & Continuous
	- Hypothesis testing: unknown takes one of few possible values; aim at small probability of incorrect decision
	- Estimation: aim at a small estimation error

- Methods
	- Classical statistics:
	  <img src="image.assets/Screen Shot 2021-11-25 at 14.19.29.png" alt="Screen Shot 2021-11-25 at 14.19.29" style="zoom:33%;" />
	- Bayesian: Use priors \& Bayes rule
	  <img src="image.assets/Screen Shot 2021-11-25 at 14.10.08.png" alt="Screen Shot 2021-11-25 at 14.10.08" style="zoom:33%;" />

## **Bayesian inference: Use Bayes rule**

### Hypothesis testing

- discrete data
  $$
  p_{\Theta \mid X}(\theta \mid x)=\frac{p_{\Theta}(\theta) p_{X \mid \Theta}(x \mid \theta)}{p_{X}(x)}
  $$
- continuous data
  $$
  p_{\Theta \mid X}(\theta \mid x)=\frac{p_{\Theta}(\theta) f_{X \mid \Theta}(x \mid \theta)}{f_{X}(x)}
  $$

## **Maximum a posteriori probability (MAP)**

- $p_{\Theta \mid X}\left(\theta^{*} \mid x\right)=\max _{\theta} p_{\Theta \mid X}(\theta \mid x)$ 
	minimizes probability of error; 
	often used in hypothesis testing
- $f_{\Theta \mid X}\left(\theta^{*} \mid x\right)=\max _{\theta} f_{\Theta \mid X}(\theta \mid x)$

## **Least Mean Squares Estimation (LMS)**

### Estimation in the absence of information

- find estimate $c$, to:
  minimize $\mathbf{E}\left[(\Theta-c)^{2}\right]$
- Optimal estimate: $c=\mathbf{E}[\Theta]$
- Optimal mean squared error:
  $$
  \mathbf{E}\left[(\Theta-\mathbf{E}[\Theta])^{2}\right]=\operatorname{Var}(\Theta)
  $$

### LMS Estimation of $\Theta$ based on $X$

- Two r.v.'s $\Theta, X$
- we observe that $X=x$
	- new universe: condition on $X=x$
- $\mathbf{E}\left[(\Theta-c)^{2} \mid X=x\right]$ is minimized by $c=\mathbf{E}[\Theta \mid X]$
- $\mathbf{E}[(\Theta-\mathbf{E}[\Theta \mid X\left.=x])^{2} \mid X=x\right] \leq \mathbf{E}\left[(\Theta-g(x))^{2} \mid X=x\right]$
	- $\mathbf{E}\left[(\Theta-\mathbf{E}[\Theta \mid X])^{2} \mid X\right] \leq \mathbf{E}\left[(\Theta-g(X))^{2} \mid X\right]$
	- $\mathbf{E}\left[(\Theta-\mathbf{E}[\Theta \mid X])^{2}\right] \leq \mathbf{E}\left[(\Theta-g(X))^{2}\right]$
$$
\mathbf{E}[\Theta \mid X] \text { minimizes } \mathbf{E}\left[(\Theta-g(X))^{2}\right]\\
\text { over all estimators } g(\cdot)
$$

### LMS Estimation w. several measurements

- Unknown r.v. $\Theta$
- Observe values of r.v.'s $X_{1}, \ldots, X_{n}$
- Best estimator: $\mathrm{E}\left[\Theta \mid X_{1}, \ldots, X_{n}\right]$
- Can be hard to compute/implement
	- involves multi-dimensional integrals, etc.

## *Thinking*

- [贝叶斯推断（Bayesian inference）](https://zh.wikipedia.org/wiki/%E8%B4%9D%E5%8F%B6%E6%96%AF%E6%8E%A8%E6%96%AD)
	- “推断统计的一种方法。这种方法使用贝叶斯定理，在有更多证据及信息时，更新特定假设的概率。”
	- 等到具体例子的时候再做笔记

# **<u>L22. Bayesian Statistical Inference II</u>**

## **Linear LMS**

- Consider estimators of $\Theta$, of the form $\hat{\Theta}=a X+b$
- Minimize $\mathbf{E}\left[(\Theta-a X-b)^{2}\right]$
- Best choice of $a, b$; best linear estimator:
  $$
  \hat{\Theta}_{L}=\mathbf{E}[\Theta]+\frac{\operatorname{Cov}(X, \Theta)}{\operatorname{var}(X)}(X-\mathbf{E}[X])
  $$

### Linear LMS properties

$$
\begin{gathered}
\hat{\Theta}_{L}=\mathbf{E}[\Theta]+\frac{\operatorname{Cov}(X, \Theta)}{\operatorname{var}(X)}(X-\mathbf{E}[X]) \\
\mathbf{E}\left[\left(\hat{\Theta}_{L}-\Theta\right)^{2}\right]=\left(1-\rho^{2}\right) \sigma_{\Theta}^{2}
\end{gathered}
$$

### Linear LMS with multiple data

- Consider estimators of the form:
  $$
  \hat{\Theta}=a_{1} X_{1}+\cdots+a_{n} X_{n}+b
  $$
- Find best choices of $a_{1}, \ldots, a_{n}, b$
- Minimize:
  $$
  \mathbf{E}\left[\left(a_{1} X_{1}+\cdots+a_{n} X_{n}+b-\Theta\right)^{2}\right]
  $$
- Set derivatives to zero linear system in $b$ and the $a_{i}$
- Only means, variances, covariances matter

## **Big Picture**

- Standard examples:

  - $X_{i}$ uniform on $[0, \theta] ;$
  	uniform prior on $\theta$

  - $X_{i} \operatorname{Bernoulli}(p)$
  	uniform (or Beta) prior on $p$

  - $X_{i}$ normal with mean $\theta$, known variance $\sigma^{2}$ 
  	normal prior on $\theta$;

  	$X_{i}=\Theta+W_{i}$
- Concepts
	- <u>prior</u>
	- calculate <u>posterior</u> using Bayes Rule
	- calculate estimators
- Estimation methods: (performance checked by MSE (mean square error))
	- MAP
	- LMS
	- Linear LMS

## *Thinking*

- 通过复习课了解了各主题间的关系（Nicely established relations among multiple topics in lecture 21 and 22）
	- 通过贝叶斯定理得到数据更新后的概率
	- 三种不同的estimator的计算及其均方误差MSE
		- MAP 最大后验
			- MSE较大
		- LMS 最小均方误差
			- MSE最小
			- 多个测量的计算包含多维积分，较难计算
		- Linear LMS 线性最小均方误差
			- MSE接近LMS
			- 多个测量的计算较容易，微分为0得出线性方程组，且只需考虑均值，方差，协方差，而不需要知道具体分布



# <u>**L23. Classical Statistical Inference - I**</u>

## **Classical Statistics**

<img src="image.assets/Screen Shot 2021-11-25 at 14.19.29.png" alt="Screen Shot 2021-11-25 at 14.19.29" style="zoom: 50%;" />

- also for vectors $X$ and $\theta$:
  $p_{X_{1}, \ldots, X_{n}}\left(x_{1}, \ldots, x_{n} ; \theta_{1}, \ldots, \theta_{m}\right)$
- These are NOT conditional probabilities;
  $\theta$ is NOT random
  - mathematically: many models, one for each possible value of $\theta$
- Problem types:
  - Hypothesis testing:
    $H_{0}: \theta=1 / 2$ versus $H_{1}: \theta=3 / 4$
  - Composite hypotheses:
    $H_{0}: \theta=1 / 2$ versus $H_{1}: \theta \neq 1 / 2$
  - Estimation: design an estimator $\hat{\Theta}$, to keep estimation error $\hat{\Theta}-\theta$ small

## **Maximum Likelihood Estimation**

- Model, with unknown parameter(s): $X \sim p_{X}(x ; \theta)$
- Pick $\theta$ that "makes data most likely" 
  $$
  \widehat{\theta}_{\mathrm{ML}}=\arg \max _{\theta} p_{X}(x ; \theta)
  $$

  ## **Desirable properties of estimators**

  - Unbiased: $\mathbf{E}\left[\widehat{\Theta}_{n}\right]=\theta$
  - Consistent: $\hat{\Theta}_{n} \rightarrow \theta$ (in probability)
  - "Small" mean squared error (MSE)
  	$$
    \begin{aligned}
    \mathrm{E}\left[(\hat{\Theta}-\theta)^{2}\right] &=\operatorname{var}(\hat{\Theta}-\theta)+(\mathrm{E}[\hat{\Theta}-\theta])^{2} \\
    &=\operatorname{var}(\hat{\Theta})+(\text { bias })^{2}
    \end{aligned}
    $$

## **Estimate a mean**

- $X_{1}, \ldots, X_{n}$ : i.i.d., mean $\theta$, variance $\sigma^{2}$ 
$X_{i}=\theta+W_{i}$
$W_{i}$ : i.i.d., mean, 0, variance $\sigma^{2}$
$\hat{\Theta}_{n}=$ sample mean $=M_{n}=\frac{X_{1}+\cdots+X_{n}}{n}$
- Properties:
- $\mathbf{E}\left[\hat{\Theta}_{n}\right]=\theta \quad$ (unbiased)
- WLLN: $\hat{\Theta}_{n} \rightarrow \theta \quad$ (consistency)
- MSE: $\sigma^{2} / n$
- Sample mean often turns out to also be the $M L$ estimate.
  E.g., if $X_{i} \sim N\left(\theta, \sigma^{2}\right)$, i.i.d.

## **Confidence intervals (CIs)**

- An $1-\alpha$ confidence interval is a (random) interval $\left[\hat{\Theta}_{n}^{-}, \hat{\Theta}_{n}^{+}\right]$,
  s.t. $\quad \mathbf{P}\left(\hat{\Theta}_{n}^{-} \leq \theta \leq \hat{\Theta}_{n}^{+}\right) \geq 1-\alpha, \quad \forall \theta$
  - often $\alpha=0.05$, or $0.25$, or $0.01$
  - interpretation is subtle
- CI in estimation of the mean
  $$
  \hat{\Theta}_{n}=\left(X_{1}+\cdots+X_{n}\right) / n
  $$
  - normal tables: $\Phi(1.96)=1-0.05 / 2$
  $$
  \begin{gathered}
  \mathbf{P}\left(\frac{\left|\hat{\Theta}_{n}-\theta\right|}{\sigma / \sqrt{n}} \leq 1.96\right) \approx 0.95 \quad(\mathrm{CLT}) \\
  \mathbf{P}\left(\hat{\Theta}_{n}-\frac{1.96 \sigma}{\sqrt{n}} \leq \theta \leq \hat{\Theta}_{n}+\frac{1.96 \sigma}{\sqrt{n}}\right) \approx 0.95
  \end{gathered}
  $$
- More generally: let $z$ be s.t. $\Phi(z)=1-\alpha / 2$
  $$
  \mathbf{P}\left(\hat{\Theta}_{n}-\frac{z \sigma}{\sqrt{n}} \leq \theta \leq \widehat{\Theta}_{n}+\frac{z \sigma}{\sqrt{n}}\right) \approx 1-\alpha
  $$

### The case of unknown $\sigma$

- Option 1: use upper bound on $\sigma$
  - if $X_{i}$ Bernoulli: $\sigma \leq 1 / 2$
- Option 2: use ad hoc estimate of $\sigma$
  - if $X_{i} \operatorname{Bernoulli}(\theta): \widehat{\sigma}=\sqrt{\hat{\Theta}(1-\widehat{\Theta})}$
- Option 3: Use generic estimate of the variance
  - Start from $\sigma^{2}=\mathbf{E}\left[\left(X_{i}-\theta\right)^{2}\right]$
    $$
    \widehat{\sigma}_{n}^{2}=\frac{1}{n} \sum_{i=1}^{n}\left(X_{i}-\theta\right)^{2} \rightarrow \sigma^{2}
    $$
    (but do not know $\theta$ )
    $$
    \widehat{S}_{n}^{2}=\frac{1}{n-1} \sum_{i=1}^{n}\left(X_{i}-\widehat{\Theta}_{n}\right)^{2} \rightarrow \sigma^{2}
    $$
    (unbiased: $\mathbf{E}\left[\widehat{S}_{n}^{2}\right]=\sigma^{2}$ )

## *Thinking*

- 经典统计推断 Classical Statistical Inference
  - 需要推断的未知数据 $\theta$
  - 与该数据相关的测试数据 $X$ 及其概率质量方程 $p_X(x;\theta)$
  - 以此通过estimator推断 $\theta$ 的值及其置信区间（confidence intervals CI）
    - 最常用也是最易理解的方法即样本均值 sample mean
- 概念上十分简单，即没有对未知数据的知识，通过测试数据推断该未知数据，那么样本数量足够大时其平均值即为很好的推测
  - 但从数学和逻辑符号系统推导出该结论却并不一定简单





















