# **Unit I: Probability Models And Discrete Random Variables**

# <u>**L1. Probability Models and Axioms**</u>

## **Sample space $\Omega$**

- "List" (set) of possible outcomes
- List must be:
	- Mutually exclusive
	- Collectively exhaustive
- Art: to be at the "right" granularity

### Sample space vs. sequential description

-     ​	<img src="image.assets/Screen Shot 2021-10-27 at 11.18.19.png" alt="Screen Shot 2021-10-27 at 11.18.19" style="zoom: 33%;" />

## **Probability axioms**

### Axioms

1. Nonnegativity: $\mathbf{P}(A) \geq 0$
2. Normalization: $\mathbf{P}(\Omega)=1$
3. Additivity: If $A \cap B=\varnothing$, then $\mathbf{P}(A \cup B)=\mathbf{P}(A)+$ $\mathbf{P}(B)$
	- If $A_{1}, A_{2}, \ldots$ are disjoint events, then: $\mathbf{P}\left(A_{1} \cup A_{2} \cup \cdots\right)=\mathbf{P}\left(A_{1}\right)+\mathbf{P}\left(A_{2}\right)+\cdots$

### Discrete uniform law

- Let all outcomes be equally likely
- Then,

$$
\mathbf{P}(A)=\frac{\text { number of elements of } A}{\text { total number of sample points }}
$$

### Continuous uniform law

- Uniform law: Probability = Area

## *Thinking*

- 概率论的基本概念和公理
	- 艺术：相关因素的选择（如天气是否影响掷骰子）

# <u>**L2. Conditioning and Bayes' Rule**</u>

## **Conditional probability**

-     ​	<img src="image.assets/Screen Shot 2021-10-27 at 12.17.34.png" alt="Screen Shot 2021-10-27 at 12.17.34" style="zoom:33%;" />
	
- $\mathbf{P}(A \mid B)=$ probability of $A$, given that $B$ occurred
	
	- $B$ is our new universe
	
- Definition: Assuming $\mathbf{P}(B) \neq 0$,
  $$
  \mathbf{P}(A \mid B)=\frac{\mathbf{P}(A \cap B)}{\mathbf{P}(B)}
  $$
	- $\mathbf{P}(A \mid B)$ undefined if $\mathbf{P}(B)=0$

### Multiplication Rule

- $\mathbf{P}(A \cap B \cap C) = \mathbf{P}(A \cap B) \cdot \mathbf{P}(C \mid A \cap B) =  \mathbf{P}(A) \cdot \mathbf{P}(B \mid A) \cdot \mathbf{P}(C \mid A \cap B)$

### Total probability theorem

-     ​	<img src="image.assets/Screen Shot 2021-10-27 at 12.17.57.png" alt="Screen Shot 2021-10-27 at 12.17.57" style="zoom:33%;" />
- Partition of sample space into $A_{1}, A_{2}, A_{3}$
- Have $\mathbf{P}\left(B \mid A_{i}\right)$, for every $i$
- One way of computing $\mathbf{P}(B):$

$$
\begin{aligned}
\mathbf{P}(B)=& \mathbf{P}\left(A_{1}\right) \mathbf{P}\left(B \mid A_{1}\right) \\
&+\quad \mathbf{P}\left(A_{2}\right) \mathbf{P}\left(B \mid A_{2}\right) \\
&+\quad \mathbf{P}\left(A_{3}\right) \mathbf{P}\left(B \mid A_{3}\right)
\end{aligned}
$$

## **Bayes’ rule**

- "Prior" probabilities $\mathbf{P}\left(A_{i}\right)$
	- initial "beliefs"
- We know $\mathbf{P}\left(B \mid A_{i}\right)$ for each $i$
- Wish to compute $\mathbf{P}\left(A_{i} \mid B\right)$
	- revise "beliefs", given that $B$ occurred

$$
\begin{aligned}
\mathbf{P}\left(A_{i} \mid B\right) &=\frac{\mathbf{P}\left(A_{i} \cap B\right)}{\mathbf{P}(B)} \\
&=\frac{\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(B \mid A_{i}\right)}{\mathbf{P}(B)} \\
&=\frac{\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(B \mid A_{i}\right)}{\sum_{j} \mathbf{P}\left(A_{j}\right) \mathbf{P}\left(B \mid A_{j}\right)}
\end{aligned}
$$



