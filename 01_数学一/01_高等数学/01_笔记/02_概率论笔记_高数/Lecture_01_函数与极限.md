---
title: Lecture 01 - 函数与极限
subject: 高等数学
chapter: 第一章
lecture: 01
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 01: 函数与极限

## 一、函数的基本概念

### 1.1 函数的定义

<span style="background-color: #ccc1d9">**定义（函数）**</span> 设 $D$ 是一个非空数集，若存在对应法则 $f$，使得对于 $D$ 中每个元素 $x$，都有唯一确定的 $y$ 与之对应，则称 $f$ 为定义在 $D$ 上的**函数**，记作 $y = f(x)$。

- **定义域**：$D$，即自变量 $x$ 的取值范围
- **值域**：$f(D) = \{y \mid y = f(x), x \in D\}$

### 1.2 函数的性质

<span style="background-color: #ccc1d9">**定义（奇偶性）**</span> 设函数 $f(x)$ 的定义域关于原点对称：
- 若 $f(-x) = f(x)$，则 $f(x)$ 为**偶函数**
- 若 $f(-x) = -f(x)$，则 $f(x)$ 为**奇函数**

<span style="background-color: #ccc1d9">**定义（周期性）**</span> 若存在非零常数 $T$，使得 $f(x + T) = f(x)$ 对所有 $x \in D$ 成立，则 $f(x)$ 为**周期函数**，$T$ 称为周期。

<span style="background-color: #ccc1d9">**定义（单调性）**</span> 设 $f(x)$ 在区间 $I$ 上定义：
- 若 $x_1 < x_2$ 时，$f(x_1) < f(x_2)$，则 $f(x)$ 在 $I$ 上**单调递增**
- 若 $x_1 < x_2$ 时，$f(x_1) > f(x_2)$，则 $f(x)$ 在 $I$ 上**单调递减**

### 1.3 常见函数类型

**基本初等函数**：
1. **幂函数**：$y = x^\alpha$（$\alpha$ 为常数）
2. **指数函数**：$y = a^x$（$a > 0, a \neq 1$）
3. **对数函数**：$y = \log_a x$（$a > 0, a \neq 1$）
4. **三角函数**：$y = \sin x, \cos x, \tan x, \cot x$
5. **反三角函数**：$y = \arcsin x, \arccos x, \arctan x, \text{arccot} x$

**复合函数**：若 $y = f(u)$，$u = g(x)$，则 $y = f(g(x))$ 称为复合函数。

---

## 二、极限的概念

### 2.1 数列极限

<span style="background-color: #ccc1d9">**定义（数列极限）**</span> 设数列 $\{x_n\}$，若存在常数 $A$，对于任意给定的 $\varepsilon > 0$，总存在正整数 $N$，使得当 $n > N$ 时，有 $|x_n - A| < \varepsilon$，则称数列 $\{x_n\}$ **收敛**于 $A$，记作 $\lim_{n \to \infty} x_n = A$ 或 $x_n \to A$（$n \to \infty$）。

<span style="background-color: #8db3e2">**定理（数列极限的唯一性）**</span> 收敛数列的极限是唯一的。

<span style="background-color: #8db3e2">**定理（数列极限的有界性）**</span> 收敛数列必有界。

### 2.2 函数极限

<span style="background-color: #ccc1d9">**定义（函数极限 - $x \to x_0$）**</span> 设函数 $f(x)$ 在点 $x_0$ 的某去心邻域内有定义，若存在常数 $A$，对于任意 $\varepsilon > 0$，存在 $\delta > 0$，使得当 $0 < |x - x_0| < \delta$ 时，有 $|f(x) - A| < \varepsilon$，则称 $A$ 为 $f(x)$ 当 $x \to x_0$ 时的极限，记作 $\lim_{x \to x_0} f(x) = A$。

<span style="background-color: #ccc1d9">**定义（左极限与右极限）**</span>
- **左极限**：$\lim_{x \to x_0^-} f(x) = A$，记作 $f(x_0^-) = A$
- **右极限**：$\lim_{x \to x_0^+} f(x) = A$，记作 $f(x_0^+) = A$

