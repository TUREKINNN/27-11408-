---
title: Lecture 02 - 随机变量及其分布
subject: 概率论与数理统计
chapter: 第二章
lecture: 02
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 02: 随机变量及其分布

## 一、随机变量的概念

### 1.1 随机变量的定义

<span style="background-color: #ccc1d9">**定义（随机变量）**</span> 设随机试验 $E$ 的样本空间为 $\Omega = \{\omega\}$ ，如果对每一个 $\omega \in \Omega$ ，都有唯一的实数 $X(\omega)$ 与之对应，并且对任意实数 $x$ ，$\{\omega \mid X(\omega) \leq x, \omega \in \Omega\}$ 是随机事件，则称定义在 $\Omega$ 上的实值单值函数 $X(\omega)$ 为**随机变量**，简记为 $X$。

**理解要点**：
- 随机变量是定义在样本空间上的函数，其定义域是样本空间 $\Omega$
- 通常用大写字母 $X, Y, Z$ 等表示随机变量
- 随机变量的取值具有随机性，但取值的概率规律是确定的

### 1.2 随机变量的分类

随机变量按其取值特点可分为两类：

| 类型 | 特点 | 示例 |
|------|------|------|
| **离散型** | 取值为有限个或可列无限个 | 掷骰子的点数、产品中的次品数 |
| **连续型** | 取值充满某个区间 | 测量误差、灯泡寿命 |

---

## 二、分布函数

### 2.1 分布函数的定义

<span style="background-color: #ccc1d9">**定义（分布函数）**</span> 设 $X$ 是随机变量，$x$ 是任意实数，称函数

$$F(x) = P\{X \leq x\}, \quad x \in \mathbb{R}$$

为随机变量 $X$ 的**分布函数**，记作 $X \sim F(x)$。

### 2.2 分布函数的性质

<span style="background-color: #8db3e2">**定理（分布函数的性质）**</span> 分布函数 $F(x)$ 具有以下性质：

1. **单调不减性**：对任意 $x_1 < x_2$，有 $F(x_1) \leq F(x_2)$
2. **右连续性**：对任意 $x_0$，有 $\lim_{x \to x_0^+} F(x) = F(x_0)$
3. **极限性质**：$F(-\infty) = 0$，$F(+\infty) = 1$

**注**：满足以上三条性质的函数必是某个随机变量的分布函数，反之亦然。

### 2.3 利用分布函数求概率

设 $X$ 的分布函数为 $F(x)$，则：

$$
\begin{align*}
P\{X \leq a\} &= F(a) \\
P\{X < a\} &= F(a-0) \\
P\{X = a\} &= F(a) - F(a-0) \\
P\{a < X \leq b\} &= F(b) - F(a) \\
P\{a \leq X \leq b\} &= F(b) - F(a-0)
\end{align*}
$$

---

## 三、离散型随机变量的概率分布律

### 3.1 概率分布律的定义

<span style="background-color: #ccc1d9">**定义（概率分布律）**</span> 设离散型随机变量 $X$ 所有可能的取值为 $x_1, x_2, \cdots$，则称

$$P\{X = x_i\} = p_i, \quad i = 1, 2, \cdots$$

为 $X$ 的**概率分布律**（或分布列）。

### 3.2 概率分布律的性质

<span style="background-color: #8db3e2">**定理**</span> 数列 $\{p_i\}$ 是离散型随机变量概率分布律的充要条件：

1. **非负性**：$p_i \geq 0$，$i = 1, 2, \cdots$
2. **归一性**：$\sum_{i=1}^{\infty} p_i = 1$

### 3.3 分布函数与概率分布律的关系

离散型随机变量 $X$ 的分布函数可表示为：

$$F(x) = P\{X \leq x\} = \sum_{x_i \leq x} p_i$$

---

## 四、连续型随机变量的概率密度函数

### 4.1 概率密度函数的定义

<span style="background-color: #ccc1d9">**定义（概率密度函数）**</span> 如果随机变量 $X$ 的分布函数 $F(x)$ 可以表示为

$$F(x) = \int_{-\infty}^{x} f(t) dt$$

