---
title: "Lecture 15：参数估计"
tags: [考研, 数学一, 概率论, 数学]
categories: 概率论

date: 2026-06-16
---

# Lecture 15：参数估计

> **考研数学一 · 概率论与数理统计 · 第15讲**
> 本讲涵盖：矩估计法、最大似然估计法（MLE）、估计量的评价标准（无偏性、有效性、一致性）
> 考纲要求：★★★★★（矩估计和MLE是考研解答题的高频考点，几乎每年一道大题）

---

## 一、参数估计的基本概念

### 1.1 问题的提出

设总体 $X$ 的分布函数为 $F(x; \\theta)$，其中 $\\theta$（可能为向量）为未知参数。现从总体中抽取样本 $X_1, X_2, \\ldots, X_n$，需要根据样本对未知参数 $\\theta$ 进行估计。

- **点估计：** 用一个统计量 $\\hat{\\theta} = \\hat{\\theta}(X_1, \\ldots, X_n)$ 来估计 $\\theta$
- **区间估计：** 用一个随机区间来包含 $\\theta$（见 Lecture 16）

### 1.2 估计量与估计值

- **估计量（Estimator）：** $\\hat{\\theta}(X_1, \\ldots, X_n)$ 是统计量（随机变量）
- **估计值（Estimate）：** 将样本观测值 $x_1, \\ldots, x_n$ 代入后得到的具体数值

---

## 二、矩估计法 ⭐⭐⭐⭐⭐

### 2.1 基本思想

用**样本矩**替换对应的**总体矩**，从而得到参数的估计。

**理论依据：** 大数定律保证样本矩依概率收敛于总体矩。

### 2.2 矩估计法的步骤 ⭐⭐⭐⭐⭐

**设总体有 $k$ 个未知参数 $\\theta_1, \\theta_2, \\ldots, \\theta_k$：**

**步骤一：** 计算总体的前 $k$ 阶原点矩（含未知参数）：

$$\\mu_1 = E(X), \quad \\mu_2 = E(X^2), \quad \\ldots, \quad \\mu_k = E(X^k)$$

这些都是 $\\theta_1, \\theta_2, \\ldots, \\theta_k$ 的函数。

**步骤二：** 建立方程组，用样本矩替换总体矩：

$$\\begin{cases} \\mu_1(\\theta_1, \\ldots, \\theta_k) = A_1 = \\bar{X} \\\\ \\mu_2(\\theta_1, \\ldots, \\theta_k) = A_2 = \\frac{1}{n}\\sum X_i^2 \\\\ \\vdots \\\\ \\mu_k(\\theta_1, \\ldots, \\theta_k) = A_k = \\frac{1}{n}\\sum X_i^k \\end{cases}$$

**步骤三：** 解方程组，得到 $\\hat{\\theta}_1, \\hat{\\theta}_2, \\ldots, \\hat{\\theta}_k$ 的估计。

> **注意：** 矩估计中通常用一阶矩 $E(X) = \\bar{X}$ 和二阶矩 $E(X^2) = \\frac{1}{n}\\sum X_i^2$。不要混淆为 $E(X) = \\bar{X}$ 和 $D(X) = S^2$。虽然 $D(X) = E(X^2) - [E(X)]^2$ 也可以使用，但标准步骤是用原点矩。

### 2.3 矩估计的经典例题

**【例1】** 设总体 $X \\sim U(0, \\theta)$（$\\theta > 0$ 未知），$X_1, \\ldots, X_n$ 为样本，求 $\\theta$ 的矩估计。

**解：**

$$E(X) = \\frac{\\theta}{2}$$

令 $E(X) = \\bar{X}$，得 $\\frac{\\theta}{2} = \\bar{X}$，所以 $\\hat{\\theta} = 2\\bar{X}$。

**【例2】** 设总体 $X \\sim E(\\lambda)$（$\\lambda > 0$ 未知），求 $\\lambda$ 的矩估计。

**解：**

$$E(X) = \\frac{1}{\\lambda}$$

令 $\\frac{1}{\\lambda} = \\bar{X}$，得 $\\hat{\\lambda} = \\frac{1}{\\bar{X}}$。

**【例3】** 设总体 $X \\sim N(\\mu, \\sigma^2)$，$\\mu, \\sigma^2$ 未知，求 $\\mu, \\sigma^2$ 的矩估计。