<span style="background-color: #8db3e2">**定理（极限存在的充要条件）**</span> $\lim_{x \to x_0} f(x) = A$ 的充要条件是 $f(x_0^-) = f(x_0^+) = A$。

<span style="background-color: #ccc1d9">**定义（函数极限 - $x \to \infty$）**</span> 若存在常数 $A$，对于任意 $\varepsilon > 0$，存在 $X > 0$，使得当 $|x| > X$ 时，有 $|f(x) - A| < \varepsilon$，则称 $\lim_{x \to \infty} f(x) = A$。

---

## 三、极限的性质与运算

### 3.1 极限的基本性质

<span style="background-color: #8db3e2">**定理（极限的唯一性）**</span> 若 $\lim f(x)$ 存在，则极限值唯一。

<span style="background-color: #8db3e2">**定理（极限的局部有界性）**</span> 若 $\lim_{x \to x_0} f(x) = A$，则存在 $M > 0$ 和 $\delta > 0$，使得当 $0 < |x - x_0| < \delta$ 时，$|f(x)| \leq M$。

<span style="background-color: #8db3e2">**定理（极限的局部保号性）**</span> 若 $\lim_{x \to x_0} f(x) = A > 0$（或 $A < 0$），则存在 $\delta > 0$，使得当 $0 < |x - x_0| < \delta$ 时，$f(x) > 0$（或 $f(x) < 0$）。

### 3.2 极限的运算法则

<span style="background-color: #8db3e2">**定理（极限的四则运算）**</span> 设 $\lim f(x) = A$，$\lim g(x) = B$，则：

1. $\lim [f(x) + g(x)] = A + B$
2. $\lim [f(x) - g(x)] = A - B$
3. $\lim [f(x) \cdot g(x)] = A \cdot B$
4. $\lim \frac{f(x)}{g(x)} = \frac{A}{B}$（$B \neq 0$）

<span style="background-color: #8db3e2">**定理（复合函数极限）**</span> 若 $\lim_{x \to x_0} g(x) = u_0$，$\lim_{u \to u_0} f(u) = A$，且在 $x_0$ 的某去心邻域内 $g(x) \neq u_0$，则 $\lim_{x \to x_0} f(g(x)) = A$。

---

## 四、两个重要极限

### 4.1 第一个重要极限

<span style="background-color: #8db3e2">**定理**</span> $\lim_{x \to 0} \frac{\sin x}{x} = 1$

**推广形式**：若 $\lim \alpha(x) = 0$，则 $\lim \frac{\sin \alpha(x)}{\alpha(x)} = 1$

### 4.2 第二个重要极限

<span style="background-color: #8db3e2">**定理**</span> $\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e$ 或 $\lim_{x \to 0} (1 + x)^{\frac{1}{x}} = e$

**推广形式**：若 $\lim \alpha(x) = 0$，则 $\lim (1 + \alpha(x))^{\frac{1}{\alpha(x)}} = e$

---

## 五、无穷小与无穷大

### 5.1 无穷小

<span style="background-color: #ccc1d9">**定义（无穷小）**</span> 若 $\lim f(x) = 0$，则称 $f(x)$ 为该极限过程中的**无穷小**。

<span style="background-color: #8db3e2">**定理（无穷小与极限的关系）**</span> $\lim f(x) = A$ 的充要条件是 $f(x) = A + \alpha(x)$，其中 $\alpha(x)$ 为无穷小。

### 5.2 无穷小的比较

<span style="background-color: #ccc1d9">**定义（无穷小的阶）**</span> 设 $\alpha(x)$ 和 $\beta(x)$ 为同一极限过程中的无穷小：

1. 若 $\lim \frac{\alpha(x)}{\beta(x)} = 0$，则称 $\alpha(x)$ 是 $\beta(x)$ 的**高阶无穷小**，记作 $\alpha(x) = o(\beta(x))$
2. 若 $\lim \frac{\alpha(x)}{\beta(x)} = c \neq 0$，则称 $\alpha(x)$ 与 $\beta(x)$ 为**同阶无穷小**
3. 若 $\lim \frac{\alpha(x)}{\beta(x)} = 1$，则称 $\alpha(x)$ 与 $\beta(x)$ 为**等价无穷小**，记作 $\alpha(x) \sim \beta(x)$