其中 $f(x)$ 是非负可积函数，则称 $X$ 为**连续型随机变量**，称 $f(x)$ 为 $X$ 的**概率密度函数**，简记为 $X \sim f(x)$。

### 4.2 概率密度函数的性质

<span style="background-color: #8db3e2">**定理**</span> 函数 $f(x)$ 是概率密度函数的充要条件：

1. **非负性**：$f(x) \geq 0$，$\forall x \in \mathbb{R}$
2. **归一性**：$\int_{-\infty}^{+\infty} f(x) dx = 1$

### 4.3 连续型随机变量的概率计算

设 $X \sim f(x)$，则：

- 对任意实数 $c$，$P\{X = c\} = 0$
- 对任意区间 $(a, b)$，$P\{a < X < b\} = \int_{a}^{b} f(x) dx$

**注**：连续型随机变量在某点的概率为0，但该点仍可能是随机变量的可能取值。

---

## 五、常见分布

### 5.1 离散型分布

#### (1) 0-1分布 $B(1, p)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率分布为

$$P\{X = 1\} = p, \quad P\{X = 0\} = 1-p \quad (0 < p < 1)$$

则称 $X$ 服从参数为 $p$ 的**0-1分布**，记为 $X \sim B(1, p)$。

**背景**：一次伯努利试验中成功的次数。

#### (2) 二项分布 $B(n, p)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率分布为

$$P\{X = k\} = \binom{n}{k} p^k (1-p)^{n-k}, \quad k = 0, 1, \cdots, n \quad (0 < p < 1)$$

则称 $X$ 服从参数为 $(n, p)$ 的**二项分布**，记为 $X \sim B(n, p)$。

**背景**：$n$ 次独立重复伯努利试验中成功的次数。

#### (3) 泊松分布 $P(\lambda)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率分布为

$$P\{X = k\} = \frac{\lambda^k}{k!} e^{-\lambda}, \quad k = 0, 1, 2, \cdots \quad (\lambda > 0)$$

则称 $X$ 服从参数为 $\lambda$ 的**泊松分布**，记为 $X \sim P(\lambda)$。

<span style="background-color: #8db3e2">**定理（泊松定理）**</span> 若 $X \sim B(n, p)$，当 $n$ 很大、$p$ 很小且 $\lambda = np$ 适中时，二项分布可用泊松分布近似：

$$\binom{n}{k} p^k (1-p)^{n-k} \approx \frac{\lambda^k}{k!} e^{-\lambda}$$

### 5.2 连续型分布

#### (1) 均匀分布 $U(a, b)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率密度为

$$f(x) = \begin{cases}
\frac{1}{b-a}, & a < x < b \\
0, & \text{其他}
\end{cases}$$

则称 $X$ 在区间 $(a, b)$ 上服从**均匀分布**，记为 $X \sim U(a, b)$。

**分布函数**：

$$F(x) = \begin{cases}
0, & x < a \\
\frac{x-a}{b-a}, & a \leq x < b \\
1, & x \geq b
\end{cases}$$

#### (2) 指数分布 $E(\lambda)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率密度为

$$f(x) = \begin{cases}
\lambda e^{-\lambda x}, & x > 0 \\
0, & \text{其他}
\end{cases} \quad (\lambda > 0)$$

则称 $X$ 服从参数为 $\lambda$ 的**指数分布**，记为 $X \sim E(\lambda)$。

**分布函数**：

$$F(x) = \begin{cases}
1 - e^{-\lambda x}, & x \geq 0 \\
0, & x < 0
\end{cases}$$

<span style="background-color: #8db3e2">**定理（无记忆性）**</span> 对任意 $t > 0, s > 0$，有

$$P\{X \geq t+s \mid X \geq t\} = P\{X \geq s\}$$

#### (3) 正态分布 $N(\mu, \sigma^2)$

<span style="background-color: #ccc1d9">**定义**</span> 如果 $X$ 的概率密度为

$$f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-\mu)^2}{2\sigma^2}}, \quad -\infty < x < +\infty$$

其中 $\mu \in \mathbb{R}, \sigma > 0$，则称 $X$ 服从参数为 $(\mu, \sigma^2)$ 的**正态分布**，记为 $X \sim N(\mu, \sigma^2)$。

