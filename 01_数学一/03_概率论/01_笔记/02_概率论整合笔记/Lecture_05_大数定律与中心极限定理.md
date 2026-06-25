---
title: Lecture 05 - 大数定律与中心极限定理
subject: 概率论与数理统计
chapter: 第五章
lecture: 05
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 05: 大数定律与中心极限定理

## 一、切比雪夫不等式

### 1.1 切比雪夫不等式的表述

<span style="background-color: #8db3e2">**定理（切比雪夫不等式）**</span> 设随机变量 $X$ 的期望 $E(X) = \mu$，方差 $D(X) = \sigma^2$，则对任意 $\varepsilon > 0$，有

$$P\{|X - \mu| \geq \varepsilon\} \leq \frac{\sigma^2}{\varepsilon^2}$$

或等价地

$$P\{|X - \mu| < \varepsilon\} \geq 1 - \frac{\sigma^2}{\varepsilon^2}$$

### 1.2 切比雪夫不等式的意义

切比雪夫不等式给出了随机变量偏离其期望的概率的上界估计，不需要知道随机变量的具体分布，只需知道期望和方差即可。

---

## 二、大数定律

### 2.1 依概率收敛

<span style="background-color: #ccc1d9">**定义（依概率收敛）**</span> 设 $X_1, X_2, \cdots, X_n, \cdots$ 是一列随机变量，$a$ 是一个常数。若对任意 $\varepsilon > 0$，有

$$\lim_{n \to \infty} P\{|X_n - a| \geq \varepsilon\} = 0$$

则称 $\{X_n\}$ **依概率收敛**于 $a$，记为 $X_n \stackrel{P}{\to} a$。

### 2.2 切比雪夫大数定律

<span style="background-color: #8db3e2">**定理（切比雪夫大数定律）**</span> 设 $X_1, X_2, \cdots, X_n, \cdots$ 是两两不相关的随机变量序列，每个 $X_i$ 的期望 $E(X_i) = \mu_i$，方差 $D(X_i) = \sigma_i^2$，且存在常数 $C$，使得 $\sigma_i^2 \leq C$ 对所有 $i$ 成立，则对任意 $\varepsilon > 0$，有

$$\lim_{n \to \infty} P\left\{\left|\frac{1}{n}\sum_{i=1}^{n}X_i - \frac{1}{n}\sum_{i=1}^{n}\mu_i\right| \geq \varepsilon\right\} = 0$$

即样本均值依概率收敛于总体均值的平均。

### 2.3 伯努利大数定律

<span style="background-color: #8db3e2">**定理（伯努利大数定律）**</span> 设 $n_A$ 是 $n$ 次独立重复伯努利试验中事件 $A$ 发生的次数，$p$ 是事件 $A$ 在每次试验中发生的概率，则对任意 $\varepsilon > 0$，有

$$\lim_{n \to \infty} P\left\{\left|\frac{n_A}{n} - p\right| \geq \varepsilon\right\} = 0$$

即频率依概率收敛于概率。

### 2.4 辛钦大数定律

<span style="background-color: #8db3e2">**定理（辛钦大数定律）**</span> 设 $X_1, X_2, \cdots, X_n, \cdots$ 是独立同分布的随机变量序列，且期望 $E(X_i) = \mu$ 存在，则对任意 $\varepsilon > 0$，有

$$\lim_{n \to \infty} P\left\{\left|\frac{1}{n}\sum_{i=1}^{n}X_i - \mu\right| \geq \varepsilon\right\} = 0$$

即样本均值依概率收敛于总体均值。

**注**：辛钦大数定律不要求方差存在，这是它与切比雪夫大数定律的区别。

---

## 三、中心极限定理

### 3.1 列维-林德伯格定理（独立同分布中心极限定理）

<span style="background-color: #8db3e2">**定理（列维-林德伯格定理）**</span> 设 $X_1, X_2, \cdots, X_n, \cdots$ 是独立同分布的随机变量序列，$E(X_i) = \mu$，$D(X_i) = \sigma^2 > 0$，则对任意实数 $x$，有

$$\lim_{n \to \infty} P\left\{\frac{\sum_{i=1}^{n}X_i - n\mu}{\sqrt{n}\sigma} \leq x\right\} = \Phi(x)$$

其中 $\Phi(x)$ 是标准正态分布的分布函数。

**意义**：当 $n$ 充分大时，独立同分布的随机变量之和 $\sum_{i=1}^{n}X_i$ 近似服从正态分布 $N(n\mu, n\sigma^2)$。

### 3.2 棣莫弗-拉普拉斯定理（二项分布的正态近似）

<span style="background-color: #8db3e2">**定理（棣莫弗-拉普拉斯定理）**</span> 设 $Y_n \sim B(n, p)$，则对任意实数 $x$，有

$$\lim_{n \to \infty} P\left\{\frac{Y_n - np}{\sqrt{np(1-p)}} \leq x\right\} = \Phi(x)$$

