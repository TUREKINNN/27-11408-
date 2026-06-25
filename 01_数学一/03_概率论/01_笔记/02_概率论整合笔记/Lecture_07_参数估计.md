---
title: Lecture 07 - 参数估计
subject: 概率论与数理统计
chapter: 第七章
lecture: 07
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 07: 参数估计

## 一、点估计的概念

### 1.1 点估计问题

<span style="background-color: #ccc1d9">**定义（点估计）**</span> 设总体 $X$ 的分布函数 $F(x; \theta)$ 中含有未知参数 $\theta$，$X_1, X_2, \cdots, X_n$ 是来自总体 $X$ 的样本，$x_1, x_2, \cdots, x_n$ 是样本值。构造一个统计量 $\hat{\theta}(X_1, X_2, \cdots, X_n)$，用它的观测值 $\hat{\theta}(x_1, x_2, \cdots, x_n)$ 作为未知参数 $\theta$ 的估计值，这种方法称为**点估计**。

称 $\hat{\theta}(X_1, X_2, \cdots, X_n)$ 为 $\theta$ 的**估计量**，称 $\hat{\theta}(x_1, x_2, \cdots, x_n)$ 为 $\theta$ 的**估计值**。

### 1.2 点估计的常用方法

点估计的常用方法有**矩估计法**和**最大似然估计法**。

---

## 二、矩估计法

### 2.1 矩估计法的思想

矩估计法的基本思想是用**样本矩**来估计**总体矩**。

设总体 $X$ 的分布中含有 $k$ 个未知参数 $\theta_1, \theta_2, \cdots, \theta_k$，总体的 $m$ 阶原点矩为 $\mu_m = E(X^m)$，样本的 $m$ 阶原点矩为 $A_m = \frac{1}{n}\sum_{i=1}^{n}X_i^m$。

令 $\mu_m = A_m, m = 1, 2, \cdots, k$，得到 $k$ 个方程，解这个方程组得到 $\theta_1, \theta_2, \cdots, \theta_k$ 的矩估计量。

### 2.2 矩估计的步骤

1. **计算总体矩**：计算总体的前 $k$ 阶原点矩 $\mu_1, \mu_2, \cdots, \mu_k$，它们是未知参数 $\theta_1, \theta_2, \cdots, \theta_k$ 的函数
2. **建立方程**：令 $\mu_m = A_m, m = 1, 2, \cdots, k$
3. **求解方程**：解方程组，得到 $\theta_1, \theta_2, \cdots, \theta_k$ 的矩估计量

---

## 三、最大似然估计法

### 3.1 似然函数

<span style="background-color: #ccc1d9">**定义（似然函数）**</span> 

1. **离散型**：设总体 $X$ 的分布律为 $P\{X = x\} = p(x; \theta)$，则样本 $X_1, X_2, \cdots, X_n$ 的似然函数为

$$L(\theta) = \prod_{i=1}^{n} p(x_i; \theta)$$

2. **连续型**：设总体 $X$ 的概率密度为 $f(x; \theta)$，则样本 $X_1, X_2, \cdots, X_n$ 的似然函数为

$$L(\theta) = \prod_{i=1}^{n} f(x_i; \theta)$$

### 3.2 最大似然估计的定义

<span style="background-color: #ccc1d9">**定义（最大似然估计）**</span> 若存在 $\hat{\theta}(x_1, x_2, \cdots, x_n)$，使得

$$L(\hat{\theta}) = \max_{\theta} L(\theta)$$

则称 $\hat{\theta}(x_1, x_2, \cdots, x_n)$ 为 $\theta$ 的**最大似然估计值**，称 $\hat{\theta}(X_1, X_2, \cdots, X_n)$ 为 $\theta$ 的**最大似然估计量**。

### 3.3 最大似然估计的步骤

1. **写出似然函数**：$L(\theta) = \prod_{i=1}^{n} f(x_i; \theta)$
2. **取对数**：$\ln L(\theta) = \sum_{i=1}^{n} \ln f(x_i; \theta)$
3. **求导**：对 $\theta$ 求导，令导数为零，解似然方程
4. **验证**：验证解是否为最大值点

---

## 四、估计量的评价标准

### 4.1 无偏性

<span style="background-color: #ccc1d9">**定义（无偏性）**</span> 设 $\hat{\theta}$ 是 $\theta$ 的估计量，若

$$E(\hat{\theta}) = \theta$$

则称 $\hat{\theta}$ 是 $\theta$ 的**无偏估计量**。

**注**：样本均值 $\overline{X}$ 是总体均值 $\mu$ 的无偏估计，样本方差 $S^2$ 是总体方差 $\sigma^2$ 的无偏估计。

### 4.2 有效性

