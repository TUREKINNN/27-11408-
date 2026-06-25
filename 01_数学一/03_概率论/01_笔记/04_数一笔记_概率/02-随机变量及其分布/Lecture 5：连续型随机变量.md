---
title: Lecture 5：连续型随机变量
  - 考研
  - 数学一
  - 概率论
  - 数学
categories: 概率论
date: 2026-06-16
---

# Lecture 5：连续型随机变量

> **考研数学一 · 概率论与数理统计 · 第5讲**
> 本讲涵盖：连续型随机变量的密度函数与分布函数、均匀分布U(a,b)、正态分布N(μ,σ²)、指数分布E(λ)、标准化变换Z=(X-μ)/σ
> 考纲要求：★★★★★（正态分布几乎每年必考，指数分布和均匀分布高频出现）

---

## 一、连续型随机变量的基本概念

### 1.1 概率密度函数的定义

**定义：** 设随机变量 $X$ 的分布函数为 $F(x)$，若存在非负可积函数 $f(x) \geq 0$，使得对任意实数 $x$，有：

$$\boxed{F(x) = \int_{-\infty}^{x} f(t) \, dt}$$

则称 $X$ 为**连续型随机变量**，$f(x)$ 称为 $X$ 的**概率密度函数**（Probability Density Function, PDF）。

### 1.2 概率密度函数的性质

$f(x)$ 必须满足以下两个条件：

1. **非负性：** $f(x) \geq 0$，对一切 $x \in \mathbb{R}$
2. **归一性：** $\displaystyle\int_{-\infty}^{+\infty} f(x) \, dx = 1$

> **重要推论：**
> - 对任意单个点 $a$，$P\{X = a\} = 0$（连续型随机变量取任何单点的概率为零）
> - 因此 $P\{a < X \leq b\} = P\{a \leq X \leq b\} = P\{a < X < b\} = P\{a \leq X < b\}$
> - 概率密度 $f(x)$ 的值**不是**概率，可以大于1

### 1.3 由密度函数求概率

$$\boxed{P\{a < X \leq b\} = F(b) - F(a) = \int_{a}^{b} f(x) \, dx}$$

即概率等于密度函数在区间 $[a, b]$ 上的定积分（曲线下方的面积）。

### 1.4 密度函数与分布函数的关系

- **由密度求分布：** $F(x) = \displaystyle\int_{-\infty}^{x} f(t) \, dt$
- **由分布求密度：** 在 $f(x)$ 的连续点处，$f(x) = F'(x)$

> **注意：** 分布函数 $F(x)$ 一定是连续的（即使 $f(x)$ 有间断点），但不一定处处可导。

---

## 二、均匀分布 ⭐⭐⭐

### 2.1 定义

若随机变量 $X$ 的概率密度函数为：

$$\boxed{f(x) = \begin{cases} \dfrac{1}{b-a}, & a \leq x \leq b \\ 0, & \text{其他} \end{cases}}$$

则称 $X$ 在区间 $[a, b]$ 上服从**均匀分布**（Uniform Distribution），记为 $X \sim U(a, b)$。

### 2.2 分布函数

$$F(x) = \begin{cases} 0, & x < a \\ \dfrac{x-a}{b-a}, & a \leq x \leq b \\ 1, & x > b \end{cases}$$

### 2.3 几何意义

- 密度函数在 $[a, b]$ 上是一条水平线（常数 $1/(b-a)$）
- $X$ 落在 $[a, b]$ 的任意子区间 $[c, d]$ 内的概率只与区间长度有关：

$$\boxed{P\{c \leq X \leq d\} = \frac{d - c}{b - a}, \quad a \leq c < d \leq b}$$

### 2.4 期望与方差

$$\boxed{E(X) = \frac{a+b}{2}, \quad D(X) = \frac{(b-a)^2}{12}}$$

