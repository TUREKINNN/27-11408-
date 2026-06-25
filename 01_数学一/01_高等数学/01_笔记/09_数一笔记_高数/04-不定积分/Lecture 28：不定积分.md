---
title: "Lecture 28：不定积分"
chapter: "04-不定积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 不定积分, 基本积分公式, 原函数]
difficulty: ★★★☆☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 28：不定积分

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算题基础） |
| **分值分布** | 约 10-15 分（计算题、综合题中频繁出现） |
| **题型** | 求不定积分、已知导数求原函数、积分与微分方程结合 |
| **难度** | 中等（基本公式必须熟记，技巧性强） |

---

## 一、原函数的概念

> 设 $f(x)$ 在区间 $I$ 上有定义，若存在函数 $F(x)$，使得对任意 $x \in I$，都有：
>
> $$\boxed{F'(x) = f(x) \quad \text{或} \quad \mathrm{d}F(x) = f(x)\,\mathrm{d}x}$$
>
> 则称 $F(x)$ 为 $f(x)$ 在区间 $I$ 上的一个**原函数**。

**关键理解**：

1. **存在性**：若 $f(x)$ 在区间 $I$ 上连续，则 $f(x)$ 在 $I$ 上必有原函数（这是原函数存在定理）
2. **不唯一性**：若 $F(x)$ 是 $f(x)$ 的一个原函数，则 $F(x) + C$（$C$ 为任意常数）也是 $f(x)$ 的原函数
3. **全体原函数**：$f(x)$ 的任意两个原函数之间只差一个常数，即全体原函数为 $F(x) + C$

> 设 $F(x)$ 和 $G(x)$ 都是 $f(x)$ 的原函数，则：
> $$[F(x) - G(x)]' = F'(x) - G'(x) = f(x) - f(x) = 0$$
> 由拉格朗日中值定理的推论，导数恒为零的函数必为常数，故 $F(x) - G(x) = C$。

---

## 二、不定积分的定义

> 函数 $f(x)$ 在区间 $I$ 上的**全体原函数**称为 $f(x)$ 在 $I$ 上的不定积分，记为：
>
> $$\boxed{\int f(x)\,\mathrm{d}x = F(x) + C}$$
>
> 其中 $\int$ 为积分号，$f(x)$ 为**被积函数**，$f(x)\,\mathrm{d}x$ 为**被积表达式**，$x$ 为**积分变量**，$C$ 为**积分常数**。

**几何意义**：不定积分 $\int f(x)\,\mathrm{d}x = F(x) + C$ 表示一族曲线（积分曲线族），它们在横坐标相同点处的切线斜率都等于 $f(x)$。

---

## 三、不定积分的性质

>
> **性质 1（求导与积分互逆）**：
> $$\left(\int f(x)\,\mathrm{d}x\right)' = f(x) \quad \text{或} \quad \mathrm{d}\!\int f(x)\,\mathrm{d}x = f(x)\,\mathrm{d}x$$
>
> **性质 2（先积后导）**：
> $$\int F'(x)\,\mathrm{d}x = F(x) + C \quad \text{或} \quad \int \mathrm{d}F(x) = F(x) + C$$
>
> **性质 3（线性性——常数提出来）**：
> $$\int k\,f(x)\,\mathrm{d}x = k\!\int f(x)\,\mathrm{d}x \quad (k \ne 0 \text{ 为常数})$$
>
> **性质 4（线性性——逐项积分）**：
> $$\int [f(x) \pm g(x)]\,\mathrm{d}x = \int f(x)\,\mathrm{d}x \pm \int g(x)\,\mathrm{d}x$$

**理解要点**：
- 性质 1、2 体现了**微分与积分互为逆运算**
- 性质 3、4 合称为不定积分的**线性性质**，是拆分复杂积分的理论基础

---

## 四、20 个基本积分公式


### 幂函数与常数类

| 编号 | 公式 | 条件 |
|------|------|------|
| ① | $\displaystyle\int 0\,\mathrm{d}x = C$ | |
| ② | $\displaystyle\int 1\,\mathrm{d}x = x + C$ | |
| ③ | $\displaystyle\int x^n\,\mathrm{d}x = \frac{x^{n+1}}{n+1} + C$ | $n \ne -1$ |
| ④ | $\displaystyle\int \frac{1}{x}\,\mathrm{d}x = \ln\|x\| + C$ | |


### 指数函数与对数函数类

| 编号 | 公式 |
|------|------|
| ⑤ | $\displaystyle\int a^x\,\mathrm{d}x = \frac{a^x}{\ln a} + C \quad (a > 0, a \ne 1)$ |
| ⑥ | $\displaystyle\int e^x\,\mathrm{d}x = e^x + C$ |
| ⑦ | $\displaystyle\int \frac{1}{x\ln a}\,\mathrm{d}x = \log_a\|x\| + C$ |

### 三角函数类

| 编号 | 公式 |
|------|------|
| ⑧ | $\displaystyle\int \sin x\,\mathrm{d}x = -\cos x + C$ |
| ⑨ | $\displaystyle\int \cos x\,\mathrm{d}x = \sin x + C$ |
| ⑩ | $\displaystyle\int \tan x\,\mathrm{d}x = -\ln\|\cos x\| + C = \ln\|\sec x\| + C$ |
| ⑪ | $\displaystyle\int \cot x\,\mathrm{d}x = \ln\|\sin x\| + C = -\ln\|\csc x\| + C$ |
| ⑫ | $\displaystyle\int \sec x\,\mathrm{d}x = \ln\|\sec x + \tan x\| + C$ |
| ⑬ | $\displaystyle\int \csc x\,\mathrm{d}x = \ln\|\csc x - \cot x\| + C$ |
| ⑭ | $\displaystyle\int \sec^2 x\,\mathrm{d}x = \tan x + C$ |
| ⑮ | $\displaystyle\int \csc^2 x\,\mathrm{d}x = -\cot x + C$ |
| ⑯ | $\displaystyle\int \sec x\tan x\,\mathrm{d}x = \sec x + C$ |
| ⑰ | $\displaystyle\int \csc x\cot x\,\mathrm{d}x = -\csc x + C$ |

### 反三角函数类（含根式）

| 编号 | 公式 |
|------|------|
| ⑱ | $\displaystyle\int \frac{1}{\sqrt{a^2 - x^2}}\,\mathrm{d}x = \arcsin\frac{x}{a} + C$ |
| ⑲ | $\displaystyle\int \frac{1}{a^2 + x^2}\,\mathrm{d}x = \frac{1}{a}\arctan\frac{x}{a} + C$ |
| ⑳ | $\displaystyle\int \frac{1}{\sqrt{x^2 \pm a^2}}\,\mathrm{d}x = \ln\left\|x + \sqrt{x^2 \pm a^2}\right\| + C$ |

---

## 五、常用技巧补充

> - **"正弦负余弦"**：$\int \sin x = -\cos x$（注意负号）
> - **"正切负余切"**：记住 $\sec^2 x \to \tan x$，$\csc^2 x \to -\cot x$
> - **"谁与谁搭档"**：$\sec x \cdot \tan x \to \sec x$，$\csc x \cdot \cot x \to -\csc x$

**公式 ⑩ 的推导**：
$$\int \tan x\,\mathrm{d}x = \int \frac{\sin x}{\cos x}\,\mathrm{d}x = -\int \frac{\mathrm{d}(\cos x)}{\cos x} = -\ln|\cos x| + C$$

**公式 ⑫ 的推导**：
$$\int \sec x\,\mathrm{d}x = \int \frac{\sec x(\sec x + \tan x)}{\sec x + \tan x}\,\mathrm{d}x = \int \frac{\mathrm{d}(\sec x + \tan x)}{\sec x + \tan x} = \ln|\sec x + \tan x| + C$$

---

## 六、典型例题

### 例 1：利用线性性质拆分

**题目**：求 $\displaystyle\int \left(3x^2 - 2\sin x + \frac{1}{x}\right)\mathrm{d}x$

**解**：

$$\int \left(3x^2 - 2\sin x + \frac{1}{x}\right)\mathrm{d}x = 3\int x^2\,\mathrm{d}x - 2\int \sin x\,\mathrm{d}x + \int \frac{1}{x}\,\mathrm{d}x$$

$$= 3 \cdot \frac{x^3}{3} - 2(-\cos x) + \ln|x| + C$$

$$= \boxed{x^3 + 2\cos x + \ln|x| + C}$$

---

### 例 2：三角恒等变换后积分

**题目**：求 $\displaystyle\int \tan^2 x\,\mathrm{d}x$

**解**：

利用恒等式 $\tan^2 x = \sec^2 x - 1$：

$$\int \tan^2 x\,\mathrm{d}x = \int (\sec^2 x - 1)\,\mathrm{d}x = \tan x - x + C$$

$$\boxed{\int \tan^2 x\,\mathrm{d}x = \tan x - x + C}$$

---

### 例 3：分式化简后积分

**题目**：求 $\displaystyle\int \frac{x^4}{1 + x^2}\,\mathrm{d}x$

**解**：

先做多项式除法：$x^4 = (x^2 - 1)(x^2 + 1) + 1$，故：

$$\frac{x^4}{1 + x^2} = x^2 - 1 + \frac{1}{1 + x^2}$$

$$\int \frac{x^4}{1 + x^2}\,\mathrm{d}x = \int (x^2 - 1)\,\mathrm{d}x + \int \frac{1}{1 + x^2}\,\mathrm{d}x$$

$$= \frac{x^3}{3} - x + \arctan x + C$$

$$\boxed{\int \frac{x^4}{1 + x^2}\,\mathrm{d}x = \frac{x^3}{3} - x + \arctan x + C}$$

---

### 例 4：已知导数求原函数

**题目**：设 $f'(x) = 2x + 3$，$f(0) = 1$，求 $f(x)$。

**解**：

$$f(x) = \int (2x + 3)\,\mathrm{d}x = x^2 + 3x + C$$

由 $f(0) = 1$ 得 $C = 1$，故：

$$\boxed{f(x) = x^2 + 3x + 1}$$

---

### 例 5：综合计算

**题目**：求 $\displaystyle\int \frac{\cos 2x}{\cos x - \sin x}\,\mathrm{d}x$

**解**：

利用 $\cos 2x = \cos^2 x - \sin^2 x = (\cos x - \sin x)(\cos x + \sin x)$：

$$\int \frac{\cos 2x}{\cos x - \sin x}\,\mathrm{d}x = \int (\cos x + \sin x)\,\mathrm{d}x = \sin x - \cos x + C$$

$$\boxed{\int \frac{\cos 2x}{\cos x - \sin x}\,\mathrm{d}x = \sin x - \cos x + C}$$

---

## 📝 总结

| 知识点 | 要点 |
|--------|------|
| **原函数** | $F'(x) = f(x)$，全体原函数差一个常数 |
| **不定积分** | 全体原函数的集合 $\int f(x)\,\mathrm{d}x = F(x) + C$ |
| **性质** | 互逆性（2条）+ 线性性（2条）= 共4条 |
| **基本公式** | 20个必须熟记，特别是幂函数、三角函数、反三角函数类 |
| **核心技巧** | 三角恒等变换、多项式除法、分式拆分 |

> 1. 积分常数 $C$ **不能忘记**！不定积分是全体原函数
> 2. $\int \frac{1}{x}\mathrm{d}x = \ln|x| + C$，**绝对值不能丢**
> 3. $\int x^n\mathrm{d}x = \frac{x^{n+1}}{n+1} + C$ 要求 $n \ne -1$，$n = -1$ 时用公式 ④
> 4. 不定积分的结果求导后应等于被积函数（可用于验算）

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 29：两类换元积分法]] — 换元法
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 30：分部积分法]] — 分部积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 16：导数基本概念]] — 导数基础