<span style="background-color: #ccc1d9">**定义（有效性）**</span> 设 $\hat{\theta}_1$ 和 $\hat{\theta}_2$ 都是 $\theta$ 的无偏估计量，若

$$D(\hat{\theta}_1) < D(\hat{\theta}_2)$$

则称 $\hat{\theta}_1$ 比 $\hat{\theta}_2$ **更有效**。

### 4.3 一致性（相合性）

<span style="background-color: #ccc1d9">**定义（一致性）**</span> 设 $\hat{\theta}_n$ 是 $\theta$ 的估计量，若对任意 $\varepsilon > 0$，有

$$\lim_{n \to \infty} P\{|\hat{\theta}_n - \theta| \geq \varepsilon\} = 0$$

则称 $\hat{\theta}_n$ 是 $\theta$ 的**一致估计量**（或相合估计量）。

---

## 五、区间估计的概念

### 5.1 区间估计的定义

<span style="background-color: #ccc1d9">**定义（区间估计）**</span> 设总体 $X$ 的分布函数 $F(x; \theta)$ 中含有未知参数 $\theta$，$X_1, X_2, \cdots, X_n$ 是来自总体 $X$ 的样本。对于给定的 $\alpha \in (0, 1)$，若存在两个统计量 $\hat{\theta}_1(X_1, X_2, \cdots, X_n)$ 和 $\hat{\theta}_2(X_1, X_2, \cdots, X_n)$，使得

$$P\{\hat{\theta}_1 < \theta < \hat{\theta}_2\} = 1 - \alpha$$

则称随机区间 $(\hat{\theta}_1, \hat{\theta}_2)$ 为 $\theta$ 的**置信水平为 $1 - \alpha$ 的置信区间**，$\hat{\theta}_1$ 称为**置信下限**，$\hat{\theta}_2$ 称为**置信上限**，$1 - \alpha$ 称为**置信水平**。

### 5.2 置信区间的求解步骤

1. **构造枢轴量**：构造一个包含 $\theta$ 的统计量 $G = G(X_1, \cdots, X_n; \theta)$，其分布已知且与 $\theta$ 无关
2. **确定分位数**：对于给定的 $\alpha$，确定常数 $a, b$ 使得 $P\{a < G < b\} = 1 - \alpha$
3. **变形求解**：将不等式 $a < G < b$ 变形为 $\hat{\theta}_1 < \theta < \hat{\theta}_2$

---

## 六、正态总体参数的区间估计

### 6.1 单个正态总体均值 $\mu$ 的区间估计

设 $X_1, X_2, \cdots, X_n$ 是来自 $N(\mu, \sigma^2)$ 的样本，$\overline{X}$ 为样本均值，$S^2$ 为样本方差。

#### (1) $\sigma^2$ 已知

枢轴量：$Z = \frac{\overline{X} - \mu}{\sigma/\sqrt{n}} \sim N(0, 1)$

置信区间：$$\left(\overline{X} - z_{\alpha/2} \frac{\sigma}{\sqrt{n}}, \overline{X} + z_{\alpha/2} \frac{\sigma}{\sqrt{n}}\right)$$

#### (2) $\sigma^2$ 未知

枢轴量：$t = \frac{\overline{X} - \mu}{S/\sqrt{n}} \sim t(n-1)$

置信区间：$$\left(\overline{X} - t_{\alpha/2}(n-1) \frac{S}{\sqrt{n}}, \overline{X} + t_{\alpha/2}(n-1) \frac{S}{\sqrt{n}}\right)$$

### 6.2 单个正态总体方差 $\sigma^2$ 的区间估计

枢轴量：$\chi^2 = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2(n-1)$

置信区间：$$\left(\frac{(n-1)S^2}{\chi_{\alpha/2}^2(n-1)}, \frac{(n-1)S^2}{\chi_{1-\alpha/2}^2(n-1)}\right)$$

### 6.3 两个正态总体均值差 $\mu_1 - \mu_2$ 的区间估计

设 $X_1, \cdots, X_{n_1}$ 来自 $N(\mu_1, \sigma_1^2)$，$Y_1, \cdots, Y_{n_2}$ 来自 $N(\mu_2, \sigma_2^2)$。

#### (1) $\sigma_1^2, \sigma_2^2$ 已知

置信区间：$$\left((\overline{X} - \overline{Y}) - z_{\alpha/2} \sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}, (\overline{X} - \overline{Y}) + z_{\alpha/2} \sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}\right)$$

#### (2) $\sigma_1^2 = \sigma_2^2 = \sigma^2$ 未知

置信区间：$$\left((\overline{X} - \overline{Y}) - t_{\alpha/2}(n_1+n_2-2) S_w \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}, (\overline{X} - \overline{Y}) + t_{\alpha/2}(n_1+n_2-2) S_w \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}\right)$$

