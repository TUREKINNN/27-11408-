---
title: Lecture 06 - 数理统计的基本概念
subject: 概率论与数理统计
chapter: 第六章
lecture: 06
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 06: 数理统计的基本概念

## 一、总体与样本

### 1.1 总体

<span style="background-color: #ccc1d9">**定义（总体）**</span> 研究对象的全体称为**总体**，总体中的每个元素称为**个体**。

在数理统计中，我们关心的是个体的某个数量指标，因此总体可以看作是这个数量指标的所有可能取值的集合，通常用随机变量 $X$ 表示总体。

### 1.2 样本

<span style="background-color: #ccc1d9">**定义（样本）**</span> 从总体中抽取的一部分个体称为**样本**，样本中所含个体的数量称为**样本容量**。

设 $X_1, X_2, \cdots, X_n$ 是从总体 $X$ 中抽取的样本，如果满足：
1. **独立性**：$X_1, X_2, \cdots, X_n$ 相互独立
2. **同分布性**：每个 $X_i$ 与总体 $X$ 同分布

则称 $X_1, X_2, \cdots, X_n$ 为**简单随机样本**，简称为样本。

### 1.3 样本值

样本 $X_1, X_2, \cdots, X_n$ 的一次具体观测值 $x_1, x_2, \cdots, x_n$ 称为**样本值**。

---

## 二、统计量

### 2.1 统计量的定义

<span style="background-color: #ccc1d9">**定义（统计量）**</span> 设 $X_1, X_2, \cdots, X_n$ 是来自总体 $X$ 的样本，若函数 $g(X_1, X_2, \cdots, X_n)$ 中不含未知参数，则称 $g(X_1, X_2, \cdots, X_n)$ 为**统计量**。

### 2.2 常用统计量

#### (1) 样本均值

$$\overline{X} = \frac{1}{n} \sum_{i=1}^{n} X_i$$

#### (2) 样本方差

$$S^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \overline{X})^2$$

**样本标准差**：$S = \sqrt{S^2}$

#### (3) 样本矩

- **$k$ 阶样本原点矩**：$A_k = \frac{1}{n} \sum_{i=1}^{n} X_i^k$
- **$k$ 阶样本中心矩**：$B_k = \frac{1}{n} \sum_{i=1}^{n} (X_i - \overline{X})^k$

#### (4) 顺序统计量

将样本 $X_1, X_2, \cdots, X_n$ 按从小到大的顺序排列：

$$X_{(1)} \leq X_{(2)} \leq \cdots \leq X_{(n)}$$

- $X_{(1)} = \min\{X_1, X_2, \cdots, X_n\}$：最小顺序统计量
- $X_{(n)} = \max\{X_1, X_2, \cdots, X_n\}$：最大顺序统计量

---

## 三、三大抽样分布

### 3.1 $\chi^2$ 分布

<span style="background-color: #ccc1d9">**定义（$\chi^2$ 分布）**</span> 设 $X_1, X_2, \cdots, X_n$ 独立同分布于 $N(0, 1)$，则称

$$\chi^2 = X_1^2 + X_2^2 + \cdots + X_n^2$$

服从自由度为 $n$ 的 **$\chi^2$ 分布**，记为 $\chi^2 \sim \chi^2(n)$。

**概率密度**：

$$f(x) = \begin{cases}
\frac{1}{2^{n/2}\Gamma(n/2)} x^{n/2-1} e^{-x/2}, & x > 0 \\
0, & x \leq 0
\end{cases}$$

**性质**：

1. **可加性**：若 $\chi_1^2 \sim \chi^2(n_1), \chi_2^2 \sim \chi^2(n_2)$ 独立，则 $\chi_1^2 + \chi_2^2 \sim \chi^2(n_1 + n_2)$
2. **期望与方差**：若 $\chi^2 \sim \chi^2(n)$，则 $E(\chi^2) = n, D(\chi^2) = 2n$

### 3.2 $t$ 分布

<span style="background-color: #ccc1d9">**定义（$t$ 分布）**</span> 设 $X \sim N(0, 1), Y \sim \chi^2(n)$ 且 $X$ 与 $Y$ 独立，则称