**意义**：当 $n$ 充分大时，二项分布 $B(n, p)$ 近似服从正态分布 $N(np, np(1-p))$。

### 3.3 中心极限定理的应用

中心极限定理的主要应用：

1. **近似计算概率**：当 $n$ 很大时，利用正态分布近似计算独立同分布随机变量之和的概率
2. **误差分析**：在测量误差分析中，多个独立误差之和近似服从正态分布
3. **质量控制**：在工业生产中，产品质量指标的波动可近似用正态分布描述

---

## 四、典型例题

### 例题1：切比雪夫不等式的应用（660题第551题）

**题目**：设随机变量 $X$ 在 $[-1, b]$ 上服从均匀分布，其中 $b$ 是未知常数，根据切比雪夫不等式有 $P\{|X - 1| \geq \varepsilon\} \leq \frac{1}{3}$，则 $\varepsilon =$ ____。

**思路**：利用均匀分布的期望和方差，结合切比雪夫不等式。

**解答**：
$X \sim U(-1, b)$，则 $E(X) = \frac{-1 + b}{2}$，$D(X) = \frac{(b + 1)^2}{12}$

由题意 $E(X) = 1$，则 $\frac{-1 + b}{2} = 1 \Rightarrow b = 3$

$$D(X) = \frac{(3 + 1)^2}{12} = \frac{16}{12} = \frac{4}{3}$$

由切比雪夫不等式：$P\{|X - 1| \geq \varepsilon\} \leq \frac{D(X)}{\varepsilon^2} = \frac{4/3}{\varepsilon^2} = \frac{1}{3}$

$$\frac{4}{3\varepsilon^2} = \frac{1}{3} \Rightarrow \varepsilon^2 = 4 \Rightarrow \varepsilon = 2$$

**总结**：先确定参数，再应用切比雪夫不等式。

---

### 例题2：大数定律的应用（660题第552题）

**题目**：将一个骰子重复掷 $n$ 次，每次掷出的点数依次为 $X_{1}, \cdots, X_{n}$。则当 $n \to \infty$ 时，$\overline{X} = \frac{1}{n} \sum_{i=1}^{n} X_{i}$ 依概率收敛于 ____。

**思路**：利用辛钦大数定律。

**解答**：
$X_i$ 独立同分布，$E(X_i) = \frac{1+2+3+4+5+6}{6} = \frac{21}{6} = \frac{7}{2}$

由辛钦大数定律，$\overline{X} \stackrel{P}{\to} E(X_i) = \frac{7}{2}$

**总结**：辛钦大数定律表明样本均值依概率收敛于总体均值。

---

### 例题3：中心极限定理的应用（660题第553题）

**题目**：设随机变量 $X_{1}, X_{2}, \cdots, X_{2n}, \cdots$ 独立且均服从指数分布 $E(\lambda)$，记 $Z_{i} = X_{2i} - X_{2i-1}, i = 1, 2, 3, \cdots$，则 $\sum_{i=1}^{n} Z_{i}$ 近似服从正态分布 $N(\_, \_)$。

**思路**：利用中心极限定理，先求期望和方差。

**解答**：
$X_i \sim E(\lambda)$，则 $E(X_i) = \frac{1}{\lambda}$，$D(X_i) = \frac{1}{\lambda^2}$

$$E(Z_i) = E(X_{2i}) - E(X_{2i-1}) = \frac{1}{\lambda} - \frac{1}{\lambda} = 0$$

$$D(Z_i) = D(X_{2i}) + D(X_{2i-1}) = \frac{1}{\lambda^2} + \frac{1}{\lambda^2} = \frac{2}{\lambda^2}$$

$\sum_{i=1}^{n} Z_i$ 的期望为 $0$，方差为 $\frac{2n}{\lambda^2}$

由中心极限定理，$\sum_{i=1}^{n} Z_i \dot{\sim} N\left(0, \frac{2n}{\lambda^2}\right)$

**总结**：中心极限定理要求计算和的期望和方差。

---

### 例题4：中心极限定理的应用（660题第554题）

**题目**：利用中心极限定理，$\lim_{n\to\infty}\sum_{k=0}^{n}\frac{n^{k}}{k!}e^{-n}=$ ____。

**思路**：将和式看作泊松分布的概率，利用中心极限定理。

**解答**：
设 $Y_n \sim P(n)$，则 $P\{Y_n \leq n\} = \sum_{k=0}^{n} \frac{n^k}{k!}e^{-n}$

由中心极限定理，当 $n \to \infty$ 时：

$$\frac{Y_n - n}{\sqrt{n}} \dot{\sim} N(0, 1)$$

$$P\{Y_n \leq n\} = P\left\{\frac{Y_n - n}{\sqrt{n}} \leq 0\right\} \to \Phi(0) = \frac{1}{2}$$