### 5.3 常用等价无穷小

当 $x \to 0$ 时：

| 原式 | 等价无穷小 |
|------|-----------|
| $\sin x$ | $x$ |
| $\tan x$ | $x$ |
| $\arcsin x$ | $x$ |
| $\arctan x$ | $x$ |
| $1 - \cos x$ | $\frac{1}{2}x^2$ |
| $\ln(1 + x)$ | $x$ |
| $e^x - 1$ | $x$ |
| $a^x - 1$ | $x \ln a$ |
| $(1 + x)^\alpha - 1$ | $\alpha x$ |

<span style="background-color: #8db3e2">**定理（等价无穷小替换）**</span> 设 $\alpha(x) \sim \alpha'(x)$，$\beta(x) \sim \beta'(x)$，且 $\lim \frac{\alpha'(x)}{\beta'(x)}$ 存在，则 $\lim \frac{\alpha(x)}{\beta(x)} = \lim \frac{\alpha'(x)}{\beta'(x)}$。

### 5.4 无穷大

<span style="background-color: #ccc1d9">**定义（无穷大）**</span> 若对于任意 $M > 0$，存在 $\delta > 0$（或 $X > 0$），使得当 $0 < |x - x_0| < \delta$（或 $|x| > X$）时，有 $|f(x)| > M$，则称 $f(x)$ 为该极限过程中的**无穷大**，记作 $\lim f(x) = \infty$。

<span style="background-color: #8db3e2">**定理（无穷小与无穷大的关系）**</span> 在同一极限过程中，若 $f(x)$ 为无穷小且 $f(x) \neq 0$，则 $\frac{1}{f(x)}$ 为无穷大；若 $f(x)$ 为无穷大，则 $\frac{1}{f(x)}$ 为无穷小。

---

## 六、极限的存在准则

### 6.1 夹逼准则

<span style="background-color: #8db3e2">**定理（夹逼准则）**</span> 若在 $x_0$ 的某去心邻域内（或 $|x|$ 充分大时），有 $g(x) \leq f(x) \leq h(x)$，且 $\lim g(x) = \lim h(x) = A$，则 $\lim f(x) = A$。

### 6.2 单调有界准则

<span style="background-color: #8db3e2">**定理（单调有界准则）**</span> 单调递增有上界（或单调递减有下界）的数列必有极限。

---

## 七、函数的连续性

### 7.1 连续的定义

<span style="background-color: #ccc1d9">**定义（连续）**</span> 设函数 $f(x)$ 在点 $x_0$ 的某邻域内有定义，若 $\lim_{x \to x_0} f(x) = f(x_0)$，则称 $f(x)$ 在点 $x_0$ **连续**。

**连续的三个条件**：
1. $f(x_0)$ 存在
2. $\lim_{x \to x_0} f(x)$ 存在
3. $\lim_{x \to x_0} f(x) = f(x_0)$

<span style="background-color: #ccc1d9">**定义（左连续与右连续）**</span>
- 若 $f(x_0^-) = f(x_0)$，则 $f(x)$ 在 $x_0$ **左连续**
- 若 $f(x_0^+) = f(x_0)$，则 $f(x)$ 在 $x_0$ **右连续**

<span style="background-color: #8db3e2">**定理**</span> $f(x)$ 在 $x_0$ 连续的充要条件是 $f(x)$ 在 $x_0$ 既左连续又右连续。

### 7.2 间断点

<span style="background-color: #ccc1d9">**定义（间断点）**</span> 若 $f(x)$ 在 $x_0$ 不连续，则称 $x_0$ 为 $f(x)$ 的**间断点**。

**间断点的分类**：