## *Thinking*

- 条件概率
	- 问题：有一个初始概率，给予一个条件，概率的变化
	- 需要知道给予条件的概率，以及初始事件发生的情况下给予条件的概率
- 常见问题：灵敏度高的器材对低发生率事件发生的判断准确率低
	- 如：疾病判断，雷达判断
		- $P(A | B) = {P(A\cap B)\over P(B)} = {P(A)P(B|A)\over P(A)P(B|A) + P(A^C)P(B|A^C)}$
		- 若 $P(A)$ （事件发生）低时，即使器材的 $P(B|A)$ （事件发生时，判断发生）高且 $P(B|A^C)$ （事件未发生时，判断发生）低，也会有低的 $P(A|B)$ （判断发生时，事件发生）

# <u>**L3. Independence**</u>

## **Independence of two events**

- "Defn:" $\mathbf{P}(B \mid A)=\mathbf{P}(B)$
	- "occurrence of $A$ provides no information about $B$ 's occurrence"
- Recall that $\mathbf{P}(A \cap B)=\mathbf{P}(A) \cdot \mathbf{P}(B \mid A)$
- Defn: $\mathbf{P}(A \cap B)=\mathbf{P}(A) \cdot \mathbf{P}(B)$

### Conditioning may affect independence

- Conditional independence, given $C$, is defined as independence under probability law 
	$\mathbf{P}(A \cap B \mid C) = \mathbf{P}(A \mid C) \cdot \mathbf{P}(B \mid C)$
- Conditional dependence:  <img src="image.assets/Screen Shot 2021-10-27 at 14.17.02.png" alt="Screen Shot 2021-10-27 at 14.17.02" style="zoom:33%;" />

### Independence of a collection of events

- $\mathbf{P}\left(A_{i} \cap A_{j} \cap \cdots \cap A_{q}\right)=\mathbf{P}\left(A_{i}\right) \mathbf{P}\left(A_{j}\right) \cdots \mathbf{P}\left(A_{q}\right)$

	for any distinct indices $i, j, \ldots, q$, (chosen from $\{1, \ldots, n\}$ )

## **The King's sibling**

- The king comes from a family of two children. What is the probability that his sibling is female?

## *Thinking*

- 独立
	- 另一事件的发生不影响该事件的概率
		- 注意：并非样本空间中两个不相交的区域，事实上它们必然不独立
		- $\mathbf{P}(A \cap B)=\mathbf{P}(A) \cdot \mathbf{P}(B)$
	- 国王的一个兄弟姐妹的性别问题
		- 有一些隐性的前提条件，如
			- 王室决定只生两个
			- 王室决定生到出现男婴为止
			- 国王会杀死他的所有兄弟

# <u>**L4. Counting**</u>

## **Discrete uniform law**

- Let all sample points be equally likely
- Then,

$$
\mathbf{P}(A)=\frac{\text { number of elements of } A}{\text { total number of sample points }}=\frac{|A|}{|\Omega|}
$$

## **Combinations**

- $\left(\begin{array}{l}n \\ k\end{array}\right):$ number of $k$-element subsets of a given $n$-element set
- Two ways of constructing an ordered sequence of $k$ distinct items:
	- Choose the $k$ items one at a time: $n(n-1) \cdots(n-k+1)=\frac{n !}{(n-k) !}$ choices
	- Choose $k$ items, then order them ( $k !$ possible orders)
- Hence:

$$
\begin{aligned}
&\left(\begin{array}{l}
n \\
k
\end{array}\right) \cdot k !=\frac{n !}{(n-k) !} \\
&\left(\begin{array}{l}
n \\
k
\end{array}\right)=\frac{n !}{k !(n-k) !}
\end{aligned}
$$

- $\sum_{k=0}^{n}\left(\begin{array}{l}n \\ k\end{array}\right)= \text{total number of subsets} =2^n$

## **Binomial probabilities**

- $n$ independent coin tosses
	- $\mathbf{P}(H)=p$