其中 $S_w^2 = \frac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1 + n_2 - 2}$。

---

## 七、典型例题

### 例题1：均匀分布的矩估计（660题第563题）

**题目**：设总体 $X \sim U[a, b]$，$X_{1}, X_{2}, \cdots, X_{n}$ 为其简单随机样本，样本均值 $\overline{X}$，样本方差 $S^{2}$，则 $a, b$ 的矩估计 $\hat{a}=$ ____，$\hat{b}=$ ____。

**思路**：利用矩估计法，建立总体矩与样本矩的方程。

**解答**：
$X \sim U[a, b]$，则 $E(X) = \frac{a+b}{2}$，$D(X) = \frac{(b-a)^2}{12}$

令：
$$E(X) = \overline{X} \Rightarrow \frac{a+b}{2} = \overline{X}$$

$$E(X^2) = A_2 = \frac{1}{n}\sum_{i=1}^{n}X_i^2$$

又 $E(X^2) = D(X) + [E(X)]^2 = \frac{(b-a)^2}{12} + \overline{X}^2$

$$\frac{(b-a)^2}{12} + \overline{X}^2 = A_2 \Rightarrow \frac{(b-a)^2}{12} = A_2 - \overline{X}^2$$

$$b - a = 2\sqrt{3(A_2 - \overline{X}^2)}$$

联立解得：
$$\hat{a} = \overline{X} - \sqrt{3(A_2 - \overline{X}^2)} = \overline{X} - \sqrt{3}S_n$$

$$\hat{b} = \overline{X} + \sqrt{3(A_2 - \overline{X}^2)} = \overline{X} + \sqrt{3}S_n$$

其中 $S_n^2 = \frac{1}{n}\sum_{i=1}^{n}(X_i - \overline{X})^2 = A_2 - \overline{X}^2$

**总结**：矩估计需要利用总体矩与样本矩相等建立方程。

---

### 例题2：均匀分布的最大似然估计（660题第564题）

**题目**：设总体 $X \sim U[a, b]$，$a, b$ 是未知参数，$X_{1}, X_{2}, \cdots, X_{n}$ 是总体 $X$ 的简单随机样本，则参数 $a, b$ 的最大似然估计量分别为 ____。

**思路**：写出似然函数，分析最大值点。

**解答**：
$X \sim U[a, b]$，概率密度为 $f(x) = \frac{1}{b-a}, a \leq x \leq b$

似然函数：
$$L(a, b) = \prod_{i=1}^{n} \frac{1}{b-a} = \frac{1}{(b-a)^n}, \quad a \leq x_i \leq b, i = 1, 2, \cdots, n$$

要使 $L(a, b)$ 最大，需使 $b - a$ 最小。

$a$ 的最大值为 $\min\{x_1, \cdots, x_n\} = x_{(1)}$

$b$ 的最小值为 $\max\{x_1, \cdots, x_n\} = x_{(n)}$

因此：
$$\hat{a} = X_{(1)}, \quad \hat{b} = X_{(n)}$$

**总结**：均匀分布的最大似然估计是顺序统计量。

---

### 例题3：矩估计与最大似然估计（660题第565题）

**题目**：总体 $X$ 的概率分布为

| $X$ | 0 | 1 | 2 |
|-----|---|---|---|
| $P$ | $\theta^2$ | $2\theta(1-\theta)$ | $(1-\theta)^2$ |

$\theta \in \left(0, \frac{1}{2}\right)$ 为待估参数。从 $X$ 中抽得样本值：1, 2, 1, 0, 1, 0, 1, 2, 1, 2。则 $\theta$ 的矩估计 $\hat{\theta}_{\text{矩}} =$ ____，$\theta$ 的最大似然估计 $\hat{\theta} =$ ____。

**思路**：分别用矩估计法和最大似然估计法。

**解答**：
1. **矩估计**：
$$E(X) = 0 \times \theta^2 + 1 \times 2\theta(1-\theta) + 2 \times (1-\theta)^2 = 2\theta - 2\theta^2 + 2 - 4\theta + 2\theta^2 = 2 - 2\theta$$

样本均值 $\overline{x} = \frac{1+2+1+0+1+0+1+2+1+2}{10} = \frac{11}{10} = 1.1$

令 $E(X) = \overline{x}$：$2 - 2\theta = 1.1 \Rightarrow \hat{\theta}_{\text{矩}} = 0.45$

2. **最大似然估计**：
似然函数：
$$L(\theta) = \prod_{i=1}^{n} P\{X = x_i\} = [\theta^2]^2 \times [2\theta(1-\theta)]^4 \times [(1-\theta)^2]^4$$