$$t = \frac{X}{\sqrt{Y/n}}$$

服从自由度为 $n$ 的 **$t$ 分布**，记为 $t \sim t(n)$。

**概率密度**：

$$f(x) = \frac{\Gamma((n+1)/2)}{\sqrt{n\pi}\Gamma(n/2)} \left(1 + \frac{x^2}{n}\right)^{-(n+1)/2}$$

**性质**：

1. **对称性**：$t$ 分布关于 $x = 0$ 对称
2. **极限分布**：当 $n \to \infty$ 时，$t(n)$ 分布趋近于标准正态分布 $N(0, 1)$

### 3.3 $F$ 分布

<span style="background-color: #ccc1d9">**定义（$F$ 分布）**</span> 设 $X \sim \chi^2(n_1), Y \sim \chi^2(n_2)$ 且 $X$ 与 $Y$ 独立，则称

$$F = \frac{X/n_1}{Y/n_2}$$

服从自由度为 $(n_1, n_2)$ 的 **$F$ 分布**，记为 $F \sim F(n_1, n_2)$。

**性质**：

1. **倒数性质**：若 $F \sim F(n_1, n_2)$，则 $\frac{1}{F} \sim F(n_2, n_1)$
2. **与 $t$ 分布的关系**：若 $t \sim t(n)$，则 $t^2 \sim F(1, n)$

---

## 四、正态总体下的抽样分布

### 4.1 单个正态总体的抽样分布

设 $X_1, X_2, \cdots, X_n$ 是来自总体 $X \sim N(\mu, \sigma^2)$ 的样本，则：

1. **样本均值**：$\overline{X} \sim N\left(\mu, \frac{\sigma^2}{n}\right)$
2. **标准化样本均值**：$\frac{\overline{X} - \mu}{\sigma/\sqrt{n}} \sim N(0, 1)$
3. **样本方差与 $\chi^2$ 分布**：$\frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$
4. **$\overline{X}$ 与 $S^2$ 独立**：$\overline{X}$ 与 $S^2$ 相互独立
5. **$t$ 分布**：$\frac{\overline{X} - \mu}{S/\sqrt{n}} \sim t(n-1)$

### 4.2 两个正态总体的抽样分布

设 $X_1, X_2, \cdots, X_{n_1}$ 是来自总体 $X \sim N(\mu_1, \sigma_1^2)$ 的样本，$Y_1, Y_2, \cdots, Y_{n_2}$ 是来自总体 $Y \sim N(\mu_2, \sigma_2^2)$ 的样本，且两样本独立，则：

1. **样本均值差**：$\overline{X} - \overline{Y} \sim N\left(\mu_1 - \mu_2, \frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}\right)$
2. **$F$ 分布**：$\frac{S_1^2/\sigma_1^2}{S_2^2/\sigma_2^2} \sim F(n_1-1, n_2-1)$
3. **当 $\sigma_1^2 = \sigma_2^2 = \sigma^2$ 时**：

$$\frac{(\overline{X} - \overline{Y}) - (\mu_1 - \mu_2)}{S_w \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}} \sim t(n_1 + n_2 - 2)$$

其中 $S_w^2 = \frac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1 + n_2 - 2}$。

---

## 五、典型例题

### 例题1：正态分布的线性组合（660题第556题）

**题目**：设相互独立的随机变量 $X_{1}, X_{2}, \cdots, X_{n}$ 均服从标准正态分布，记 $\overline{X} = \frac{1}{n} \sum_{i=1}^{n} X_{i}$，则随机变量 $X_{1} - \overline{X}$ 服从的分布及参数为 ____。

**思路**：计算期望和方差，判断分布类型。

**解答**：
$$E(X_1 - \overline{X}) = E(X_1) - E(\overline{X}) = 0 - 0 = 0$$

$$D(X_1 - \overline{X}) = D\left(\frac{n-1}{n}X_1 - \frac{1}{n}\sum_{i=2}^{n}X_i\right)$$

