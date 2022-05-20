# ***Unit II: General Random Variables***

# <u>L8. Continuous Random Variables</u>

## **Continuous r.v. and Probability Density Functions $f_X$**

$$
\mathbf{P} (a \leq X \leq b)=\int_{a}^{b} f_{X}(x) d x \\\\
f_X(x) = \lim_{\delta \to 0} {\mathbf{P}(x\leq X\leq x+\delta)\over \delta}
$$

- $\mathbf{P} (X = a)= 0$
- $\int_{-\infty}^{\infty} f_{X}(x) d x=1$
- $\mathbf{P}(x \leq X \leq x+\delta)=\int_{x}^{x+\delta} f_{X}(s) d s \approx f_{X}(x) \cdot \delta$
- $\mathbf{P}(X \in B)=\int_{B} f_{X}(x) d x, $  for "nice" sets $B$

### Means and variances

$$
\mathbf{E}[X]=\int_{-\infty}^{\infty} x f_{X}(x) d x
$$

$$
\operatorname{var}(X)=\sigma_{X}^{2}=\int_{-\infty}^{\infty}(x-\mathbf{E}[X])^{2} f_{X}(x)dx = \mathbf{E}[X^2]-(\mathbf{E}[X])^2
$$

- $\mathbf{E}[g(X)]=\int_{-\infty}^{\infty} g(x) f_{X}(x) d x$

### Continuous Uniform r.v.

<img src="image.assets/Screen Shot 2021-11-10 at 10.11.19.png" alt="Screen Shot 2021-11-10 at 10.11.19" style="zoom: 33%;" />

- $f_X(x)=\frac{1}{b-a}, a \leq x \leq b$
- $\mathbf{E}[X]=\int_{a}^{b} x \cdot \frac{1}{b-a} d x=\frac{a+b}{2}$
- $\sigma_X^2=\int_{a}^{b}\left(x-\frac{a+b}{2}\right)^{2} \frac{1}{b-a} d x=\frac{(b-a)^{2}}{12}$
	- $\sigma_{X}=\frac{b-a}{\sqrt{12}}$

## **Cumulative distribution function (CDF)**

<img src="image.assets/Screen Shot 2021-11-10 at 10.23.26.png" alt="Screen Shot 2021-11-10 at 10.23.26" style="zoom:33%;" />
$$
F_{X}(x)=\mathrm{P}(X \leq x)=\int_{-\infty}^{x} f_{X}(t) d t
$$

$$
\frac{d F_{X}}{d x}(x)=f_{X}(x)
$$

### Discrete r.v.

<img src="image.assets/Screen Shot 2021-11-10 at 10.24.09.png" alt="Screen Shot 2021-11-10 at 10.24.09" style="zoom:33%;" />
$$
F_{X}(x)=\mathbf{P}(X \leq x)=\sum_{k \leq x} p_{X}(k)
$$

$$
p_{X}(k)=F_{X}(k)-F_{X}(k-1)
$$

### Mixed distributions

- Schematic drawing of a combination of a PDF and a PMF

<img src="image.assets/Screen Shot 2021-11-10 at 10.31.53.png" alt="Screen Shot 2021-11-10 at 10.31.53" style="zoom:33%;" />

- The corresponding CDF:

<img src="image.assets/Screen Shot 2021-11-10 at 10.32.32.png" alt="Screen Shot 2021-11-10 at 10.32.32" style="zoom:33%;" />

## **Gaussian (normal) PDF**

<img src="image.assets/Screen Shot 2021-11-10 at 10.38.54.png" alt="Screen Shot 2021-11-10 at 10.38.54" style="zoom:33%;" />
$$
\text { Standard normal } N(0,1): f_{X}(x)=\frac{1}{\sqrt{2 \pi}} e^{-x^{2} / 2} \\
\mathbf{E}[X]=0 \quad \operatorname{var}(X)=1
$$

$$
\text { General normal } N\left(\mu, \sigma^{2}\right): f_{X}(x)=\frac{1}{\sigma \sqrt{2 \pi}} e^{-(x-\mu)^{2} / 2 \sigma^{2}} \\
\mathbf{E}[X]=\mu \quad \operatorname{Var}(X)=\sigma^{2}
$$

### Normal CDF