**解：**

两个未知参数，需要两个方程：

$$E(X) = \\mu = \\bar{X} \quad \\Rightarrow \\quad \\hat{\\mu} = \\bar{X}$$

$$E(X^2) = \\sigma^2 + \\mu^2 = \\frac{1}{n}\\sum X_i^2$$

$$\\hat{\\sigma}^2 = \\frac{1}{n}\\sum X_i^2 - \\bar{X}^2 = \\frac{1}{n}\\sum(X_i - \\bar{X})^2 = B_2$$

> **注意：** 正态分布 $\\mu$ 的矩估计是 $\\bar{X}$，$\\sigma^2$ 的矩估计是 $B_2 = \\frac{1}{n}\\sum(X_i-\\bar{X})^2$（分母为 $n$），**不是** $S^2$（分母为 $n-1$）！

**【例4】** 设总体 $X$ 的密度为 $f(x; \\theta) = (\\theta+1)x^\\theta$（$0 < x < 1$，$\\theta > -1$），求 $\\theta$ 的矩估计。

**解：**

$$E(X) = \\int_0^1 x(\\theta+1)x^\\theta \, dx = (\\theta+1) \\int_0^1 x^{\\theta+1} \, dx = \\frac{\\theta+1}{\\theta+2}$$

令 $\\frac{\\theta+1}{\\theta+2} = \\bar{X}$，解得 $\\hat{\\theta} = \\frac{2\\bar{X}-1}{1-\\bar{X}}$。

---

## 三、最大似然估计法（MLE） ⭐⭐⭐⭐⭐

### 3.1 基本思想

选取参数 $\\theta$ 的值，使得**观测到当前样本的概率最大**。即：已经发生了的事件，应该有最大的概率。

### 3.2 似然函数

**离散型总体：** 若 $P\\{X = x\\} = p(x; \\theta)$，则似然函数为：

$$\\boxed{L(\\theta) = \\prod_{i=1}^n p(x_i; \\theta)}$$

**连续型总体：** 若密度函数为 $f(x; \\theta)$，则似然函数为：

$$\\boxed{L(\\theta) = \\prod_{i=1}^n f(x_i; \\theta)}$$

### 3.3 最大似然估计的步骤 ⭐⭐⭐⭐⭐

**步骤一：写出似然函数**

$$L(\\theta) = \\prod_{i=1}^n f(x_i; \\theta)$$

**步骤二：取对数似然函数**

$$\\ln L(\\theta) = \\sum_{i=1}^n \\ln f(x_i; \\theta)$$

> **取对数的原因：** 将乘积转化为求和，方便求导。$\\ln L$ 和 $L$ 在相同的 $\\theta$ 处取最大值。

**步骤三：对 $\\theta$ 求导，令导数为零**

$$\\frac{d \\ln L(\\theta)}{d\\theta} = 0$$

**步骤四：解方程，得到 $\\hat{\\theta}_{\\text{MLE}}$**

**若参数为向量 $\\theta = (\\theta_1, \\ldots, \\theta_k)$**，则对每个参数分别求偏导：

$$\\frac{\\partial \\ln L}{\\partial \\theta_j} = 0, \quad j = 1, 2, \\ldots, k$$

### 3.4 MLE 的不变性

若 $\\hat{\\theta}$ 是 $\\theta$ 的 MLE，$g$ 为单调函数，则 $g(\\hat{\\theta})$ 是 $g(\\theta)$ 的 MLE。

$$\\boxed{\\hat{g(\\theta)}_{\\text{MLE}} = g(\\hat{\\theta}_{\\text{MLE}})}$$

---

## 四、最大似然估计的经典例题

**【例5】** 设 $X_1, \\ldots, X_n$ 为来自 $B(1, p)$ 的样本，求 $p$ 的 MLE。

**解：**

$$L(p) = \\prod_{i=1}^n p^{x_i}(1-p)^{1-x_i} = p^{\\sum x_i}(1-p)^{n-\\sum x_i}$$

$$\\ln L = \\left(\\sum x_i\\right) \\ln p + \\left(n - \\sum x_i\\right) \\ln(1-p)$$