当 $\mu = 0, \sigma = 1$ 时，称为**标准正态分布**，记为 $X \sim N(0, 1)$，其概率密度为：

$$\varphi(x) = \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}$$

**分布函数**：$\Phi(x) = \int_{-\infty}^{x} \varphi(t) dt$

**性质**：$\Phi(-x) = 1 - \Phi(x)$

---

## 六、随机变量函数的分布

### 6.1 离散型随机变量函数的分布

设 $X$ 是离散型随机变量，分布律为 $P\{X = x_i\} = p_i$，则 $Y = g(X)$ 的分布律为：

$$P\{Y = y_j\} = \sum_{g(x_i) = y_j} p_i$$

### 6.2 连续型随机变量函数的分布

设 $X \sim f_X(x)$，$Y = g(X)$，求 $Y$ 的概率密度 $f_Y(y)$ 的方法：

1. **分布函数法**：
   - 先求 $Y$ 的分布函数 $F_Y(y) = P\{Y \leq y\} = P\{g(X) \leq y\}$
   - 再求导得 $f_Y(y) = F_Y'(y)$

2. **公式法**（单调函数）：
   若 $g(x)$ 严格单调且可导，其反函数为 $x = h(y)$，则：

$$f_Y(y) = f_X(h(y)) \cdot |h'(y)|$$

---

## 七、典型例题

### 例题1：指数分布的参数求解（660题第521题）

**题目**：设随机变量 $X$ 服从参数为 $\lambda$ 的指数分布，对 $X$ 作3次独立重复观察，至少有一次观测值大于2的概率为 $\frac{7}{8}$，则 $\lambda =$ ____。

**思路**：利用对立事件概率公式和指数分布的性质。

**解答**：
$X \sim E(\lambda)$，则 $P\{X > 2\} = e^{-2\lambda}$

3次独立观察中，至少有一次大于2的对立事件是"3次都不大于2"：
$$P\{\text{至少一次} > 2\} = 1 - P\{\text{三次都} \leq 2\} = 1 - [P\{X \leq 2\}]^3$$

又 $P\{X \leq 2\} = 1 - e^{-2\lambda}$，代入得：
$$1 - (1 - e^{-2\lambda})^3 = \frac{7}{8}$$

$$(1 - e^{-2\lambda})^3 = \frac{1}{8}$$

$$1 - e^{-2\lambda} = \frac{1}{2}$$

$$e^{-2\lambda} = \frac{1}{2}$$

$$-2\lambda = \ln \frac{1}{2} = -\ln 2$$

$$\lambda = \frac{\ln 2}{2}$$

**总结**：指数分布的概率计算 $P\{X > x\} = e^{-\lambda x}$ 是关键。

---

### 例题2：指数分布的无记忆性（660题第522题）

**题目**：设随机变量 $X$ 服从参数为1的指数分布，则 $P\{3 > X > 2 \mid X > 1\} =$ ____。

**思路**：利用指数分布的无记忆性。

**解答**：
$X \sim E(1)$，由无记忆性：
$$P\{X > t+s \mid X > t\} = P\{X > s\}$$

$$P\{3 > X > 2 \mid X > 1\} = P\{X > 2 \mid X > 1\} - P\{X > 3 \mid X > 1\}$$

$$= P\{X > 1\} - P\{X > 2\} = e^{-1} - e^{-2}$$

**总结**：无记忆性是指数分布的重要性质，$P\{X > t+s \mid X > t\} = P\{X > s\}$。

---

### 例题3：概率密度的对称性（660题第523题）

**题目**：设随机变量 $X$ 的概率密度函数 $f(x)$ 满足 $f(1+x) = f(1-x)$，且 $\int_{1}^{2} f(x) dx = 0.3$，则 $F(0) =$ ____。

**思路**：利用概率密度的对称性和归一性。

**解答**：
$f(1+x) = f(1-x)$ 表示 $f(x)$ 关于 $x=1$ 对称。

$$\int_{-\infty}^{1} f(x) dx = \int_{1}^{+\infty} f(x) dx = 0.5$$

$$\int_{1}^{2} f(x) dx = 0.3 \Rightarrow \int_{2}^{+\infty} f(x) dx = 0.5 - 0.3 = 0.2$$