- No closed form available for CDF
	- but there are tables (for standard normal)
	
	- CDF of standard normal RV Y at y: $\Phi(y)$
	
		- given in tables for $y \geq 0$
		- for $y<0$, use the result: $\Phi(y)=1-\Phi(-y)$
	
	- To evaluate CDF of a general standard normal, express it as a function of a standard normal:
		$$
		\begin{gathered}
		X \sim N\left(\mu, \sigma^{2}\right) \Leftrightarrow \frac{X-\mu}{\sigma} \sim N(0,1) \\
		P(X \leq x)=P\left(\frac{X-\mu}{\sigma} \leq \frac{x-\mu}{\sigma}\right)=\Phi\left(\frac{x-\mu}{\sigma}\right)
		\end{gathered}
		$$

**The constellation of concepts**
$$
\begin{array}{rcl}
p_{X}(x) & & f_{X}(x) \\
& F_{X}(x) & \\
\sum_{x} x p_{X}(x) & \mathbf{E}[X] & \int x f_{X}(x) d x \\
& \operatorname{var}(x) & \\
p_{X, Y}(x, y) & & f_{X, Y}(x, y) \\
p_{X \mid A}(x) & & f_{X \mid A}(x) \\
p_{X \mid Y}(x \mid y) & & f_{X \mid Y}(x \mid y)
\end{array}
$$

## *Thinking*

- 连续随机变量
  - 概率密度函数（对应概率质量函数）$p_X \to f_X$
  - 求和变积分 $\sum \to \int$
- 累计分布函数 CDF
	- 概率密度函数的积分 $F_{X}(x)=\mathrm{P}(X \leq x)$

# <u>L9. Multiple Continuous Random Variables</u>

<img src="image.assets/Screen Shot 2021-11-10 at 11.55.11.png" alt="Screen Shot 2021-11-10 at 11.55.11" style="zoom:33%;" />

## **Joint PDF $f_{X, Y}(x, y)$**

$$
\mathbf{P}((X, Y) \in S)=\iint_{S} f_{X, Y}(x, y) d x d y
$$
- Interpretation:
  $$
  \mathbf{P}(x \leq X \leq x+\delta, y \leq Y \leq y+\delta) \approx f_{X, Y}(x, y) \cdot \delta^{2}
  $$
- Marginal PDF:
	$$
	f_{X}(x)=\int_{-\infty}^{\infty} f_{X, Y}(x, y) d y
	$$
- Expectations:
  $$
  \mathbf{E}[g(X, Y)]=\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y) f_{X, Y}(x, y) d x d y
  $$
- $X$ and $Y$ are called independent if
  $$
  f_{X, Y}(x, y)=f_{X}(x) f_{Y}(y), \quad \text{for all }x, y
  $$
  - $E[X Y]=E[X] E[Y]$
  - $g(X)$ and $h(Y)$ are independent
  - $E[g(X) h(Y)]=E[g(X)] E[h(Y)]$

## **Conditioning**

- Recall
  $$
  \mathbf{P}(x \leq X \leq x+\delta) \approx f_{X}(x) \cdot \delta
  $$
- By analogy, would like:
  $$
  \mathbf{P}(x \leq X \leq x+\delta \mid Y \approx y) \approx f_{X \mid Y}(x \mid y) \cdot \delta
  $$
- This leads us to the definition:
  $$
  f_{X \mid Y}(x \mid y)=\frac{f_{X, Y}(x, y)}{f_{Y}(y)} \quad \text { if } f_{Y}(y)>0
  $$
- For given $y$, conditional PDF is a (normalized) "section" of the joint PDF
- If independent, $f_{X, Y}=f_{X} f_{Y}$, we obtain 
  $$
  f_{X \mid Y}(x \mid y)=f_{X}(x)
  $$

### Total Expectation Theorem

$$
\begin{aligned}
E[X] &=\int_{-\infty}^{\infty} E[X \mid Y=y] f_{Y}(y) d y \\
E[g(X)] &=\int_{-\infty}^{\infty} E[g(X) \mid Y=y] f_{Y}(y) d y \\
E[g(X, Y)] &=\int_{-\infty}^{\infty} E[g(X, Y) \mid Y=y] f_{Y}(y) d y
\end{aligned}
$$

## *Thinking*

- 多元连续随机变量
  - 和多元离散随机变量公式类似，理解稍有不同
  - 体积的切面

- 总结
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
	

# <u>L10. Continuous Bayes' Rule; Derived Distributions</u>

## **The Bayes variations**

### Discrete