$$= \theta^4 \times 16\theta^4(1-\theta)^4 \times (1-\theta)^8 = 16\theta^8(1-\theta)^{12}$$

对数似然：
$$\ln L(\theta) = \ln 16 + 8\ln \theta + 12\ln(1-\theta)$$

求导并令为零：
$$\frac{d\ln L}{d\theta} = \frac{8}{\theta} - \frac{12}{1-\theta} = 0 \Rightarrow 8(1-\theta) = 12\theta \Rightarrow 8 = 20\theta \Rightarrow \hat{\theta} = 0.4$$

**总结**：矩估计和最大似然估计可能不同。

---

## 八、解题方法总结

### 8.1 主要方法

| 类型 | 方法 |
|------|------|
| 矩估计 | 令总体矩 = 样本矩，解方程组 |
| 最大似然估计 | 写出似然函数，取对数，求导找极值 |
| 无偏性 | 计算 $E(\hat{\theta})$ 是否等于 $\theta$ |
| 有效性 | 比较无偏估计量的方差 |
| 区间估计 | 构造枢轴量，确定分位数，变形求解 |

### 8.2 常见易错点

1. **矩估计的阶数**：要估计 $k$ 个参数，需要建立 $k$ 个方程
2. **最大似然估计的边界点**：当似然方程无解时，考虑边界点
3. **样本方差的无偏性**：$S^2 = \frac{1}{n-1}\sum(X_i - \overline{X})^2$ 是无偏的
4. **置信区间的分位数**：注意是双侧分位数还是单侧分位数

---

## 九、练习题精选

### 基础练习

1. 设总体 $X \sim P(\lambda)$，求 $\lambda$ 的矩估计和最大似然估计。

2. 设总体 $X \sim N(\mu, \sigma^2)$，求 $\mu$ 和 $\sigma^2$ 的矩估计和最大似然估计。

### 提高练习

3. 设总体 $X$ 的概率密度为 $f(x; \theta) = \theta x^{\theta-1}, 0 < x < 1, \theta > 0$，求 $\theta$ 的矩估计和最大似然估计。

4. 设 $X_1, X_2, \cdots, X_n$ 是来自 $N(\mu, 4)$ 的样本，求 $\mu$ 的置信水平为 $0.95$ 的置信区间。

---

## 参考答案提示

1. 矩估计和最大似然估计都是 $\hat{\lambda} = \overline{X}$（提示：泊松分布的期望和方差都等于 $\lambda$）

2. 矩估计：$\hat{\mu} = \overline{X}, \hat{\sigma}^2 = S_n^2$；最大似然估计：$\hat{\mu} = \overline{X}, \hat{\sigma}^2 = S_n^2$（提示：似然函数求导）

3. 矩估计：$\hat{\theta} = \frac{\overline{X}}{1 - \overline{X}}$；最大似然估计：$\hat{\theta} = \frac{n}{\sum_{i=1}^{n}\ln X_i}$（提示：计算期望和似然函数）

4. 置信区间：$\left(\overline{X} - \frac{2z_{0.025}}{\sqrt{n}}, \overline{X} + \frac{2z_{0.025}}{\sqrt{n}}\right)$（提示：$\sigma^2$ 已知，用 $Z$ 分布）

---

> **注**：本 Lecture 内容涵盖点估计、矩估计、最大似然估计、估计量评价标准及区间估计。建议结合《基础过关660题》第563-570题进行练习巩固。

### 补充：置信区间的意义

<span style="background-color: #8db3e2">**置信水平的直观理解**</span>

置信水平为 $1-\alpha$ 的置信区间 $(\hat{\theta}_1, \hat{\theta}_2)$ 的含义：

如果重复抽样 $100$ 次，每次构造一个置信区间，则大约有 $100(1-\alpha)$ 个区间会包含参数的真值 $\theta$。

**注意**：
- 参数 $\theta$ 是确定的，未知的
- 置信区间是随机的，依赖于样本
- 我们不能说"$\theta$ 以 $1-\alpha$ 的概率落在置信区间内"

### 补充：假设检验的两类错误

| 错误类型 | 定义 | 概率 | 记号 |
|----------|------|------|------|
| 第一类错误（弃真） | $H_0$ 为真但被拒绝 | $\alpha$ | 显著性水平 |
| 第二类错误（取伪） | $H_0$ 为假但被接受 | $\beta$ | - |

**关系**：当样本容量 $n$ 固定时，减小 $\alpha$ 会增大 $\beta$，反之亦然。要同时减小两类错误，需增大 $n$。

**检验的势（功效）**：$1 - \beta$，即当 $H_1$ 为真时正确拒绝 $H_0$ 的概率。