$$\\frac{d \\ln L}{dp} = \\frac{\\sum x_i}{p} - \\frac{n - \\sum x_i}{1-p} = 0$$

$$\\sum x_i (1-p) = (n - \\sum x_i) p$$

$$\\sum x_i = np$$

$$\\hat{p} = \\frac{\\sum x_i}{n} = \\bar{X}$$

**【例6】** 设 $X_1, \\ldots, X_n$ 为来自 $E(\\lambda)$ 的样本，求 $\\lambda$ 的 MLE。

**解：**

$$L(\\lambda) = \\prod_{i=1}^n \\lambda e^{-\\lambda x_i} = \\lambda^n e^{-\\lambda \\sum x_i}$$

$$\\ln L = n \\ln \\lambda - \\lambda \\sum x_i$$

$$\\frac{d \\ln L}{d\\lambda} = \\frac{n}{\\lambda} - \\sum x_i = 0$$

$$\\hat{\\lambda} = \\frac{n}{\\sum x_i} = \\frac{1}{\\bar{X}}$$

**【例7】** 设 $X_1, \\ldots, X_n$ 为来自 $N(\\mu, \\sigma^2)$ 的样本，$\\mu, \\sigma^2$ 均未知，求 $\\mu, \\sigma^2$ 的 MLE。

**解：**

$$L(\\mu, \\sigma^2) = (2\\pi\\sigma^2)^{-n/2} \\exp\\left\\{-\\frac{1}{2\\sigma^2}\\sum(x_i - \\mu)^2\\right\\}$$

$$\\ln L = -\\frac{n}{2}\\ln(2\\pi) - \\frac{n}{2}\\ln\\sigma^2 - \\frac{1}{2\\sigma^2}\\sum(x_i-\\mu)^2$$

对 $\\mu$ 求偏导：
$$\\frac{\\partial \\ln L}{\\partial \\mu} = \\frac{1}{\\sigma^2}\\sum(x_i - \\mu) = 0 \\Rightarrow \\hat{\\mu} = \\bar{X}$$

对 $\\sigma^2$ 求偏导（令 $\\sigma^2 = \\tau$）：
$$\\frac{\\partial \\ln L}{\\partial \\tau} = -\\frac{n}{2\\tau} + \\frac{1}{2\\tau^2}\\sum(x_i - \\bar{X})^2 = 0$$

$$\\hat{\\sigma}^2 = \\frac{1}{n}\\sum(x_i - \\bar{X})^2 = B_2$$

> **结论：** 正态分布 $\\mu$ 的 MLE 是 $\\bar{X}$，$\\sigma^2$ 的 MLE 是 $B_2$（分母为 $n$）。这与矩估计结果相同。

**【例8】** 设总体 $X \\sim U(0, \\theta)$，求 $\\theta$ 的 MLE。

**解：**

$$L(\\theta) = \\prod_{i=1}^n \\frac{1}{\\theta} = \\frac{1}{\\theta^n}, \quad 0 \\leq x_i \\leq \\theta \text{ 对所有 } i$$

似然函数 $L(\\theta) = \\theta^{-n}$ 随 $\\theta$ 减小而增大，但约束条件 $\\theta \\geq \\max(x_i)$。

因此 $\\hat{\\theta}_{\\text{MLE}} = \\max\\{X_1, \\ldots, X_n\\} = X_{(n)}$。

> **注意：** 这个例题说明 MLE 不能总是通过求导得到！当似然函数单调时，需要直接从约束条件判断。

---

## 五、估计量的评价标准 ⭐⭐⭐⭐

### 5.1 无偏性

**定义：** 若 $E(\\hat{\\theta}) = \\theta$，则称 $\\hat{\\theta}$ 是 $\\theta$ 的**无偏估计**（Unbiased Estimator）。

$$\\boxed{E(\\hat{\\theta}) = \\theta}$$

**常见无偏估计：**

| 参数 | 无偏估计 | 说明 |
|------|---------|------|
| $\\mu = E(X)$ | $\\bar{X}$ | 样本均值是总体均值的无偏估计 |
| $\\sigma^2 = D(X)$ | $S^2 = \\frac{1}{n-1}\\sum(X_i - \\bar{X})^2$ | 样本方差（分母 $n-1$）是总体方差的无偏估计 |