| 类型 | 条件 | 特点 |
|------|------|------|
| **可去间断点** | $\lim_{x \to x_0} f(x)$ 存在，但不等于 $f(x_0)$ 或 $f(x_0)$ 无定义 | 极限存在 |
| **跳跃间断点** | $f(x_0^-)$ 和 $f(x_0^+)$ 都存在但不相等 | 左右极限存在但不相等 |
| **无穷间断点** | $\lim_{x \to x_0} f(x) = \infty$ | 极限为无穷 |
| **振荡间断点** | $\lim_{x \to x_0} f(x)$ 不存在且不为无穷 | 极限不存在 |

**第一类间断点**：可去间断点和跳跃间断点（左右极限都存在）
**第二类间断点**：无穷间断点和振荡间断点（左右极限至少有一个不存在）

### 7.3 连续函数的性质

<span style="background-color: #8db3e2">**定理（连续函数的四则运算）**</span> 若 $f(x)$ 和 $g(x)$ 在 $x_0$ 连续，则 $f(x) + g(x)$、$f(x) - g(x)$、$f(x) \cdot g(x)$、$\frac{f(x)}{g(x)}$（$g(x_0) \neq 0$）也在 $x_0$ 连续。

<span style="background-color: #8db3e2">**定理（复合函数的连续性）**</span> 若 $g(x)$ 在 $x_0$ 连续，$f(u)$ 在 $u_0 = g(x_0)$ 连续，则复合函数 $f(g(x))$ 在 $x_0$ 连续。

<span style="background-color: #8db3e2">**定理（反函数的连续性）**</span> 若 $f(x)$ 在区间 $I$ 上单调连续，则其反函数 $f^{-1}(x)$ 在对应区间上也连续。

### 7.4 闭区间上连续函数的性质

<span style="background-color: #8db3e2">**定理（最大值最小值定理）**</span> 若 $f(x)$ 在闭区间 $[a, b]$ 上连续，则 $f(x)$ 在 $[a, b]$ 上必有最大值和最小值。

<span style="background-color: #8db3e2">**定理（有界性定理）**</span> 若 $f(x)$ 在闭区间 $[a, b]$ 上连续，则 $f(x)$ 在 $[a, b]$ 上有界。

<span style="background-color: #8db3e2">**定理（介值定理）**</span> 若 $f(x)$ 在闭区间 $[a, b]$ 上连续，且 $f(a) \neq f(b)$，则对于介于 $f(a)$ 和 $f(b)$ 之间的任意值 $C$，至少存在一点 $\xi \in (a, b)$，使得 $f(\xi) = C$。

<span style="background-color: #8db3e2">**定理（零点定理）**</span> 若 $f(x)$ 在闭区间 $[a, b]$ 上连续，且 $f(a) \cdot f(b) < 0$，则至少存在一点 $\xi \in (a, b)$，使得 $f(\xi) = 0$。

---

## 八、典型例题

### 例题1：重要极限的应用

**题目**：设 $\lim_{x \to 0} \left(1 + x + \frac{f(x)}{x}\right)^{\frac{1}{x}} = e^3$，求 $\lim_{x \to 0} \left(1 + \frac{f(x)}{x}\right)^{\frac{1}{x}}$。

**思路**：利用第二个重要极限的形式，分析指数部分。

**解答**：
由 $\lim_{x \to 0} \left(1 + x + \frac{f(x)}{x}\right)^{\frac{1}{x}} = e^3$

设 $u = x + \frac{f(x)}{x}$，则 $\lim_{x \to 0} u = 0$

利用 $(1 + u)^{\frac{1}{u}} \to e$，有 $\lim_{x \to 0} \left(1 + x + \frac{f(x)}{x}\right)^{\frac{1}{x}} = e^{\lim_{x \to 0} \frac{x + \frac{f(x)}{x}}{x}} = e^{\lim_{x \to 0} \left(1 + \frac{f(x)}{x^2}\right)}$

所以 $\lim_{x \to 0} \left(1 + \frac{f(x)}{x^2}\right) = 3$

即 $\lim_{x \to 0} \frac{f(x)}{x^2} = 2$

因此 $\lim_{x \to 0} \left(1 + \frac{f(x)}{x}\right)^{\frac{1}{x}} = e^{\lim_{x \to 0} \frac{f(x)}{x^2}} = e^2$