$$= \left(\frac{n-1}{n}\right)^2 D(X_1) + \sum_{i=2}^{n} \left(\frac{1}{n}\right)^2 D(X_i)$$

$$= \frac{(n-1)^2}{n^2} + \frac{n-1}{n^2} = \frac{n-1}{n}$$

由于 $X_1 - \overline{X}$ 是正态变量的线性组合，仍服从正态分布：

$$X_1 - \overline{X} \sim N\left(0, \frac{n-1}{n}\right)$$

**总结**：正态变量的线性组合仍为正态分布。

---

### 例题2：最小顺序统计量的概率密度（660题第557题）

**题目**：设总体 $X$ 服从区间 $[0,1]$ 上的均匀分布，$X_{1}, X_{2}, \cdots, X_{n}$ 为从 $X$ 中抽得的简单随机样本，$Y = \min_{1 \leqslant i \leqslant n} X_{i}$，则 $Y$ 的概率密度 $f_{Y}(y) =$ ____。

**思路**：利用最小值分布的公式。

**解答**：
$X \sim U(0,1)$，则 $F_X(x) = x, 0 < x < 1$

$$F_Y(y) = P\{\min(X_1, \cdots, X_n) \leq y\} = 1 - P\{\min(X_1, \cdots, X_n) > y\}$$

$$= 1 - P\{X_1 > y, \cdots, X_n > y\} = 1 - [1 - F_X(y)]^n$$

$$= 1 - (1 - y)^n, 0 < y < 1$$

$$f_Y(y) = F_Y'(y) = n(1 - y)^{n-1}, 0 < y < 1$$

**总结**：最小值分布的公式 $F_{\min}(x) = 1 - [1 - F(x)]^n$。

---

### 例题3：样本方差的期望（660题第558题）

**题目**：设总体 $X$ 的概率密度函数为 $f(x)=\frac{1}{2}\mathrm{e}^{-|x-\mu|}(-\infty<x<+\infty)$，$X_{1}, X_{2}, \cdots, X_{n}$ 为总体 $X$ 的简单随机样本，其样本方差为 $S^{2}$，则 $E(S^{2})=$ ____。

**思路**：利用样本方差的性质 $E(S^2) = D(X)$。

**解答**：
$X$ 的概率密度为拉普拉斯分布，$E(X) = \mu$

$$D(X) = E(X^2) - [E(X)]^2 = E(X^2) - \mu^2$$

$$E(X^2) = \int_{-\infty}^{+\infty} x^2 \cdot \frac{1}{2}e^{-|x-\mu|} dx$$

令 $t = x - \mu$：

$$= \int_{-\infty}^{+\infty} (t + \mu)^2 \cdot \frac{1}{2}e^{-|t|} dt = \frac{1}{2}\int_{-\infty}^{+\infty} (t^2 + 2\mu t + \mu^2)e^{-|t|} dt$$

$$= \frac{1}{2}\int_{-\infty}^{+\infty} t^2 e^{-|t|} dt + \mu^2 = \int_{0}^{+\infty} t^2 e^{-t} dt + \mu^2 = 2 + \mu^2$$

$$D(X) = 2 + \mu^2 - \mu^2 = 2$$

由于 $E(S^2) = D(X)$，故 $E(S^2) = 2$

**总结**：样本方差是总体方差的无偏估计。

---

### 例题4：$F$ 分布的性质（660题第559题）

**题目**：设总体 $X \sim F(n, n)$，且 $P\{|X| < A\} = 0.3, A$ 为一常数，则 $P\left\{X < \frac{1}{A}\right\} =$ ____。

**思路**：利用 $F$ 分布的倒数性质。

**解答**：
若 $X \sim F(n, n)$，则 $\frac{1}{X} \sim F(n, n)$，即 $X$ 与 $\frac{1}{X}$ 同分布。

$$P\{X < A\} = P\left\{\frac{1}{X} < A\right\} = P\left\{X > \frac{1}{A}\right\}$$

$$P\{|X| < A\} = P\{-A < X < A\} = P\{0 < X < A\} = 0.3$$