**$E(S^2) = \\sigma^2$ 的证明：**

$$E(S^2) = E\\left[\\frac{1}{n-1}\\sum(X_i - \\bar{X})^2\\right]$$

利用 $\\sum(X_i - \\bar{X})^2 = \\sum(X_i - \\mu)^2 - n(\\bar{X} - \\mu)^2$：

$$E(S^2) = \\frac{1}{n-1}[n\\sigma^2 - n \\cdot \\frac{\\sigma^2}{n}] = \\frac{1}{n-1}(n-1)\\sigma^2 = \\sigma^2$$

> **$B_2 = \\frac{1}{n}\\sum(X_i - \\bar{X})^2$ 不是无偏估计：** $E(B_2) = \\frac{n-1}{n}\\sigma^2 \\neq \\sigma^2$。这就是为什么样本方差分母要用 $n-1$。

### 5.2 有效性

**定义：** 设 $\\hat{\\theta}_1$ 和 $\\hat{\\theta}_2$ 都是 $\\theta$ 的无偏估计，若：

$$D(\\hat{\\theta}_1) < D(\\hat{\\theta}_2)$$

则称 $\\hat{\\theta}_1$ 比 $\\hat{\\theta}_2$ **更有效**（More Efficient）。

> **有效性的含义：** 在所有无偏估计中，方差越小的估计越好（估计值越集中在真值附近）。

**最小方差无偏估计（MVUE）：** 在所有无偏估计中方差最小的估计。

### 5.3 一致性（相合性）

**定义：** 若当 $n \\to \\infty$ 时，$\\hat{\\theta} \\xrightarrow{P} \\theta$，则称 $\\hat{\\theta}$ 是 $\\theta$ 的**一致估计**（Consistent Estimator）。

即：随着样本量增大，估计量依概率收敛于真值。

**判断一致性的方法：**

由大数定律，$\\bar{X} \\xrightarrow{P} E(X) = \\mu$，所以 $\\bar{X}$ 是 $\\mu$ 的一致估计。

一般地，若 $\\hat{\\theta}$ 是无偏估计且 $D(\\hat{\\theta}) \\to 0$（$n \\to \\infty$），则 $\\hat{\\theta}$ 是一致估计。

---

## 六、矩估计与MLE的对比

| | 矩估计法 | 最大似然估计法 |
|---|---------|---------------|
| **思想** | 样本矩 = 总体矩 | 使似然函数最大 |
| **步骤** | 简单（列方程解方程） | 较复杂（求似然函数→取对数→求导） |
| **适用范围** | 只需矩存在 | 需要密度/分布律已知 |
| **精度** | 一般 | 通常更优 |
| **不变性** | 无 | 有（MLE的不变性） |
| **计算** | 解方程 | 求导数为零的点 |

---

## 七、易错点与考试陷阱

### ⚠️ 易错点1：矩估计用原点矩

标准的矩估计法用 $E(X^k) = \\frac{1}{n}\\sum X_i^k$（原点矩），不是用中心矩。虽然 $D(X) = E(X^2) - [E(X)]^2$ 也可以构造等价方程，但考试中推荐按标准步骤做。

### ⚠️ 易错点2：MLE中均匀分布的处理

$U(0, \\theta)$ 的 MLE 不是通过求导得到的，而是从约束条件 $\\theta \\geq \\max(x_i)$ 得到。考试中容易忽略这一点。

### ⚠️ 易错点3：$\\sigma^2$ 的矩估计和MLE都是 $B_2$

正态总体的 $\\sigma^2$ 的矩估计和 MLE 都是 $B_2 = \\frac{1}{n}\\sum(X_i - \\bar{X})^2$（分母 $n$），不是 $S^2$（分母 $n-1$）。

### ⚠️ 易错点4：取对数后的求导

$\\ln L = \\sum \\ln f(x_i; \\theta)$，对 $\\theta$ 求导时是 $\\sum \\frac{\\partial}{\\partial \\theta} \\ln f(x_i; \\theta)$，不要忘记链式法则。

### ⚠️ 易错点5：无偏估计的判断

$E(\\hat{\\theta}) = \\theta$ 才是无偏。$E(B_2) = \\frac{n-1}{n}\\sigma^2 \\neq \\sigma^2$，所以 $B_2$ 不是 $\\sigma^2$ 的无偏估计。