**推导期望：**
$$E(X) = \int_a^b x \cdot \frac{1}{b-a} \, dx = \frac{1}{b-a} \cdot \frac{x^2}{2}\bigg|_a^b = \frac{b^2 - a^2}{2(b-a)} = \frac{a+b}{2}$$

**推导方差：**
$$E(X^2) = \int_a^b x^2 \cdot \frac{1}{b-a} \, dx = \frac{a^2 + ab + b^2}{3}$$
$$D(X) = E(X^2) - [E(X)]^2 = \frac{a^2+ab+b^2}{3} - \frac{(a+b)^2}{4} = \frac{(b-a)^2}{12}$$

### 2.5 典型应用场景

1. **舍入误差：** 对某值四舍五入产生的误差通常服从 $U(-0.5, 0.5)$
2. **随机数生成：** 计算机生成的伪随机数服从 $U(0, 1)$
3. **等可能概型的连续化：** 在区间上"等可能"取值

**【例1】** 公共汽车站每隔 15 分钟发一辆车，乘客随机到达车站，求候车时间不超过 6 分钟的概率。

**解：** 设 $X$ 为乘客的候车时间，$X \sim U(0, 15)$
$$P\{X \leq 6\} = F(6) = \frac{6 - 0}{15 - 0} = \frac{6}{15} = \frac{2}{5} = 0.4$$

---

## 三、指数分布 ⭐⭐⭐⭐

### 3.1 定义

若随机变量 $X$ 的概率密度函数为：

$$\boxed{f(x) = \begin{cases} \lambda e^{-\lambda x}, & x > 0 \\ 0, & x \leq 0 \end{cases}}$$

其中 $\lambda > 0$ 为常数，则称 $X$ 服从参数为 $\lambda$ 的**指数分布**（Exponential Distribution），记为 $X \sim E(\lambda)$ 或 $X \sim \text{Exp}(\lambda)$。

### 3.2 分布函数

$$\boxed{F(x) = \begin{cases} 1 - e^{-\lambda x}, & x > 0 \\ 0, & x \leq 0 \end{cases}}$$

**验证归一性：**
$$\int_0^{+\infty} \lambda e^{-\lambda x} \, dx = \left[-e^{-\lambda x}\right]_0^{+\infty} = 0 - (-1) = 1 \quad \checkmark$$

### 3.3 期望与方差

$$\boxed{E(X) = \frac{1}{\lambda}, \quad D(X) = \frac{1}{\lambda^2}}$$

**推导期望：** 利用分部积分：
$$E(X) = \int_0^{+\infty} x \lambda e^{-\lambda x} \, dx = \left[-xe^{-\lambda x}\right]_0^{+\infty} + \int_0^{+\infty} e^{-\lambda x} \, dx = 0 + \frac{1}{\lambda} = \frac{1}{\lambda}$$

**推导方差：**
$$E(X^2) = \int_0^{+\infty} x^2 \lambda e^{-\lambda x} \, dx = \frac{2}{\lambda^2}$$
$$D(X) = \frac{2}{\lambda^2} - \frac{1}{\lambda^2} = \frac{1}{\lambda^2}$$

### 3.4 无记忆性 ⭐⭐⭐⭐

指数分布具有**无记忆性**（Memoryless Property），这是连续型分布中唯一具有无记忆性的分布：

$$\boxed{P\{X > s + t \mid X > s\} = P\{X > t\}, \quad s, t > 0}$$

即"已经等待了 $s$ 个单位时间"不影响"还需要等待 $t$ 个单位时间以上"的概率。

**证明：**
$$P\{X > s+t | X > s\} = \frac{P\{X > s+t\}}{P\{X > s\}} = \frac{e^{-\lambda(s+t)}}{e^{-\lambda s}} = e^{-\lambda t} = P\{X > t\} \quad \checkmark$$

> **重要结论：**
> - 离散型中只有**几何分布**具有无记忆性
> - 连续型中只有**指数分布**具有无记忆性
> - 指数分布可看作几何分布在连续情形的对应