**总结**：利用重要极限 $(1 + \alpha)^{\frac{1}{\alpha}} \to e$，关键是分析指数部分的极限。

---

### 例题2：无穷小阶的比较

**题目**：当 $x \to 0$ 时，比较 $\sin x - x$ 与 $x^3$ 的阶。

**思路**：利用泰勒展开或洛必达法则。

**解答**：
方法一（泰勒展开）：
$\sin x = x - \frac{x^3}{6} + o(x^3)$

所以 $\sin x - x = -\frac{x^3}{6} + o(x^3) \sim -\frac{x^3}{6}$

因此 $\lim_{x \to 0} \frac{\sin x - x}{x^3} = -\frac{1}{6}$

方法二（洛必达法则）：
$\lim_{x \to 0} \frac{\sin x - x}{x^3} = \lim_{x \to 0} \frac{\cos x - 1}{3x^2} = \lim_{x \to 0} \frac{-\sin x}{6x} = -\frac{1}{6}$

**总结**：$\sin x - x$ 与 $x^3$ 是同阶无穷小，$\sin x - x \sim -\frac{x^3}{6}$。

---

### 例题3：间断点的判断

**题目**：设 $f(x) = \frac{e^x - b}{(x - a)(x - b)}$ 有无穷间断点 $x = e$，可去间断点 $x = 1$，求 $(a, b)$。

**思路**：根据间断点类型分析函数在相应点的极限情况。

**解答**：
对于可去间断点 $x = 1$：
$\lim_{x \to 1} f(x)$ 存在，需要分子分母同时为零或分母为零但极限存在。

若 $x = 1$ 使分母为零，则 $a = 1$ 或 $b = 1$。

若 $a = 1$，则分子 $e^1 - b = e - b$，为使极限存在，需 $e - b = 0$，即 $b = e$。

对于无穷间断点 $x = e$：
$\lim_{x \to e} f(x) = \infty$，需要分母为零但分子不为零。

若 $b = e$，则 $x = e$ 时分母 $(e - a)(e - e) = 0$，分子 $e^e - e \neq 0$，满足无穷间断点条件。

验证：$(a, b) = (1, e)$

**总结**：判断间断点类型需要分析极限的存在性及值。

---

### 例题4：数列极限

**题目**：设 $x_0 = 0$, $x_n = \frac{1 + 2x_{n-1}}{1 + x_{n-1}}$（$n = 1, 2, 3, \cdots$），求 $\lim_{n \to \infty} x_n$。

**思路**：证明数列收敛，然后设极限求解。

**解答**：
首先证明数列单调递增且有界：
- $x_1 = 1$, $x_2 = \frac{3}{2} = 1.5$, $x_3 = \frac{4}{2.5} = 1.6$
- 可证明 $0 \leq x_n \leq 2$ 且 $x_n$ 单调递增

由单调有界准则，$\lim_{n \to \infty} x_n$ 存在，设为 $A$。

由递推关系：$A = \frac{1 + 2A}{1 + A}$

解得：$A(1 + A) = 1 + 2A$，即 $A + A^2 = 1 + 2A$

$A^2 - A - 1 = 0$，解得 $A = \frac{1 + \sqrt{5}}{2}$（取正值，因为 $x_n > 0$）

**总结**：递推数列求极限，先证明收敛（单调有界），再设极限解方程。

---

### 例题5：极限计算综合

**题目**：计算 $\lim_{x \to 0} \frac{\sqrt{1 + \tan x} - \sqrt{1 + \sin x}}{e^{\tan x} - e^{\sin x}}$。

**思路**：分子有理化，利用等价无穷小替换。

**解答**：
分子有理化：
$\sqrt{1 + \tan x} - \sqrt{1 + \sin x} = \frac{\tan x - \sin x}{\sqrt{1 + \tan x} + \sqrt{1 + \sin x}}$

分母：$e^{\tan x} - e^{\sin x} = e^{\sin x}(e^{\tan x - \sin x} - 1) \sim e^{\sin x}(\tan x - \sin x)$