$$
\begin{gathered}
p_{X \mid Y}(x \mid y)\cdot p_{Y}(y) = p_{X, Y}(x, y) =   p_{Y \mid X}(y \mid x)\cdot p_{X}(x)\\
\downarrow\\
p_{X \mid Y}(x \mid y)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)}=\frac{p_{X}(x) p_{Y \mid X}(y \mid x)}{p_{Y}(y)} \\
\text{where }\quad p_{Y}(y)=\sum_{x} p_{X}(x) p_{Y \mid X}(y \mid x)
\end{gathered}
$$

- Example
	- $X = 1, 0$: airplane present/not present
	- $Y = 1, 0$: something did/did not register on radar

### Continuous counterpart

$$
\begin{gathered}
f_{X \mid Y}(x \mid y) =\frac{f_{X, Y}(x, y)}{f_{Y}(y)}=\frac{f_{X}(x) f_{Y \mid X}(y \mid x)}{f_{Y}(y)} \\
f_{Y}(y) =\int_{x} f_{X}(x) f_{Y \mid X}(y \mid x) d x
\end{gathered}
$$

- Example
	- $X$ : some signal; "prior" $f_{X}(x)$ 
	- $Y$ : noisy version of $X$ 
	- $f_{Y \mid X}(y \mid x):$ model of the noise

### Discrete $X$, Continuous $Y$

$$
\begin{gathered}
p_{X \mid Y}(x \mid y)=\frac{p_{X}(x) f_{Y \mid X}(y \mid x)}{f_{Y}(y)} \\
f_{Y}(y)=\sum_{x} p_{X}(x) f_{Y \mid X}(y \mid x)
\end{gathered}
$$

- Example
	- $X:$ a discrete signal; "prior" $p_{X}(x)$
	- $Y$ : noisy version of $X$
	- $f_{Y \mid X}(y \mid x)$ : continuous noise model

### Continuous $X$, Discrete $Y$

$$
\begin{aligned}
&f_{X \mid Y}(x \mid y)=\frac{f_{X}(x) p_{Y \mid X}(y \mid x)}{p_{Y}(y)} \\
&p_{Y}(y)=\int_{x} f_{X}(x) p_{Y \mid X}(y \mid x) d x
\end{aligned}
$$
- Example:

	- $X:$ a continuous signal; "prior" $f_{X}(x)$ (e.g., intensity of light beam);

	- $Y$ : discrete r.v. affected by $X$ (e.g., photon count)

	- $p_{Y \mid X}(y \mid x):$ model of the discrete r.v.

## **Derived Distribution**

### Definition

- It is a PMF or PDF of a function of one or more random variables with known probability law

  - Obtaining the PDF for
    $$
    g(X, Y)=Y / X
    $$
    involves deriving a distribution.
    Note: $g(X, Y)$ is a random variable

### Methodology

- Discrete

	- Obtain probability mass for each possible value of $Y=g(X)$

	$$
	\begin{aligned}
	p_{Y}(y) &=\mathbf{P}(g(X)=y) \\
	&=\sum_{x: g(x)=y} p_{X}(x)
	\end{aligned}
	$$

- Continuous

	- Two-step procedure:
		- Get CDF of $Y: \quad F_{Y}(y)=\mathbf{P}(Y \leq y)$
		- Differentiate to get

	$$
	f_{Y}(y)=\frac{d F_{Y}}{d y}(y)
	$$

### Example

- $X:$ uniform on $[0,2]$
- Find PDF of $Y=X^{3}$
- Solution:

$$
\begin{aligned}
F_{Y}(y) &=\mathbf{P}(Y \leq y)=\mathbf{P}\left(X^{3} \leq y\right) \\
&=\mathbf{P}\left(X \leq y^{1 / 3}\right)=\frac{1}{2} y^{1 / 3} \\
f_{Y} &(y)=\frac{d F_{Y}}{d y}(y)=\frac{1}{6 y^{2 / 3}}
\end{aligned}
$$

### The pdf of $Y=a X+b$

$$
Y=2 X+5
$$
<img src="image.assets/Screen Shot 2021-11-12 at 09.49.10.png" alt="Screen Shot 2021-11-12 at 09.49.10" style="zoom:33%;" />
$$
F_Y(y) = \mathbf{P}(2x+5<y) = \mathbf{P}(x<{y-5\over 2}) = F_X({y-5\over 2}) \\
\text{take derivatives on both sidees} \\
\downarrow \\
f_y(y) = {1\over 2} f_X({y-5\over 2}) \\
\downarrow
$$

$$
f_{Y}(y)=\frac{1}{|a|} f_{X}\left(\frac{y-b}{a}\right)
$$
## *Thinking*