### 3.5 典型应用场景

- **寿命分布：** 电子元件、灯泡的寿命
- **等待时间：** 两次事件之间的时间间隔（泊松过程中）
- **排队论：** 顾客到达的间隔时间

**【例2】** 某电子元件的寿命 $X$（单位：小时）服从 $\lambda = 0.001$ 的指数分布。求：

**(1)** 该元件寿命超过 1000 小时的概率

**解：**
$$P\{X > 1000\} = e^{-0.001 \times 1000} = e^{-1} \approx 0.3679$$

**(2)** 该元件已使用 500 小时，还能再使用 1000 小时以上的概率

**解：** 由无记忆性：
$$P\{X > 1500 | X > 500\} = P\{X > 1000\} = e^{-1} \approx 0.3679$$

---

## 四、正态分布 ⭐⭐⭐⭐⭐

### 4.1 定义

若随机变量 $X$ 的概率密度函数为：

$$\boxed{f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-\mu)^2}{2\sigma^2}}, \quad -\infty < x < +\infty}$$

其中 $\mu$ 为实数，$\sigma > 0$，则称 $X$ 服从参数为 $(\mu, \sigma^2)$ 的**正态分布**（Normal Distribution），记为 $X \sim N(\mu, \sigma^2)$。

### 4.2 期望与方差

$$\boxed{E(X) = \mu, \quad D(X) = \sigma^2}$$

即参数 $\mu$ 是分布的中心（期望），$\sigma^2$ 是分布的离散程度（方差），$\sigma$ 是标准差。

### 4.3 密度函数的性质

$f(x)$ 的图形关于 $x = \mu$ 对称，具有以下特征：

1. **对称轴：** $x = \mu$
2. **最大值：** $f(\mu) = \dfrac{1}{\sqrt{2\pi}\sigma}$
3. **拐点：** $x = \mu \pm \sigma$（二阶导数为零的点）
4. **渐近线：** $x$ 轴（$f(x) \to 0$ 当 $x \to \pm\infty$）
5. $\sigma$ 越大，曲线越"扁平"；$\sigma$ 越小，曲线越"尖峭"

**对称性公式：**
$$f(\mu - x) = f(\mu + x), \quad \forall x$$
$$P\{X \leq \mu - a\} = P\{X \geq \mu + a\}, \quad \forall a > 0$$

### 4.4 标准正态分布 ⭐⭐⭐⭐⭐

当 $\mu = 0$，$\sigma = 1$ 时，$X \sim N(0, 1)$ 称为**标准正态分布**，其密度函数和分布函数分别记为：

$$\varphi(x) = \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}}, \quad -\infty < x < +\infty$$

$$\Phi(x) = \int_{-\infty}^{x} \frac{1}{\sqrt{2\pi}} e^{-\frac{t^2}{2}} \, dt$$

**标准正态分布的重要性质：**

$$\boxed{\Phi(-x) = 1 - \Phi(x)}$$

**证明：** 由 $\varphi(t)$ 关于 $t=0$ 对称：
$$\Phi(-x) = \int_{-\infty}^{-x} \varphi(t) \, dt = \int_{x}^{+\infty} \varphi(t) \, dt = 1 - \Phi(x)$$

**常用数值（必须记住）：**

| $\Phi(x)$ 的值 | 对应概率 |
|-----------------|---------|
| $\Phi(0) = 0.5$ | $P\{Z \leq 0\} = 0.5$ |
| $\Phi(1) \approx 0.8413$ | $P\{-1 < Z < 1\} \approx 68.27\%$ |
| $\Phi(1.645) \approx 0.95$ | $P\{-1.645 < Z < 1.645\} = 90\%$ |
| $\Phi(1.96) \approx 0.975$ | $P\{-1.96 < Z < 1.96\} = 95\%$ |
| $\Phi(2) \approx 0.9772$ | $P\{-2 < Z < 2\} \approx 95.45\%$ |
| $\Phi(2.576) \approx 0.995$ | $P\{-2.576 < Z < 2.576\} = 99\%$ |
| $\Phi(3) \approx 0.9987$ | $P\{-3 < Z < 3\} \approx 99.73\%$ |