原式 $= \lim_{x \to 0} \frac{\tan x - \sin x}{(\sqrt{1 + \tan x} + \sqrt{1 + \sin x}) \cdot e^{\sin x}(\tan x - \sin x)}$

$= \lim_{x \to 0} \frac{1}{(\sqrt{1 + \tan x} + \sqrt{1 + \sin x}) \cdot e^{\sin x}}$

$= \frac{1}{(1 + 1) \cdot 1} = \frac{1}{2}$

**总结**：有理化是处理根式差的有效方法，配合等价无穷小可简化计算。

---

## 九、解题方法总结

### 9.1 求极限的主要方法

1. **利用极限定义**：适用于证明极限
2. **利用四则运算**：适用于简单组合
3. **利用等价无穷小替换**：适用于 $\frac{0}{0}$ 型
4. **利用重要极限**：适用于特定形式
5. **利用夹逼准则**：适用于不等式关系
6. **利用洛必达法则**：适用于 $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ 型
7. **利用泰勒展开**：适用于复杂函数

### 9.2 常见题型

| 题型 | 方法 |
|------|------|
| $\frac{0}{0}$ 型 | 等价无穷小、洛必达、泰勒展开 |
| $\frac{\infty}{\infty}$ 型 | 洛必达、提取最高次项 |
| $1^\infty$ 型 | 利用 $(1 + \alpha)^{\frac{1}{\alpha}} \to e$ |
| $\infty - \infty$ 型 | 通分、有理化 |
| $0 \cdot \infty$ 型 | 转化为 $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ |
| 数列极限 | 单调有界、夹逼准则 |

---

## 十、练习题精选

### 基础练习

1. 求 $\lim_{x \to \infty} \left(\sqrt[3]{1 - x^6} - ax^2 - b\right) = 0$ 中的 $a, b$。

2. 计算 $\lim_{x \to +\infty} \left(x^3 \ln \frac{x + 1}{x - 1} - 2x^2\right)$。

3. 计算 $\lim_{x \to +\infty} (\sqrt[6]{x^6 + x^5} - \sqrt[6]{x^6 - x^5})$。

4. 设 $f(x) = \begin{cases} \frac{e^{ax^3} - 1}{x - \arcsin x}, & x > 0 \\ 6, & x \leq 0 \end{cases}$ 在 $x = 0$ 连续，求 $a$。

### 提高练习

5. 计算 $\lim_{x \to 0} \frac{(1 - \sqrt{\cos x})(1 - \sqrt[3]{\cos x}) \cdots (1 - \sqrt[n]{\cos x})}{(1 - \cos x)^{n-1}}$。

6. 设 $\lim_{x \to 1} f(x)$ 存在，且 $f(x) = e^{-2x} + x^{\frac{2}{1-x}} \lim_{x \to 1} f(x)$，求 $f(x)$。

7. 设 $[x]$ 表示不超过 $x$ 的最大整数，求 $\lim_{x \to 0} x\left[\frac{2}{x}\right]$。

---

## 参考答案提示

1. $a = -1$, $b = \frac{1}{3}$（提示：有理化后分析）

2. $\frac{2}{3}$（提示：令 $t = \frac{1}{x}$，泰勒展开）

3. $\frac{1}{3}$（提示：提取 $x$，有理化）

4. $a = 2$（提示：利用连续性定义，求左右极限）

5. $\frac{1}{2 \cdot 3 \cdots n} = \frac{1}{n!}$（提示：利用 $1 - \sqrt[k]{\cos x} \sim \frac{x^2}{2k}$）

6. $f(x) = e^{-2x} + \frac{e^{-2}}{1 - e^{-2}} x^{\frac{2}{1-x}}$（提示：设 $A = \lim_{x \to 1} f(x)$，解方程）

7. $2$（提示：利用夹逼准则，$\frac{2}{x} - 1 < \left[\frac{2}{x}\right] \leq \frac{2}{x}$）

---

> **注**：本 Lecture 内容涵盖函数与极限的基本概念、性质、计算方法及典型例题。建议结合《基础过关660题》对应章节进行练习巩固。