- 贝叶斯定理的变体
	- 连续，连续和离散的混合
- 导出分布 derived distribution
	- 先求新的r.v.的累积分布函数CDF，其导数即为新的r.v.的概率密度函数PDF




# <u>L11. Derived Distributions (cont.); Covariance</u>

## **Derived Distributions (cont.)**

### A general formula

- Let $Y=g(X)$
  $g$ strictly monotonic.

  <img src="image.assets/Screen Shot 2021-11-12 at 11.30.22.png" alt="Screen Shot 2021-11-12 at 11.30.22" style="zoom: 50%;" />

- Event $x \leq X \leq x+\delta$ is the same as $g(x) \leq Y \leq g(x+\delta)$ or (approximately)
  $$
  g(x) \leq Y \leq g(x)+\delta|(d g / d x)(x)|
  $$
- Hence,
  $$
  \delta f_{X}(x)=\delta f_{Y}(y)\left|\frac{d g}{d x}(x)\right|
  $$
  where $y=g(x)$

### Convolution: the distribution of $X + Y;X, Y$ independent

- $W=X+Y$
  $$
  \begin{aligned}
  p_{W}(w) &=\mathbf{P}(X+Y=w) \\
  &=\sum_{x} \mathbf{P}(X=x) \mathbf{P}(Y=w-x) \\
  &=\sum_{x} p_{X}(x) p_{Y}(w-x)
  \end{aligned}
  $$
- The continuous case
  $$
  \begin{array}{rcl}
  f_{W \mid X}(w \mid x)&=&f_{Y}(w-x) \\\\
  f_{W, X}(w, x)&=&f_{X}(x) f_{W \mid X}(w \mid x) \\
  &=&f_{X}(x) f_{Y}(w-x) \\\\
  f_{W}(w)&=&\int_{-\infty}^{\infty} f_{X}(x) f_{Y}(w-x) d x
  \end{array}
  $$

### Two independent normal r.v.s

- $X \sim N\left(\mu_{x}, \sigma_{x}^{2}\right), Y \sim N\left(\mu_{y}, \sigma_{y}^{2}\right)$, independent
  $$
  \begin{aligned}
  f_{X, Y}(x, y) &=f_{X}(x) f_{Y}(y) \\
  &=\frac{1}{2 \pi \sigma_{x} \sigma_{y}} \exp \left\{-\frac{\left(x-\mu_{x}\right)^{2}}{2 \sigma_{x}^{2}}-\frac{\left(y-\mu_{y}\right)^{2}}{2 \sigma_{y}^{2}}\right\}
  \end{aligned}
  $$
- PDF is constant on the ellipse where
  $$
  \frac{\left(x-\mu_{x}\right)^{2}}{2 \sigma_{x}^{2}}+\frac{\left(y-\mu_{y}\right)^{2}}{2 \sigma_{y}^{2}}
  $$
  is constant
- Ellipse is a circle when $\sigma_{x}=\sigma_{y}$

### The sum of independent normal r.v.’s

- $X \sim N\left(0, \sigma_{x}^{2}\right), Y \sim N\left(0, \sigma_{y}^{2}\right)$, independent
- Let $W=X+Y$
  $$
  \begin{aligned}
  f_{W}(w) &=\int_{-\infty}^{\infty} f_{X}(x) f_{Y}(w-x) d x \\
  &=\frac{1}{2 \pi \sigma_{x} \sigma_{y}} \int_{-\infty}^{\infty} e^{-x^{2} / 2 \sigma_{x}^{2}} e^{-(w-x)^{2} / 2 \sigma_{y}^{2}} d x \\
  \text { (algebra) } &=c e^{-\gamma w^{2}}
  \end{aligned}
  $$
- Conclusion: $W$ is normal
  - $\operatorname{mean}=0, \operatorname{variance}=\sigma_{x}^{2}+\sigma_{y}^{2}$
  - same argument for nonzero mean case

## **Covariance**

- $\operatorname{cov}(X, Y)=\mathbf{E}[(X-\mathbf{E}[X]) \cdot(Y-\mathbf{E}[Y])]$
	- Zero-mean case: $\operatorname{cov}(X, Y)=\mathbf{E}[X Y]$
	- $\operatorname{cov}(X, Y)=\mathbf{E}[X Y]-\mathbf{E}[X] \mathbf{E}[Y]$
	- $\operatorname{var}\left(\sum_{i=1}^{n} X_{i}\right)=\sum_{i=1}^{n} \operatorname{var}\left(X_{i}\right)+ \sum_{(i, j): i \neq j} \operatorname{cov}\left(X_{i}, X_{j}\right)$
	- independent $\Rightarrow \operatorname{cov}(X, Y)=0$ (converse is not true)