### 4.5 标准化变换 ⭐⭐⭐⭐⭐

**定理：** 若 $X \sim N(\mu, \sigma^2)$，则：

$$\boxed{Z = \frac{X - \mu}{\sigma} \sim N(0, 1)}$$

$Z$ 称为 $X$ 的**标准化随机变量**（Standardized Variable）。

**证明：**
$$E(Z) = E\left(\frac{X-\mu}{\sigma}\right) = \frac{E(X)-\mu}{\sigma} = 0$$
$$D(Z) = D\left(\frac{X-\mu}{\sigma}\right) = \frac{D(X)}{\sigma^2} = \frac{\sigma^2}{\sigma^2} = 1$$

由正态分布的线性变换性质，$Z$ 仍服从正态分布，故 $Z \sim N(0,1)$。

**一般正态分布的概率计算公式：**

$$\boxed{P\{a < X \leq b\} = \Phi\left(\frac{b-\mu}{\sigma}\right) - \Phi\left(\frac{a-\mu}{\sigma}\right)}$$

$$P\{X \leq x\} = \Phi\left(\frac{x-\mu}{\sigma}\right)$$

### 4.6 正态分布的线性变换性质 ⭐⭐⭐⭐

若 $X \sim N(\mu, \sigma^2)$，$Y = aX + b$（$a \neq 0$），则：

$$\boxed{Y \sim N(a\mu + b, \, a^2\sigma^2)}$$

**推论：** 若 $X \sim N(\mu, \sigma^2)$，则：
- $aX + b \sim N(a\mu + b, a^2\sigma^2)$
- $\dfrac{X - \mu}{\sigma} \sim N(0, 1)$（标准化）

### 4.7 3σ 法则（三西格玛法则）

$$P\{|X - \mu| < \sigma\} = P\{-1 < Z < 1\} = 2\Phi(1) - 1 \approx 0.6827$$
$$P\{|X - \mu| < 2\sigma\} = 2\Phi(2) - 1 \approx 0.9545$$
$$\boxed{P\{|X - \mu| < 3\sigma\} = 2\Phi(3) - 1 \approx 0.9973}$$

> **实际意义：** 正态分布的随机变量几乎总是落在 $(\mu - 3\sigma, \mu + 3\sigma)$ 范围内，超出的概率仅为 0.27%。

### 4.8 经典例题

**【例3】** 设 $X \sim N(3, 4)$，求 $P\{2 < X < 5\}$ 和 $P\{|X| > 2\}$。

**解：** $\mu = 3$，$\sigma = 2$

$$P\{2 < X < 5\} = \Phi\left(\frac{5-3}{2}\right) - \Phi\left(\frac{2-3}{2}\right) = \Phi(1) - \Phi(-0.5)$$
$$= \Phi(1) - [1 - \Phi(0.5)] = 0.8413 - 1 + 0.6915 = 0.5328$$

$$P\{|X| > 2\} = 1 - P\{-2 \leq X \leq 2\}$$
$$= 1 - \left[\Phi\left(\frac{2-3}{2}\right) - \Phi\left(\frac{-2-3}{2}\right)\right]$$
$$= 1 - [\Phi(-0.5) - \Phi(-2.5)] = 1 - [0.3085 - 0.0062] = 1 - 0.3023 = 0.6977$$

**【例4】** 设 $X \sim N(\mu, \sigma^2)$，$P\{X \leq -1.6\} = 0.036$，$P\{X \leq 5.9\} = 0.758$，求 $\mu$ 和 $\sigma$。