$$P\left\{X < \frac{1}{A}\right\} = 1 - P\left\{X \geq \frac{1}{A}\right\} = 1 - P\{X < A\} = 1 - 0.3 = 0.7$$

**总结**：$F(n,n)$ 分布中 $X$ 与 $\frac{1}{X}$ 同分布。

---

### 例题5：$\chi^2$ 分布的应用（660题第560题）

**题目**：总体 $X \sim N(\mu, \sigma^{2})(\sigma > 0)$，$X_{1}, X_{2}, \cdots, X_{n}$ 为从 $X$ 中抽得的简单随机样本，$\overline{X}$ 为样本均值，则 $\frac{1}{\sigma^{2}} \sum_{i=1}^{n} (X_{i} - \mu)^{2} \sim$ ____，$\frac{1}{\sigma^{2}} \sum_{i=1}^{n} (X_{i} - \overline{X})^{2} \sim$ ____。

**思路**：利用 $\chi^2$ 分布的定义。

**解答**：
1. $\frac{X_i - \mu}{\sigma} \sim N(0,1)$，且相互独立，由 $\chi^2$ 分布定义：

$$\frac{1}{\sigma^2}\sum_{i=1}^{n}(X_i - \mu)^2 = \sum_{i=1}^{n}\left(\frac{X_i - \mu}{\sigma}\right)^2 \sim \chi^2(n)$$

2. 由抽样分布定理，$\frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$，而：

$$\frac{1}{\sigma^2}\sum_{i=1}^{n}(X_i - \overline{X})^2 = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$$

**总结**：注意自由度的区别。

---

### 例题6：$t$ 分布与 $F$ 分布的关系（660题第561题）

**题目**：设随机变量 $X \sim t(n), Y \sim F(1, n)$，常数 $c$ 满足 $P\{X > c\} = 0.6$，则 $P\{Y > c^{2}\} =$ ____。

**思路**：利用 $t$ 分布与 $F$ 分布的关系。

**解答**：
若 $X \sim t(n)$，则 $X^2 \sim F(1, n)$，即 $Y = X^2$

$$P\{Y > c^2\} = P\{X^2 > c^2\} = P\{X > c \text{ 或 } X < -c\}$$

由于 $t$ 分布关于原点对称：

$$P\{X < -c\} = P\{X > c\} = 0.6$$

$$P\{Y > c^2\} = 0.6 + 0.6 = 1.2$$

但概率不能超过1，说明 $c < 0$（因为 $P\{X > c\} = 0.6 > 0.5$），此时：

$$P\{X^2 > c^2\} = P\{X > |c|\} + P\{X < -|c|\} = 2P\{X > |c|\}$$

又 $P\{X > c\} = 0.6$，则 $P\{X > |c|\} = P\{X < c\} = 0.4$

$$P\{Y > c^2\} = 2 \times 0.4 = 0.8$$

**总结**：$t(n)^2 = F(1,n)$，注意 $t$ 分布的对称性。

---

### 例题7：正态分布的参数识别（660题第562题）

**题目**：设总体 $X$ 的概率密度为 $f(x) = Ae^{-x^2 + x}, x \in \mathbb{R}$，其中 $A$ 为待定常数。从 $X$ 中抽得简单随机样本：$X_{1}, \cdots, X_{5}, \overline{X}$ 为样本均值，则 $A =$ ____，$E(\overline{X}) =$ ____，$D(\overline{X}) =$ ____。

**思路**：将概率密度化为正态分布的标准形式。

**解答**：
$$f(x) = A e^{-x^2 + x} = A e^{-(x^2 - x)} = A e^{-\left[(x - 1/2)^2 - 1/4\right]} = A e^{1/4} e^{-(x - 1/2)^2}$$

正态分布 $N(\mu, \sigma^2)$ 的概率密度为 $\frac{1}{\sqrt{2\pi}\sigma} e^{-(x-\mu)^2/(2\sigma^2)}$

对比得：$2\sigma^2 = 1 \Rightarrow \sigma^2 = \frac{1}{2}, \mu = \frac{1}{2}$