---

## 八、本讲知识框架图

```
参数估计
├── 矩估计法 ⭐⭐⭐⭐⭐
│   ├── 思想：样本矩替换总体矩
│   ├── 步骤：求E(Xᵏ) → 令E(Xᵏ)=Aₖ → 解方程
│   ├── 正态N(μ,σ²)：μ̂=X̄, σ̂²=B₂
│   └── 均匀U(0,θ)：θ̂=2X̄
├── 最大似然估计(MLE) ⭐⭐⭐⭐⭐
│   ├── 思想：使观测到当前样本的概率最大
│   ├── 步骤：L(θ)=∏f(xᵢ;θ) → lnL → d/dθ=0 → 解
│   ├── 不变性：g(θ)的MLE = g(θ̂_MLE)
│   └── 特殊情况：U(0,θ)的MLE=max(Xᵢ)
├── 估计量的评价标准 ⭐⭐⭐⭐
│   ├── 无偏性：E(θ̂)=θ
│   │   ├── X̄是μ的无偏估计
│   │   └── S²是σ²的无偏估计（分母n-1）
│   ├── 有效性：D(θ̂₁)<D(θ̂₂)则θ̂₁更有效
│   └── 一致性：θ̂ →ᵖ θ（n→∞）
└── 两种方法对比
    ├── 矩估计：简单但精度一般
    └── MLE：复杂但通常更优
```

---

## 九、习题精选

**习题1：** 设总体 $X$ 的密度为 $f(x; \\theta) = \\theta x^{\\theta-1}$（$0 < x < 1$，$\\theta > 0$），求 $\\theta$ 的矩估计和 MLE。

**解：**

矩估计：$E(X) = \\frac{\\theta}{\\theta+1} = \\bar{X}$，$\\hat{\\theta} = \\frac{\\bar{X}}{1-\\bar{X}}$

MLE：$L = \\theta^n \\prod x_i^{\\theta-1}$，$\\ln L = n\\ln\\theta + (\\theta-1)\\sum \\ln x_i$

$\\frac{n}{\\theta} + \\sum \\ln x_i = 0$，$\\hat{\\theta} = -\\frac{n}{\\sum \\ln x_i}$

**习题2：** 设 $X_1, X_2, X_3$ 来自 $N(\\mu, 1)$，以下哪个是 $\\mu$ 的无偏估计？(a) $\\hat{\\mu}_1 = \\frac{X_1+X_2+X_3}{3}$，(b) $\\hat{\\mu}_2 = \\frac{X_1+X_2}{2}$

**解：** 两者都是无偏估计：$E(\\hat{\\mu}_1) = \\mu$，$E(\\hat{\\mu}_2) = \\mu$。但 $D(\\hat{\\mu}_1) = 1/3 < D(\\hat{\\mu}_2) = 1/2$，所以 $\\hat{\\mu}_1$ 更有效。

**习题3：** 设 $X \\sim P(\\lambda)$，$X_1, \\ldots, X_n$ 为样本，求 $\\lambda$ 的矩估计和 MLE。

**解：** 矩估计和MLE都得到 $\\hat{\\lambda} = \\bar{X}$。

---

## 十、考研真题考点分析

| 题型 | 考点 | 频率 |
|------|------|------|
| 解答题 | 矩估计法求参数估计 | 极高 |
| 解答题 | 最大似然估计法求参数估计 | 极高 |
| 选择题 | 无偏估计的判断 | 高频 |
| 选择题 | $S^2$ 分母 $n-1$ 的原因（无偏性） | 高频 |
| 填空题 | MLE的不变性应用 | 中频 |
| 选择题 | 两个估计量的有效性比较 | 中频 |

> **备考建议：** 矩估计和MLE是考研解答题的必考内容。建议先做矩估计（简单），再做MLE（需要取对数求导）。记住正态分布、指数分布、均匀分布的矩估计和MLE结果。无偏估计的判断是选择题常考内容。

---

> **下一讲预告：** [[01_数学一/03_概率论/01_笔记/04_数一笔记_概率/06-数理统计与参数估计/Lecture 16：置信区间与假设检验]] —— 置信区间的构造、假设检验的基本原理与两类错误