**解：**
$$\Phi\left(\frac{-1.6-\mu}{\sigma}\right) = 0.036 \Rightarrow \frac{-1.6-\mu}{\sigma} = \Phi^{-1}(0.036) \approx -1.80$$

$$\Phi\left(\frac{5.9-\mu}{\sigma}\right) = 0.758 \Rightarrow \frac{5.9-\mu}{\sigma} = \Phi^{-1}(0.758) \approx 0.70$$

联立方程：
$$\frac{-1.6-\mu}{\sigma} = -1.80 \quad \cdots (1)$$
$$\frac{5.9-\mu}{\sigma} = 0.70 \quad \cdots (2)$$

由 $(2) - (1)$：$\dfrac{7.5}{\sigma} = 2.50$，得 $\sigma = 3$

代入 $(2)$：$\dfrac{5.9-\mu}{3} = 0.70$，得 $\mu = 5.9 - 2.1 = 3.8$

所以 $X \sim N(3.8, 9)$。

**【例5】** 设 $X \sim N(0, 1)$，$P\{X > u_\alpha\} = \alpha$（$0 < \alpha < 1$），则 $u_\alpha = \Phi^{-1}(1-\alpha)$，求 $u_{0.025}$。

**解：** $P\{X > u_{0.025}\} = 0.025$，即 $\Phi(u_{0.025}) = 0.975$

由标准正态分布表：$u_{0.025} = 1.96$

---

## 五、分布函数的进一步讨论

### 5.1 分布函数与密度函数的关系总结

| | 离散型 | 连续型 |
|---|---|---|
| 基本描述 | 分布律 $P\{X=x_k\}=p_k$ | 密度函数 $f(x)$ |
| 分布函数 | $F(x)=\sum_{x_k \leq x} p_k$ | $F(x)=\int_{-\infty}^x f(t)dt$ |
| 求概率 | $P\{a<X\leq b\}=\sum_{a<x_k\leq b}p_k$ | $P\{a<X\leq b\}=\int_a^b f(x)dx$ |
| $F(x)$ 的性质 | 单调不减、右连续 | 单调不减、连续（绝对连续） |

### 5.2 分布函数的通用性质

无论离散型还是连续型，分布函数 $F(x)$ 都满足：

1. **单调不减性：** 若 $x_1 < x_2$，则 $F(x_1) \leq F(x_2)$
2. **有界性：** $0 \leq F(x) \leq 1$
3. **极限性质：** $F(-\infty) = 0$，$F(+\infty) = 1$
4. **右连续性：** $F(x) = F(x^+)$

---

## 六、常见连续型分布对比表 ⭐⭐⭐⭐⭐

| 分布 | 记号 | 密度函数 $f(x)$ | $E(X)$ | $D(X)$ |
|------|------|-----------------|--------|--------|
| 均匀分布 | $U(a,b)$ | $\frac{1}{b-a}$，$a \leq x \leq b$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| 指数分布 | $E(\lambda)$ | $\lambda e^{-\lambda x}$，$x > 0$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |
| 正态分布 | $N(\mu,\sigma^2)$ | $\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $\mu$ | $\sigma^2$ |
| 标准正态 | $N(0,1)$ | $\frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}$ | $0$ | $1$ |

---

## 七、综合例题

**【例6】（均匀分布的条件概率）**

设 $X \sim U(0, 5)$，求方程 $4x^2 + 4Xx + X + 2 = 0$ 有实根的概率。

**解：** 有实根的条件是判别式 $\Delta \geq 0$：
$$\Delta = (4X)^2 - 4 \times 4 \times (X+2) = 16X^2 - 16X - 32 = 16(X^2 - X - 2) \geq 0$$
$$X^2 - X - 2 \geq 0 \Rightarrow (X-2)(X+1) \geq 0$$

所以 $X \geq 2$ 或 $X \leq -1$。由于 $X \sim U(0, 5)$，只需 $X \geq 2$：