由对称性，$\int_{-\infty}^{0} f(x) dx = \int_{2}^{+\infty} f(x) dx = 0.2$

$$F(0) = P\{X \leq 0\} = \int_{-\infty}^{0} f(x) dx = 0.2$$

**总结**：概率密度的对称性可简化积分计算。

---

### 例题4：随机变量函数的分布（660题第524题）

**题目**：设随机变量 $X$ 服从区间 $(-1, 3)$ 上的均匀分布，$Y = X^2$，则 $Y$ 的概率密度 $f_Y(y) =$ ____。

**思路**：使用分布函数法求随机变量函数的分布。

**解答**：
$X \sim U(-1, 3)$，则 $f_X(x) = \frac{1}{4}, -1 < x < 3$

当 $y < 0$ 时，$F_Y(y) = 0$

当 $0 \leq y < 1$ 时：
$$F_Y(y) = P\{X^2 \leq y\} = P\{-\sqrt{y} \leq X \leq \sqrt{y}\} = \frac{\sqrt{y} - (-\sqrt{y})}{4} = \frac{\sqrt{y}}{2}$$

当 $1 \leq y < 9$ 时：
$$F_Y(y) = P\{-1 \leq X \leq \sqrt{y}\} = \frac{\sqrt{y} - (-1)}{4} = \frac{\sqrt{y} + 1}{4}$$

当 $y \geq 9$ 时，$F_Y(y) = 1$

求导得概率密度：
$$f_Y(y) = \begin{cases}
\frac{1}{4\sqrt{y}}, & 0 < y < 1 \\
\frac{1}{8\sqrt{y}}, & 1 < y < 9 \\
0, & \text{其他}
\end{cases}$$

**总结**：分布函数法是求随机变量函数分布的通用方法。

---

### 例题5：正态分布的性质（660题第525题）

**题目**：设随机变量 $X \sim N(\mu, \sigma^2)(\sigma > 0)$，其分布函数为 $F(x)$，则 $F(\mu + x\sigma) + F(\mu - x\sigma) =$ ____。

**思路**：利用标准正态分布的对称性。

**解答**：
$$F(\mu + x\sigma) = P\{X \leq \mu + x\sigma\} = P\left\{\frac{X - \mu}{\sigma} \leq x\right\} = \Phi(x)$$

$$F(\mu - x\sigma) = P\{X \leq \mu - x\sigma\} = P\left\{\frac{X - \mu}{\sigma} \leq -x\right\} = \Phi(-x)$$

由标准正态分布性质 $\Phi(-x) = 1 - \Phi(x)$：

$$F(\mu + x\sigma) + F(\mu - x\sigma) = \Phi(x) + 1 - \Phi(x) = 1$$

**总结**：正态分布关于均值 $\mu$ 对称。

---

### 例题6：概率密度的确定（660题第526题）

**题目**：设随机变量 $X$ 的概率密度函数 $f(x) = \begin{cases} x, & a < x < b \\ 0, & \text{其他} \end{cases} (a > 0)$，其中 $a, b$ 为待定常数，且 $E(X^2) = 2$，则 $P\{|X| < \sqrt{2}\} =$ ____。

**思路**：利用概率密度的归一性和数学期望确定参数。

**解答**：
由归一性：$\int_{a}^{b} x dx = \frac{b^2 - a^2}{2} = 1 \Rightarrow b^2 - a^2 = 2$

由 $E(X^2) = 2$：$\int_{a}^{b} x^3 dx = \frac{b^4 - a^4}{4} = 2 \Rightarrow b^4 - a^4 = 8$

$$b^4 - a^4 = (b^2 - a^2)(b^2 + a^2) = 2(b^2 + a^2) = 8 \Rightarrow b^2 + a^2 = 4$$

联立解得：$b^2 = 3, a^2 = 1$，又 $a > 0$，故 $a = 1, b = \sqrt{3}$

$$P\{|X| < \sqrt{2}\} = P\{0 < X < \sqrt{2}\} = \int_{1}^{\sqrt{2}} x dx = \frac{(\sqrt{2})^2 - 1^2}{2} = \frac{1}{2}$$

**总结**：概率密度的待定参数可通过归一性和其他条件确定。

---