### Correlation coefficient

- Dimensionless version of covariance:
  $$
  \begin{aligned}
  \rho &=\mathbf{E}\left[\frac{(X-\mathbf{E}[X])}{\sigma_{X}} \cdot \frac{(Y-\mathbf{E}[Y])}{\sigma_{Y}}\right] \\
  &=\frac{\operatorname{cov}(X, Y)}{\sigma_{X} \sigma_{Y}}
  \end{aligned}
  $$
- $-1 \leq \rho \leq 1$
- $|\rho|=1 \quad \Leftrightarrow \quad(X-\mathbf{E}[X])=c(Y-\mathbf{E}[Y])$ (linearly related)
- Independent $\Rightarrow \rho=0$ (converse is not true)

## *Thinking*

- 导出分布
	- 导出函数 $g$ 的导数：若 $Y=g(X)$ ，且 $g$ 是严格单调的，则 $f_Y(y) = {1\over g'(x)}f_X(x)$
	- 多元导出分布
		- 正态多元导出分布
- 协方差 Covariance $\operatorname{cov}(X, Y)=\mathbf{E}[(X-\mathbf{E}[X]) \cdot(Y-\mathbf{E}[Y])]$
	- 衡量两个随机变量的联合变化程度
	- 相关系数 Correlation Coefficient $\rho =\mathbf{E}\left[\frac{(X-\mathbf{E}[X])}{\sigma_{X}} \cdot \frac{(Y-\mathbf{E}[Y])}{\sigma_{Y}}\right] =\frac{\operatorname{cov}(X, Y)}{\sigma_{X} \sigma_{Y}}\quad \in[-1,1]$
		- 标准化的（normalized）两个随机变量之间的关系，无单位



# <u>L12. Iterated Expectations</u>

## **Conditional expectations $\mathbf{E}[X|Y]$**

- Given the value $y$ of a r.v. $Y$ :
  $$
  \mathbf{E}[X \mid Y=y]=\sum_{x} x p_{X \mid Y}(x \mid y)
  $$
  (integral in continuous case)
- $\mathbf{E}[X|Y]$ is a r.v. as a function of $Y$

### Law of iterated expectations

$$
\mathbf{E}[\mathbf{E}[X \mid Y]]=\sum_{y} \mathbf{E}[X \mid Y=y] p_{Y}(y)=\mathbf{E}[X]
$$

## **$\operatorname{var}(X \mid Y)$ and its expectation**

- $\operatorname{var}(X \mid Y=y)=\mathbf{E}\left[(X-\mathbf{E}[X \mid Y=y])^{2} \mid Y=y\right]$
- $\operatorname{var}(X \mid Y):$ a r.v. with value $\operatorname{var}(X \mid Y=y)$ when $Y=y$
	- a r.v. as a function of $Y$


### Law of total variance

$$
\operatorname{var}(X)=\mathrm{E}[\operatorname{var}(X \mid Y)]+\operatorname{var}(\mathrm{E}[X \mid Y])
$$

- Proof
	1. Recall: $\operatorname{var}(X)=\mathbf{E}\left[X^{2}\right]-(\mathbf{E}[X])^{2}$
	2. $\operatorname{var}(X \mid Y)=\mathbf{E}\left[X^{2} \mid Y\right]-(\mathbf{E}[X \mid Y])^{2}$
	3. $\mathbf{E}[\operatorname{var}(X \mid Y)]=\mathbf{E}\left[X^{2}\right]-\mathbf{E}\left[(\mathbf{E}[X \mid Y])^{2}\right]$
	4. $\operatorname{var}(\mathbf{E}[X \mid Y])=\mathbf{E}\left[(\mathbf{E}[X \mid Y])^{2}\right]-(\mathbf{E}[X])^{2}$
	5. Sum of right-hand sides of (3), (4):
		$\mathbf{E}\left[X^{2}\right]-(\mathbf{E}[X])^{2}=\operatorname{var}(X)$

## **Examples**

- Section means and variances
	- see notes

- Sum of a random number of independent r.v.’s
	- see notes


## *Thinking*

- 条件期望值和条件方差
	- 迭代期望值定理 Law of Iterated Expectation
	- 全方差定理 Law of Total Variance



