$$P\{X \geq 2\} = \frac{5 - 2}{5 - 0} = \frac{3}{5}$$

**【例7】（指数分布的综合应用）**

某元件寿命 $X \sim E(0.01)$（单位：小时）。独立使用 5 个这样的元件，求至少有 3 个超过 100 小时的概率。

**解：** 单个元件：
$$P\{X > 100\} = e^{-0.01 \times 100} = e^{-1} \approx 0.3679$$

设 $Y$ 为 5 个中超过 100 小时的个数，$Y \sim B(5, e^{-1})$：

$$P\{Y \geq 3\} = \binom{5}{3}p^3(1-p)^2 + \binom{5}{4}p^4(1-p) + \binom{5}{5}p^5$$

其中 $p = e^{-1} \approx 0.3679$，$1-p \approx 0.6321$：

$$P\{Y \geq 3\} \approx 10 \times 0.0498 \times 0.3996 + 5 \times 0.0183 \times 0.6321 + 0.0067$$
$$\approx 0.1990 + 0.0579 + 0.0067 = 0.2636$$

**【例8】（正态分布的标准化综合）**

设 $X \sim N(2, \sigma^2)$，且 $P\{2 < X < 4\} = 0.3$，求 $P\{X < 0\}$。

**解：** 标准化 $Z = \dfrac{X - 2}{\sigma} \sim N(0, 1)$

$$P\{2 < X < 4\} = \Phi\left(\frac{4-2}{\sigma}\right) - \Phi\left(\frac{2-2}{\sigma}\right) = \Phi\left(\frac{2}{\sigma}\right) - \Phi(0) = \Phi\left(\frac{2}{\sigma}\right) - 0.5 = 0.3$$

$$\Phi\left(\frac{2}{\sigma}\right) = 0.8$$

由正态分布的对称性：
$$P\{X < 0\} = \Phi\left(\frac{0-2}{\sigma}\right) = \Phi\left(-\frac{2}{\sigma}\right) = 1 - \Phi\left(\frac{2}{\sigma}\right) = 1 - 0.8 = 0.2$$

---

## 八、易错点与考试陷阱

### ⚠️ 易错点1：密度函数的值不是概率

$f(x)$ 可以大于1！$f(x)$ 只有在积分后才是概率：
$$P\{a < X < b\} = \int_a^b f(x) \, dx$$

### ⚠️ 易错点2：连续型随机变量单点概率为零

$P\{X = a\} = 0$ 对任意 $a$ 成立，因此：
$$P\{a \leq X \leq b\} = P\{a < X < b\} = \int_a^b f(x) \, dx$$

但这**不意味着** $\{X = a\}$ 是不可能事件！

### ⚠️ 易错点3：指数分布的无记忆性条件

无记忆性的表达式中 $s, t > 0$，不是 $s, t \geq 0$。

### ⚠️ 易错点4：正态分布标准化

$X \sim N(\mu, \sigma^2)$ 标准化为 $Z = \dfrac{X - \mu}{\sigma}$，**不要**误写为 $Z = \dfrac{X - \mu}{\sigma^2}$。

### ⚠️ 易错点5：$\Phi$ 函数的计算

$$\Phi(-x) = 1 - \Phi(x)$$
$$P\{a < X < b\} = \Phi\left(\frac{b-\mu}{\sigma}\right) - \Phi\left(\frac{a-\mu}{\sigma}\right)$$

考试中容易忘记减去 $\Phi\left(\dfrac{a-\mu}{\sigma}\right)$ 或搞错正负号。

---

## 九、本讲知识框架图