### 例题7：条件概率的计算（660题第527题）

**题目**：设随机变量 $X$ 的概率密度函数为 $f(x) = \begin{cases} xe^{-x}, & x > 0 \\ 0, & x \leq 0 \end{cases}$，则 $P\{X \leq 2 \mid X \geq 1\} =$ ____。

**思路**：利用条件概率公式和积分计算。

**解答**：
$$P\{X \leq 2 \mid X \geq 1\} = \frac{P\{1 \leq X \leq 2\}}{P\{X \geq 1\}}$$

$$P\{1 \leq X \leq 2\} = \int_{1}^{2} xe^{-x} dx = [-xe^{-x}]_{1}^{2} + \int_{1}^{2} e^{-x} dx = -2e^{-2} + e^{-1} - e^{-2} + e^{-1} = 2e^{-1} - 3e^{-2}$$

$$P\{X \geq 1\} = \int_{1}^{+\infty} xe^{-x} dx = [-xe^{-x}]_{1}^{+\infty} + \int_{1}^{+\infty} e^{-x} dx = e^{-1} + e^{-1} = 2e^{-1}$$

$$P\{X \leq 2 \mid X \geq 1\} = \frac{2e^{-1} - 3e^{-2}}{2e^{-1}} = 1 - \frac{3}{2e}$$

**总结**：条件概率公式 $P(A|B) = \frac{P(AB)}{P(B)}$ 是解题关键。

---

### 例题8：全概率公式的应用（660题第528题）

**题目**：已知随机变量 $X$ 的概率分布为 $P\{X = k\} = \frac{1}{3} (k = 1, 2, 3)$，当 $X = k$ 时随机变量 $Y$ 在 $(0, k)$ 上服从均匀分布，则 $P\{Y \leq 2.5\} =$ ____。

**思路**：利用全概率公式分解。

**解答**：
由全概率公式：
$$P\{Y \leq 2.5\} = \sum_{k=1}^{3} P\{X = k\} P\{Y \leq 2.5 \mid X = k\}$$

$$P\{Y \leq 2.5 \mid X = 1\} = P\{Y \leq 2.5\} = 1 \quad (\text{因} Y \in (0,1))$$

$$P\{Y \leq 2.5 \mid X = 2\} = P\{Y \leq 2.5\} = 1 \quad (\text{因} Y \in (0,2))$$

$$P\{Y \leq 2.5 \mid X = 3\} = \frac{2.5}{3} = \frac{5}{6}$$

$$P\{Y \leq 2.5\} = \frac{1}{3} \times 1 + \frac{1}{3} \times 1 + \frac{1}{3} \times \frac{5}{6} = \frac{17}{18}$$

**总结**：全概率公式适用于多阶段随机试验。

---

### 例题9：正态分布的概率计算（660题第529题）

**题目**：随机变量 $X$ 服从正态分布 $N(3, 6^2)$，$P\{3 < X < 4\} = 0.2$，则 $P\{X \geq 2\} =$ ____。

**思路**：利用正态分布的对称性。

**解答**：
$X \sim N(3, 36)$，令 $Z = \frac{X - 3}{6} \sim N(0,1)$

$$P\{3 < X < 4\} = P\left\{0 < Z < \frac{1}{6}\right\} = \Phi\left(\frac{1}{6}\right) - \Phi(0) = \Phi\left(\frac{1}{6}\right) - 0.5 = 0.2$$

$$\Phi\left(\frac{1}{6}\right) = 0.7$$

$$P\{X \geq 2\} = P\left\{Z \geq \frac{2-3}{6}\right\} = P\left\{Z \geq -\frac{1}{6}\right\} = 1 - \Phi\left(-\frac{1}{6}\right) = \Phi\left(\frac{1}{6}\right) = 0.7$$

**总结**：正态分布概率计算需先标准化。

---

## 八、解题方法总结

### 8.1 主要方法

| 类型 | 方法 |
|------|------|
| 分布函数判定 | 验证单调不减、右连续、极限性质 |
| 离散型分布律 | 利用非负性和归一性 |
| 连续型概率密度 | 利用非负性和归一性，积分求概率 |
| 随机变量函数分布 | 分布函数法、公式法（单调函数） |
| 常见分布 | 牢记各分布的概率密度和性质 |