$$A e^{1/4} = \frac{1}{\sqrt{2\pi}\sqrt{1/2}} = \frac{1}{\sqrt{\pi}} \Rightarrow A = \frac{e^{-1/4}}{\sqrt{\pi}}$$

$$E(\overline{X}) = E(X) = \mu = \frac{1}{2}$$

$$D(\overline{X}) = \frac{D(X)}{n} = \frac{\sigma^2}{5} = \frac{1/2}{5} = \frac{1}{10}$$

**总结**：通过配方法识别正态分布的参数。

---

## 六、解题方法总结

### 6.1 主要方法

| 类型 | 方法 |
|------|------|
| 统计量判断 | 不含未知参数 |
| $\chi^2$ 分布 | 标准正态变量的平方和 |
| $t$ 分布 | 标准正态变量除以 $\chi^2$ 变量的平方根 |
| $F$ 分布 | 两个独立 $\chi^2$ 变量的比值 |
| 正态总体抽样分布 | 记住关键结论 |

### 6.2 常见易错点

1. **样本方差的自由度**：$S^2 = \frac{1}{n-1}\sum(X_i - \overline{X})^2$，不是 $\frac{1}{n}$
2. **$\chi^2$ 分布的自由度**：$\frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$，不是 $\chi^2(n)$
3. **$t$ 分布与正态分布的关系**：$n \to \infty$ 时 $t(n) \to N(0,1)$
4. **$F$ 分布的自由度顺序**：$F(n_1, n_2) \neq F(n_2, n_1)$

---

## 七、练习题精选

### 基础练习

1. 设 $X_1, X_2, X_3$ 是来自 $N(0,1)$ 的样本，求 $P\{\overline{X} > 0\}$。

2. 设 $X \sim \chi^2(10)$，求 $E(X)$ 和 $D(X)$。

### 提高练习

3. 设 $X \sim t(8)$，求 $P\{X^2 > 4\}$。

4. 设 $X \sim F(5, 10)$，且 $P\{X > a\} = 0.05$，求 $P\left\{\frac{1}{X} > a\right\}$。

---

## 参考答案提示

1. $P\{\overline{X} > 0\} = 0.5$（提示：$\overline{X} \sim N(0, 1/3)$）

2. $E(X) = 10$，$D(X) = 20$（提示：$\chi^2(n)$ 的期望和方差公式）

3. $P\{X^2 > 4\} = P\{X > 2\} + P\{X < -2\}$（提示：$X^2 \sim F(1, 8)$）

4. $P\left\{\frac{1}{X} > a\right\} = P\{X < 1/a\} = 1 - P\{X \geq 1/a\}$（提示：$\frac{1}{X} \sim F(10, 5)$）

---

> **注**：本 Lecture 内容涵盖总体、样本、统计量、三大抽样分布及正态总体下的抽样分布。建议结合《基础过关660题》第556-562题进行练习巩固。

### 补充：分位数的概念

<span style="background-color: #ccc1d9">**分位数的定义**</span>

设随机变量 $X$ 的分布函数为 $F(x)$，对于给定的概率 $p \in (0,1)$，满足

$$F(x_p) = P\{X \leq x_p\} = p$$

的 $x_p$ 称为 $X$ 的 $p$ 分位数（下侧分位数）。

**上侧分位数**：满足 $P\{X > x^p\} = p$ 的 $x^p$ 称为上侧 $p$ 分位数。

**常用分位数**：
- 标准正态分布：$z_{\alpha/2}$，满足 $\Phi(z_{\alpha/2}) = 1 - \alpha/2$
- $t$ 分布：$t_{\alpha}(n)$，满足 $P\{t(n) > t_{\alpha}(n)\} = \alpha$
- $\chi^2$ 分布：$\chi^2_{\alpha}(n)$，满足 $P\{\chi^2(n) > \chi^2_{\alpha}(n)\} = \alpha$
- $F$ 分布：$F_{\alpha}(n_1, n_2)$，满足 $P\{F(n_1,n_2) > F_{\alpha}(n_1,n_2)\} = \alpha$