```
连续型随机变量
├── 基本概念
│   ├── 密度函数 f(x) ≥ 0, ∫f(x)dx = 1
│   ├── 分布函数 F(x) = ∫₋∞ˣ f(t)dt
│   └── P{a<X<b} = ∫ₐᵇ f(x)dx
├── 均匀分布 U(a,b) ⭐⭐⭐
│   ├── f(x) = 1/(b-a)
│   ├── E(X) = (a+b)/2
│   └── D(X) = (b-a)²/12
├── 指数分布 E(λ) ⭐⭐⭐⭐
│   ├── f(x) = λe^{-λx}, x>0
│   ├── E(X) = 1/λ, D(X) = 1/λ²
│   ├── 无记忆性 ⭐
│   └── 寿命模型、泊松过程间隔
├── 正态分布 N(μ,σ²) ⭐⭐⭐⭐⭐
│   ├── 标准正态 N(0,1): φ(x), Φ(x)
│   ├── 标准化: Z=(X-μ)/σ ~ N(0,1)
│   ├── Φ(-x) = 1-Φ(x)
│   ├── 线性变换: aX+b ~ N(aμ+b, a²σ²)
│   └── 3σ法则
└── 无记忆性
    ├── 离散: 几何分布
    └── 连续: 指数分布
```

---

## 十、习题精选

**习题1：** 设 $X \sim U(1, 6)$，求方程 $x^2 + Xx + 1 = 0$ 有实根的概率。

**解：** $\Delta = X^2 - 4 \geq 0$，即 $X \geq 2$ 或 $X \leq -2$。由 $X \sim U(1,6)$：
$$P\{X \geq 2\} = \frac{6-2}{6-1} = \frac{4}{5}$$

**习题2：** 设 $X \sim E(2)$，求 $P\{X > 1\}$ 和 $P\{X > 3 | X > 2\}$。

**解：**
$$P\{X > 1\} = e^{-2} \approx 0.1353$$
$$P\{X > 3 | X > 2\} = P\{X > 1\} = e^{-2} \approx 0.1353 \quad \text{（无记忆性）}$$

**习题3：** 设 $X \sim N(10, 4)$，求 $P\{8 < X < 14\}$。

**解：** $\mu = 10$，$\sigma = 2$
$$P\{8 < X < 14\} = \Phi\left(\frac{14-10}{2}\right) - \Phi\left(\frac{8-10}{2}\right) = \Phi(2) - \Phi(-1)$$
$$= 0.9772 - 0.1587 = 0.8185$$

**习题4：** 设 $X \sim N(\mu, \sigma^2)$，$P\{X < -5\} = 0.6915$，$P\{X < 2\} = 0.8413$，求 $\mu$ 和 $\sigma$。

**解：**
$$\Phi\left(\frac{-5-\mu}{\sigma}\right) = 0.6915 \Rightarrow \frac{-5-\mu}{\sigma} \approx 0.50$$
$$\Phi\left(\frac{2-\mu}{\sigma}\right) = 0.8413 \Rightarrow \frac{2-\mu}{\sigma} \approx 1.00$$

解方程组：$\mu = -8$，$\sigma = 6$，即 $X \sim N(-8, 36)$。

---

## 十一、考研真题考点分析

| 题型 | 考点 | 频率 |
|------|------|------|
| 填空题 | 正态分布概率计算（标准化） | 极高 |
| 选择题 | 指数分布无记忆性 | 高频 |
| 解答题 | 正态分布参数确定 | 高频 |
| 选择题 | 均匀分布的概率计算 | 中频 |
| 解答题 | 密度函数与分布函数互求 | 高频 |
| 填空题 | $\Phi$ 函数的性质应用 | 极高 |

> **备考建议：** 正态分布是考研概率论中最重要的分布，标准化方法必须熟练掌握。$\Phi$ 函数的常用值和对称性 $\Phi(-x)=1-\Phi(x)$ 是解题的基础。指数分布的无记忆性几乎每年都会以选择题形式出现。

---

> **下一讲预告：** [[01_数学一/03_概率论/01_笔记/04_数一笔记_概率/02-随机变量及其分布/Lecture 6：随机变量函数的分布]] —— 分布函数法和公式法求 $Y = g(X)$ 的分布