### 8.2 常见易错点

1. **分布函数的定义**：$F(x) = P\{X \leq x\}$，不是 $P\{X < x\}$
2. **连续型随机变量单点概率**：$P\{X = c\} = 0$，但 $\{X = c\}$ 不是不可能事件
3. **指数分布的参数**：注意不同教材中指数分布的参数形式可能不同
4. **正态分布标准化**：$Z = \frac{X - \mu}{\sigma}$，不是 $\frac{X - \mu}{\sigma^2}$

---

## 九、练习题精选

### 基础练习

1. 设随机变量 $X$ 的分布函数为 $F(x) = \begin{cases} 0, & x < 0 \\ A\sin x, & 0 \leq x < \frac{\pi}{2} \\ 1, & x \geq \frac{\pi}{2} \end{cases}$，求常数 $A$ 及 $P\{|X| < \frac{\pi}{6}\}$。

2. 设 $X \sim B(2, p), Y \sim B(3, p)$，若 $P\{X \geq 1\} = \frac{5}{9}$，求 $P\{Y \geq 1\}$。

3. 设 $X \sim N(1, 4)$，求 $P\{X^2 \leq 9\}$。

### 提高练习

4. 设随机变量 $X$ 的概率密度为 $f(x) = \frac{1}{2} e^{-|x|}$，求 $Y = X^2$ 的概率密度。

5. 设 $X \sim U(0, 1)$，求 $Y = -\frac{1}{\lambda} \ln(1 - X)$ 的分布。

---

## 参考答案提示

1. $A = 1$，$P\{|X| < \frac{\pi}{6}\} = \frac{1}{2}$（提示：利用分布函数右连续性）

2. $P\{Y \geq 1\} = \frac{19}{27}$（提示：先由 $P\{X \geq 1\}$ 求 $p$）

3. $P\{X^2 \leq 9\} = \Phi(1) - \Phi(-2)$（提示：标准化后计算）

4. $f_Y(y) = \frac{1}{2\sqrt{y}} e^{-\sqrt{y}}, y > 0$（提示：分布函数法）

5. $Y \sim E(\lambda)$（提示：这是生成指数分布的常用方法）

---

> **注**：本 Lecture 内容涵盖随机变量、分布函数、离散型和连续型随机变量、常见分布及典型例题。建议结合《基础过关660题》第521-529题进行练习巩固。
### 补充：常见分布汇总表

| 分布名称 | 记号 | 概率分布/密度函数 | 期望 | 方差 |
|----------|------|-------------------|------|------|
| 两点分布 | $B(1,p)$ | $P\{X=k\}=p^k(1-p)^{1-k}, k=0,1$ | $p$ | $p(1-p)$ |
| 二项分布 | $B(n,p)$ | $P\{X=k\}=\binom{n}{k}p^k(1-p)^{n-k}$ | $np$ | $np(1-p)$ |
| 泊松分布 | $P(\lambda)$ | $P\{X=k\}=\frac{\lambda^k e^{-\lambda}}{k!}$ | $\lambda$ | $\lambda$ |
| 几何分布 | $Ge(p)$ | $P\{X=k\}=(1-p)^{k-1}p, k=1,2,\cdots$ | $\frac{1}{p}$ | $\frac{1-p}{p^2}$ |
| 超几何分布 | $H(N,M,n)$ | $P\{X=k\}=\frac{\binom{M}{k}\binom{N-M}{n-k}}{\binom{N}{n}}$ | $\frac{nM}{N}$ | $\frac{nM(N-M)(N-n)}{N^2(N-1)}$ |
| 均匀分布 | $U(a,b)$ | $f(x)=\frac{1}{b-a}, a<x<b$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| 指数分布 | $E(\lambda)$ | $f(x)=\lambda e^{-\lambda x}, x>0$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |
| 正态分布 | $N(\mu,\sigma^2)$ | $f(x)=\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $\mu$ | $\sigma^2$ |
| 伽马分布 | $\Gamma(\alpha,\lambda)$ | $f(x)=\frac{\lambda^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x}, x>0$ | $\frac{\alpha}{\lambda}$ | $\frac{\alpha}{\lambda^2}$ |