$$
\begin{align}
\mathbf{P}(k \text { heads })&=\sum_{k\text { - head seq. }} \mathbf{P}(\text { seq. }) \\
&=(\# \text { of } k \text { - head seqs. }) \cdot p^{k}(1-p)^{n-k} \\
&=\left(\begin{array}{l}
n \\
k
\end{array}\right) p^{k}(1-p)^{n-k}
\end{align}
$$

## *Thinking*

- 计数
	- 针对离散均匀概率问题
		- $\mathbf{P}(A)=\frac{\text { number of elements of } A}{\text { total number of sample points }}=\frac{|A|}{|\Omega|}$
	- 使用组合公式进行计数从而得出结果
		- $\left(\begin{array}{l}
			n \\
			k
			\end{array}\right)=\frac{n !}{k !(n-k) !}$

# <u>**L5. Discrete Random Variables I**</u>

## **Random variables**

- An assignment of a value (number) to every possible outcome
- Mathematically: A function from the sample space $\Omega$ to the real numbers
	- discrete or continuous values
- Notation:
  - random variable $X$: function $\Omega\to \mathbb{R}$
  - numerical value $x \in \mathbb{R}$

### Probability mass function (PMF)

- ("probability law", "probability distribution" of $X$ )
- Notation: 
	- $\begin{aligned}
		p_{X}(x) &=\mathbf{P}(X=x) \\
		&=\mathbf{P}(\{\omega \in \Omega \text { s.t. } X(\omega)=x\})
		\end{aligned}$
- $p_{X}(x) \geq 0 \quad \sum_{x} p_{X}(x)=1$
## **Expectation**

- Definition:
	- $\mathbf{E}[X]=\sum_{x} x p_{X}(x)$
- Interpretations:
	- Center of gravity of PMF
	- Average in large number of repetitions of the experiment
### Properties of expectations

- Let $X$ be a r.v. and let $Y=g(X)$
$-$ Hard: $\mathbf{E}[Y]=\sum_{y} y p_{Y}(y)$
- Easy: $\mathbf{E}[Y]=\sum_{x} g(x) p_{X}(x)$
- Caution: In general, $\mathbf{E}[g(X)] \neq g(\mathbf{E}[X])$
	- equal if $g$ is linear

### Variance

- Second moment: $\mathbf{E}\left[X^{2}\right]=\sum_{x} x^{2} p_{X}(x)$
- Variance
	- $\begin{aligned}
		\operatorname{var}(X) &=\mathbf{E}\left[(X-\mathbf{E}[X])^{2}\right] \\
		&=\sum_{x}(x-\mathbf{E}[X])^{2} p_{X}(x) \\
		&=\mathbf{E}\left[X^{2}\right]-(\mathbf{E}[X])^{2}
		\end{aligned}$
- Properties:
	- $\operatorname{var}(X) \geq 0$
	- $\operatorname{var}(\alpha X+\beta)=\alpha^{2} \operatorname{var}(X)$
- Standard deviation: $\sigma_{X}=\sqrt{\operatorname{var}(X)}$  (same unit as random variable)

## *Thinking*

- 随机变量：及其概率质量函数，期望值，和方差
	- 随机变量：将样本空间投影到实数值的函数
		- $X$: function $\Omega\to \mathbb{R}$
	- 概率质量函数：离散随机变量在各特定取值上的概率
		- $p_{X}(x)=\mathbf{P}(X=x)=\mathbf{P}(\{\omega \in \Omega \text { s.t. } X(\omega)=x\})$
	- 期望值：随机变量的各特定取值乘以其概率的总和
		- ++ 字面意思的期望值（分布的中心，如质心等）
		- $\mathbf{E}[X]=\sum_{x} x p_{X}(x)$
		- $\mathbf{E}[g(X)]=\sum_{x} g(x) p_{X}(x)$
			- 如果 $g$ 是线性的，则 $\mathbf{E}[g(X)] = g(\mathbf{E}[X])$，i.e. $\mathbf{E}[\alpha X+\beta]=\alpha \mathbf{E}[X]+\beta$
	- 方差：随机变量减去其期望值，结果的二次幂作为随机变量，该随机变量的期望值即为方差
		- ++ 描述随机变量的离散程度（单位和随机变量不同）
		- $\operatorname{var}(X)=\mathbf{E}\left[(X-\mathbf{E}[X])^{2}\right]
			=\sum_{x}(x-\mathbf{E}[X])^{2} p_{X}(x)
			=\mathbf{E}\left[X^{2}\right]-(\mathbf{E}[X])^{2}$
			- 标准差：$\sigma_{X}=\sqrt{\operatorname{var}(X)}$ （单位相同）



# <u>**L6. Discrete Random Variables II**</u>

## **Geometric PMF**

### e.g. $X$: number of independent coin tosses until first head

$$
\begin{gathered}
p_{X}(k)=(1-p)^{k-1} p, \quad k=1,2, \ldots \\
\\
\mathbf{E}[X]=\sum_{k=1}^{\infty} k p_{X}(k)=\sum_{k=1}^{\infty} k(1-p)^{k-1} p
\end{gathered}
$$

### Conditional PMF and expectation

- $p_{X \mid A}(x)=\mathbf{P}(X=x \mid A)$
- $\mathbf{E}[X \mid A]=\sum_{x} x p_{X \mid A}(x)$

### in the example

- $p_{\mathrm{X}-2\mid \mathrm{X}>2}(k) = p_{\mathrm{X}}(k)$

### Total Expectation theorem

- Partition of sample space into disjoint events $A_{1},  A_{2}, \ldots, A_{n}$
	- $\mathbf{P}(B) = \mathbf{P}\left(A_{1}\right) \mathbf{P}\left(B \mid A_{1}\right)+\cdots+\mathbf{P}\left(A_{n}\right) \mathbf{P}\left(B \mid A_{n}\right)$
	- $\to \quad p_{X}(x)=\mathbf{P}\left(A_{1}\right) p_{X \mid A_{1}}(x)+\cdots+\mathbf{P}\left(A_{n}\right) p_{X \mid A_{n}}(x)$
	- $\to\quad \mathbf{E}[X]=\mathbf{P}\left(A_{1}\right) \mathbf{E}\left[X \mid A_{1}\right]+\cdots+\mathbf{P}\left(A_{n}\right) \mathbf{E}\left[X \mid A_{n}\right]$
- Geometric example:
	- $A_{1}:\{X=1\}, \quad A_{2}:\{X>1\}$
	- $\begin{aligned} \mathbf{E}[X]&&&=& & \mathbf{P}(X=1) \mathbf{E}[X \mid X=1] 
		 &+&&&\mathbf{P}(X>1) \mathbf{E}[X \mid X>1] 
		\\ &&&=& & p\cdot 1 
		 &+&&&(1-p)\cdot(\mathbf{E}[X-1 \mid X-1>0]+1)
		\\ &&&=& & p\cdot 1 
		 &+&&&(1-p)\cdot(\mathbf{E}[X]+1)\end{aligned}$
	- Solve to get  $\mathbf{E} [X]=1 / p$

## **Joint/Marginal/Conditional PMFs**

- Joint: $p_{X, Y}(x, y)=\mathbf{P}(X=x$ and $Y=y)$
  - $\sum_{x} \sum_{y} p_{X, Y}(x, y)=1$

- Marginal: $p_{X}(x)=\sum_{y} p_{X, Y}(x, y)$
- Conditional: $p_{X \mid Y}(x \mid y)=\mathbf{P}(X=x \mid Y=y)=\frac{p_{X, Y}(x, y)}{p_{Y}(y)}$
  - $\sum_{x} p_{X \mid Y}(x \mid y)=1$


## *Thinking*

- 通过条件期望值进行几何期望值的计算
	- 类似递归和分治（divide and conquer）
- 联合概率质量函数
	- 两个随机变量的关系

# <u>**L7. Discrete Random Variables III**</u>

## **Review**

### PMF notations

- Marginal: $p_{X}(x)=\mathbf{P}(X=x)$
- Joint: $p_{X, Y}(x, y)=\mathbf{P}(X=x, Y=y)$
- Conditional: $p_{X \mid Y}(x \mid y)=\mathbf{P}(X=x \mid Y=y)$
- Relations
	- $p_{X}(x)=\sum_{y} p_{X, Y}(x, y)$
	- $p_{X, Y}(x, y)=p_{X}(x) p_{Y \mid X}(y \mid x)$

### Probability and PMF (event and random varaible)

- $\mathbf{P}(A) \sim p_X(x)$
	- $A:X=x$
- $\mathbf{P}(A \cap B)=\mathbf{P}(A) \cdot \mathbf{P}(B \mid A) \sim p_{X, Y}(x, y)=p_{X}(x) p_{Y \mid X}(y \mid x)$
	- $A:X=x\qquad B:Y=y$

## **Multiple Random Variables**

### PMF: Independent random variables

$$
p_{X, Y, Z}(x, y, z)=p_{X}(x) p_{Y \mid X}(y \mid x) p_{Z \mid X, Y}(z \mid x, y)
$$

- Random variables $X, Y, Z$ are **independent** if:
	- $p_{X, Y, Z}(x, y, z)=p_{X}(x) \cdot p_{Y}(y) \cdot p_{Z}(z)$
		for all $x, y, z$

### Expectations

$$
\begin{gathered}
\mathbf{E}[X]=\sum_{x} x p_{X}(x) \\
\mathbf{E}[g(X, Y)]=\sum_{x} \sum_{y} g(x, y) p_{X, Y}(x, y)
\end{gathered}
$$

- In general:
	- $\mathbf{E}[g(X, Y)] \neq g(\mathbf{E}[X], \mathbf{E}[Y])$
- <u>Linear</u>:
	- $\mathbf{E}[\alpha X+\beta]=\alpha \mathbf{E}[X]+\beta$
	- $\mathbf{E}[X+Y+Z]=\mathbf{E}[X]+\mathbf{E}[Y]+\mathbf{E}[Z]$
- If $X, Y$ are <u>independent</u>:
	- $\mathbf{E}[X Y]=\mathbf{E}[X] \mathbf{E}[Y]$
	- $\mathbf{E}[g(X) h(Y)]=\mathbf{E}[g(X)] \cdot \mathbf{E}[h(Y)]$

### Variances

- $\operatorname{Var}(a X)=a^{2} \operatorname{Var}(X)$
- $\operatorname{Var}(X+a)=\operatorname{Var}(X)$
- If $X, Y$ are <u>independent</u>:
	- $\operatorname{Var}(X+Y)=\operatorname{Var}(X)+\operatorname{Var}(Y)$
- Examples:
	- If $X=Y, \operatorname{Var}(X+Y)= 4\operatorname{Var}(X)$
	- If $X=-Y, \operatorname{Var}(X+Y)= 0$
	- If $X, Y$ indep., and $Z=X-3 Y$, $\operatorname{Var}(X)=\operatorname{Var}(Z)+9\operatorname{Var}(Y)$

## *Thinking*

- 事件和随机变量的关系，也是事件概率和概率质量函数的关系
	- $A:X=x \quad\to\quad \mathbf{P}(A) \sim p_X(x)$
- 多个随机变量的属性公式（详见笔记）
	- 概率质量函数PMF
	- 期望值
	- 方差
- 利用这些公式的计算技巧



# <u>Quiz1 Review</u>

## Some Discrete Distributions

|           | $x$                                                          | $p_X(k)$                                                     | $\mathbf{E}[X]$ | $\operatorname{Var}(X)$ |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ | --------------- | ----------------------- |
| Bernoulli | $\begin{cases}1 & \text { success } \\ 0 & \text { failure }\end{cases}$ | $\begin{cases}p & k=1 \\ 1-p & k=0\end{cases}$               | $p$             | $p(1-p)$                |
| Binomial  | Number of successes <br />in $n$ Bernoulli trials            | $\left(\begin{array}{l}n \\ k\end{array}\right) p^{k}(1-p)^{n-k}$<br/>$k=0,1, \ldots, n$ | $np$            | $np(1-p)$               |
| Geometric | Number of trials <br />until first success                   | $(1-p)^{k-1} p$<br/>$k=1,2, \ldots$                          | $1 \over p$     | $1-p \over p^2$         |
| Uniform   | An integer in <br />the interval $[a,b]$                     | $\begin{cases}\frac{1}{b-a+1} & k=a, \ldots, b \\ 0 & \text { otherwise }\end{cases}$ | $a+b \over 2$   | $(b-a)(b-a+2) \over 12$ |



# <u>Quiz1</u>

## *Thinking*

- 对问题公式化的方式及建立符号系统是重要的
- 不必简化计算，甚至可以直接带入符号
- 对于期望值和方差进行拆分计算往往简单很多：前者只需线性，后者需要独立
- 计数是重要的解题方式
- 贝叶斯定理
- 利用求和符号 $\sum$ 连乘符号 $\prod$ 书写公式



