**总结**：泊松分布当 $\lambda$ 很大时可用正态分布近似。

---

### 例题5：中心极限定理的应用（660题第555题）

**题目**：某车间有 200 台车床，在生产期间内由于各种原因需停工。已知开工率为 0.6，且各台车床停工与否相互独立。而开工的车床需用电 $1 \mathrm{kW}$，应供该车间至少 ____ kW 电力才能以 $99.9\%$ 的可能性保证不会因供电不足而影响生产。（用中心极限定理作近似计算，$\Phi(3.1) = 0.999$）

**思路**：设开工车床数为 $X$，则 $X \sim B(n, p)$，利用中心极限定理近似。

**解答**：
$X \sim B(200, 0.6)$，则 $E(X) = np = 120$，$D(X) = np(1-p) = 48$

设供电量为 $k$ kW，则要求 $P\{X \leq k\} \geq 0.999$

由中心极限定理：

$$P\{X \leq k\} \approx \Phi\left(\frac{k - 120}{\sqrt{48}}\right) \geq 0.999$$

$$\frac{k - 120}{\sqrt{48}} \geq 3.1 \Rightarrow k \geq 120 + 3.1 \times \sqrt{48} \approx 120 + 21.27 = 141.27$$

取 $k = 141.3$ kW（进一法保留一位小数）

**总结**：二项分布的正态近似是中心极限定理的典型应用。

---

## 五、解题方法总结

### 5.1 主要方法

| 类型 | 方法 |
|------|------|
| 切比雪夫不等式 | $P\{|X-\mu| \geq \varepsilon\} \leq \frac{\sigma^2}{\varepsilon^2}$ |
| 大数定律 | 判断依概率收敛的极限值 |
| 中心极限定理 | 计算和的期望、方差，用正态分布近似 |
| 二项分布近似 | $B(n,p) \dot{\sim} N(np, np(1-p))$ |

### 5.2 常见易错点

1. **切比雪夫不等式的方向**：是概率的上界估计，不是精确值
2. **大数定律的条件**：切比雪夫大数定律要求方差有界，辛钦大数定律不要求方差
3. **中心极限定理的应用条件**：$n$ 要充分大，一般 $n \geq 30$
4. **连续性修正**：用正态分布近似离散分布时，可考虑连续性修正

---

## 六、练习题精选

### 基础练习

1. 设 $X \sim N(0, 1)$，用切比雪夫不等式估计 $P\{|X| \geq 2\}$。

2. 设 $X_1, X_2, \cdots, X_n$ 独立同分布，$E(X_i) = 1, D(X_i) = 4$，求 $\overline{X} = \frac{1}{n}\sum_{i=1}^{n}X_i$ 依概率收敛于何值。

### 提高练习

3. 设 $X_i \sim B(1, p)$，$i = 1, 2, \cdots, n$ 独立，求 $P\left\{\sum_{i=1}^{100}X_i \leq 55\right\}$ 的近似值（$p = 0.5$）。

4. 某保险公司有 10000 个客户，每个客户每年索赔的概率为 0.01，求索赔人数不超过 120 人的概率近似值。

---

## 参考答案提示

1. $P\{|X| \geq 2\} \leq \frac{1}{4}$（提示：$D(X) = 1$）

2. $\overline{X} \stackrel{P}{\to} 1$（提示：辛钦大数定律）

3. $P\left\{\sum X_i \leq 55\right\} \approx \Phi(1) \approx 0.8413$（提示：中心极限定理）

4. $P\{X \leq 120\} \approx \Phi(2) \approx 0.9772$（提示：$X \sim B(10000, 0.01)$）

---

> **注**：本 Lecture 内容涵盖切比雪夫不等式、大数定律和中心极限定理。建议结合《基础过关660题》第551-555题进行练习巩固。

### 补充：中心极限定理的深入理解

<span style="background-color: #8db3e2">**为什么中心极限定理重要？**</span>

中心极限定理告诉我们：无论单个随机变量 $X_i$ 服从什么分布，只要满足独立同分布条件（或满足李雅普诺夫条件），它们的和 $S_n = \sum_{i=1}^{n} X_i$ 在 $n$ 足够大时，都近似服从正态分布。

**直观理解**：
- 许多微小独立因素的叠加效果趋于正态分布
- 这解释了为什么自然界中大量现象近似服从正态分布

### 补充：连续性修正

用正态分布近似二项分布时，进行连续性修正可提高精度：

$$P\{Y_n = k\} \approx \frac{1}{\sqrt{2\pi npq}} e^{-\frac{(k-np)^2}{2npq}}$$

或使用区间近似：
$$P\{k_1 \leq Y_n \leq k_2\} \approx \Phi\left(\frac{k_2+0.5-np}{\sqrt{npq}}\right) - \Phi\left(\frac{k_1-0.5-np}{\sqrt{npq}}\right)$$
