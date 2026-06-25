---
title: "Lecture 50：幂级数"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 幂级数, 收敛半径, 阿贝尔定理, 逐项求导, 逐项积分]
difficulty: ★★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 50：幂级数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算题核心考点） |
| **分值分布** | 约 10-14 分 |
| **题型** | 求收敛半径/收敛域、幂级数求和、逐项求导/积分 |
| **难度** | 较难 |

---

## 一、幂级数的基本概念

> 形如
>
> $$\sum_{n=0}^{\infty} a_n (x - x_0)^n = a_0 + a_1(x-x_0) + a_2(x-x_0)^2 + \cdots$$
>
> 的级数称为 $(x - x_0)$ 的**幂级数**。当 $x_0 = 0$ 时：
>
> $$\sum_{n=0}^{\infty} a_n x^n = a_0 + a_1 x + a_2 x^2 + \cdots$$
>
> 称为 $x$ 的幂级数。其中 $a_n$ 称为**系数**。

---

## 二、阿贝尔定理

>
> (1) 若幂级数 $\displaystyle\sum_{n=0}^{\infty} a_n x^n$ 在 $x = x_0 \ne 0$ 处**收敛**，则对所有满足 $|x| < |x_0|$ 的 $x$，幂级数**绝对收敛**。
>
> (2) 若幂级数 $\displaystyle\sum_{n=0}^{\infty} a_n x^n$ 在 $x = x_1$ 处**发散**，则对所有满足 $|x| > |x_1|$ 的 $x$，幂级数**发散**。

> 阿贝尔定理揭示了幂级数的"对称性"：
> - 在某点收敛 → 内部全部绝对收敛
> - 在某点发散 → 外部全部发散
>
> 这意味着存在一个 $R \ge 0$，使得 $(-R, R)$ 内绝对收敛、$|x| > R$ 时发散。这个 $R$ 就是**收敛半径**。

---

## 三、收敛半径与收敛区间

### 3.1 收敛半径的定义

> 对于幂级数 $\displaystyle\sum a_n x^n$，存在 $R \ge 0$（$R$ 可以为 $0$ 或 $+\infty$），使得：
> - 当 $|x| < R$ 时，级数绝对收敛
> - 当 $|x| > R$ 时，级数发散
>
> $R$ 称为幂级数的**收敛半径**，$(-R, R)$ 称为**收敛区间**。

### 3.2 收敛半径的求法

>
> $$\boxed{R = \frac{1}{\rho} = \lim_{n\to\infty}\left|\frac{a_n}{a_{n+1}}\right|}$$
>
> 其中 $\rho = \displaystyle\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right|$。
>
> - $\rho = 0$ → $R = +\infty$，级数对所有 $x$ 收敛
> - $\rho = +\infty$ → $R = 0$，级数仅在 $x = 0$ 处收敛
> - $0 < \rho < +\infty$ → $R = \frac{1}{\rho}$

>
> $$\boxed{R = \frac{1}{\rho} = \frac{1}{\displaystyle\lim_{n\to\infty}\sqrt[n]{|a_n|}}}$$

### 3.3 收敛区间 vs 收敛域

>
> - **收敛区间** $= (-R, R)$，开区间，**不包含端点**
> - **收敛域** = 收敛区间 **加上** 使级数收敛的端点
>
> 求出收敛半径后，必须**单独检验两个端点** $x = \pm R$ 处的敛散性！

> 在端点处，幂级数变成了常数项级数，用前面学过的审敛法（比较法、莱布尼茨准则等）判断。

---

## 四、求收敛域的标准流程

>
> **Step 1**：求收敛半径 $R = \dfrac{1}{\rho}$。
>
> **Step 2**：写出收敛区间 $(-R, R)$。
>
> **Step 3**：分别代入 $x = R$ 和 $x = -R$，判断对应常数项级数的敛散性。
>
> **Step 4**：写出收敛域。

**【例1】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{x^n}{n}$ 的收敛域。

**解**：

**Step 1**：$a_n = \dfrac{1}{n}$

$$\rho = \lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right| = \lim_{n\to\infty}\frac{n}{n+1} = 1 \quad \Rightarrow \quad R = 1$$

**Step 2**：收敛区间 $(-1, 1)$。

**Step 3**：端点检验

$x = 1$：$\displaystyle\sum\frac{1}{n}$（调和级数）→ 发散

$x = -1$：$\displaystyle\sum\frac{(-1)^n}{n}$（交错调和级数）→ 收敛（莱布尼茨准则）

**Step 4**：收敛域为 $[-1, 1)$。$\square$

**【例2】** 求 $\displaystyle\sum_{n=0}^{\infty} \frac{x^n}{n!}$ 的收敛域。

**解**：

$$\rho = \lim_{n\to\infty}\frac{n!}{(n+1)!} = \lim_{n\to\infty}\frac{1}{n+1} = 0 \quad \Rightarrow \quad R = +\infty$$

收敛域为 $(-\infty, +\infty)$（即对所有实数 $x$ 收敛）。$\square$


**【例3】** 求 $\displaystyle\sum_{n=0}^{\infty} n! \, x^n$ 的收敛域。

**解**：

$$\rho = \lim_{n\to\infty}\frac{(n+1)!}{n!} = +\infty \quad \Rightarrow \quad R = 0$$

仅在 $x = 0$ 处收敛。$\square$

**【例4】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{(x-2)^n}{n \cdot 3^n}$ 的收敛域。

**解**：这是 $(x-2)$ 的幂级数。令 $t = x - 2$。

$a_n = \dfrac{1}{n \cdot 3^n}$

$$\rho = \lim_{n\to\infty}\frac{n \cdot 3^n}{(n+1) \cdot 3^{n+1}} = \frac{1}{3} \quad \Rightarrow \quad R = 3$$

收敛区间：$|t| < 3$，即 $|x - 2| < 3$，$-1 < x < 5$。

端点检验：

$x = 5$（$t = 3$）：$\displaystyle\sum\frac{3^n}{n \cdot 3^n} = \sum\frac{1}{n}$ → 发散

$x = -1$（$t = -3$）：$\displaystyle\sum\frac{(-3)^n}{n \cdot 3^n} = \sum\frac{(-1)^n}{n}$ → 收敛

收敛域为 $[-1, 5)$。$\square$

---

## 五、幂级数的运算性质

### 5.1 四则运算

> 设 $\displaystyle\sum a_n x^n$ 的收敛半径为 $R_1$，$\displaystyle\sum b_n x^n$ 的收敛半径为 $R_2$，则
>
> $$\sum a_n x^n \pm \sum b_n x^n = \sum (a_n \pm b_n) x^n$$
>
> 收敛半径 $R \ge \min(R_1, R_2)$。

### 5.2 和函数的连续性

> 幂级数 $\displaystyle\sum a_n x^n$ 的和函数 $S(x)$ 在收敛区间 $(-R, R)$ 内**连续**。
>
> 若级数在端点 $x = R$（或 $x = -R$）处收敛，则 $S(x)$ 在该端点处也连续（单侧连续）。

### 5.3 逐项求导

> 设 $\displaystyle S(x) = \sum_{n=0}^{\infty} a_n x^n$，收敛半径为 $R$，则在 $(-R, R)$ 内：
>
> $$\boxed{S'(x) = \sum_{n=1}^{\infty} n a_n x^{n-1}}$$
>
> 逐项求导后的幂级数**收敛半径不变**（仍为 $R$），但端点处的敛散性可能改变。

### 5.4 逐项积分

> 设 $\displaystyle S(x) = \sum_{n=0}^{\infty} a_n x^n$，收敛半径为 $R$，则对任意 $x \in (-R, R)$：
>
> $$\boxed{\int_0^x S(t)\,dt = \sum_{n=0}^{\infty} \frac{a_n}{n+1} x^{n+1}}$$
>
> 逐项积分后的幂级数**收敛半径不变**，且端点处的敛散性可能变好。

> 逐项求导和逐项积分是**求幂级数和函数**的核心工具！
>
> 基本思路：通过逐项求导/积分，将复杂级数转化为已知和函数的简单级数（如等比级数）。

---

## 六、幂级数求和

### 6.1 基本方法

>
> 1. **识别法**：直接认出是某个已知函数的展开式（如 $e^x$、$\sin x$、$\frac{1}{1-x}$ 等）
> 2. **逐项求导法**：对级数逐项求导，化为已知级数，再积分回来
> 3. **逐项积分法**：对级数逐项积分，化为已知级数，再求导回来

### 6.2 常用的幂级数求和公式

>
> $$\frac{1}{1-x} = \sum_{n=0}^{\infty} x^n = 1 + x + x^2 + \cdots \quad (-1 < x < 1)$$
>
> $$\frac{1}{1+x} = \sum_{n=0}^{\infty} (-1)^n x^n = 1 - x + x^2 - \cdots \quad (-1 < x < 1)$$
>
> $$\frac{1}{1-x^2} = \sum_{n=0}^{\infty} x^{2n} \quad (-1 < x < 1)$$

### 6.3 经典例题

**【例5】** 求 $\displaystyle\sum_{n=1}^{\infty} n x^n$ 的和函数。

**解**：已知 $\displaystyle\sum_{n=0}^{\infty} x^n = \frac{1}{1-x}$（$|x| < 1$）

逐项求导：$\displaystyle\sum_{n=1}^{\infty} n x^{n-1} = \frac{1}{(1-x)^2}$

两边乘以 $x$：$\displaystyle\sum_{n=1}^{\infty} n x^n = \frac{x}{(1-x)^2}$，$|x| < 1$。$\square$

**【例6】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{x^n}{n} = x + \frac{x^2}{2} + \frac{x^3}{3} + \cdots$ 的和函数。

**解**：设 $S(x) = \displaystyle\sum_{n=1}^{\infty}\frac{x^n}{n}$

逐项求导：$S'(x) = \displaystyle\sum_{n=1}^{\infty} x^{n-1} = \frac{1}{1-x}$，$|x| < 1$

积分：$S(x) = \displaystyle\int_0^x \frac{1}{1-t}\,dt = -\ln(1-x)$

故 $S(x) = -\ln(1-x)$，$-1 \le x < 1$（注意 $x = -1$ 处由莱布尼茨准则知收敛）。$\square$

**【例7】** 求 $\displaystyle\sum_{n=0}^{\infty} \frac{x^{2n+1}}{2n+1}$ 的和函数。

**解**：设 $S(x) = \displaystyle\sum_{n=0}^{\infty}\frac{x^{2n+1}}{2n+1}$

逐项求导：$S'(x) = \displaystyle\sum_{n=0}^{\infty} x^{2n} = \frac{1}{1-x^2}$，$|x| < 1$

积分：$S(x) = \displaystyle\int_0^x \frac{1}{1-t^2}\,dt = \frac{1}{2}\ln\frac{1+x}{1-x}$

故 $S(x) = \dfrac{1}{2}\ln\dfrac{1+x}{1-x}$，$-1 < x < 1$。$\square$

**【例8】** 求 $\displaystyle\sum_{n=1}^{\infty} n^2 x^n$ 的和函数。

**解**：已知 $\displaystyle\sum_{n=1}^{\infty} nx^n = \frac{x}{(1-x)^2}$

方法：设 $S(x) = \displaystyle\sum n^2 x^n$

注意到 $n^2 = n(n-1) + n$：

$$S(x) = \sum n(n-1)x^n + \sum nx^n$$

$\displaystyle\sum n(n-1)x^n = x^2 \sum n(n-1)x^{n-2} = x^2 \cdot \frac{d^2}{dx^2}\left(\frac{1}{1-x}\right) = x^2 \cdot \frac{2}{(1-x)^3} = \frac{2x^2}{(1-x)^3}$

$$S(x) = \frac{2x^2}{(1-x)^3} + \frac{x}{(1-x)^2} = \frac{2x^2 + x(1-x)}{(1-x)^3} = \frac{x(x+1)}{(1-x)^3} \quad \square$$

---

## 七、考研真题精选

### 【真题1】（2019年数一·解答·10分）

**题目**：求 $\displaystyle\sum_{n=0}^{\infty} \frac{(-1)^n}{(2n+1)!} x^{2n+1}$ 的收敛域及和函数。

**解**：

**收敛域**：由比值法

$$\left|\frac{u_{n+1}}{u_n}\right| = \frac{|x|^{2n+3}/(2n+3)!}{|x|^{2n+1}/(2n+1)!} = \frac{|x|^2}{(2n+2)(2n+3)} \to 0$$

$R = +\infty$，收敛域 $(-\infty, +\infty)$。

**和函数**：此即 $\sin x$ 的麦克劳林展开式，和函数为 $\sin x$。$\square$

### 【真题2】（解答题·12分）

**题目**：求 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n(2n-1)} x^{2n}$ 的收敛域及和函数。

**解**：

令 $t = x^2$，考虑 $\displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n(2n-1)}t^n$

$a_n = \dfrac{(-1)^{n-1}}{n(2n-1)}$，$\rho = \displaystyle\lim\left|\frac{a_{n+1}}{a_n}\right| = \lim\frac{n(2n-1)}{(n+1)(2n+1)} = 1$

$R_t = 1$，即 $|t| \le 1$，$|x| \le 1$。

端点 $t = 1$（$x = \pm 1$）：$\displaystyle\sum\frac{(-1)^{n-1}}{n(2n-1)}$，通项 $\sim \frac{1}{2n^2}$，绝对收敛。

收敛域 $[-1, 1]$。

设 $S(t) = \displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n(2n-1)}t^n$

$S'(t) = \displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{2n-1}t^{n-1}$

$S''(t) = \displaystyle\sum_{n=1}^{\infty}(-1)^{n-1}t^{n-2} = \frac{1}{1+t} \cdot \frac{1}{t} \cdot t = \frac{1}{1+t}$（需仔细计算）

最终 $S(x) = 2x\arctan x - \ln(1+x^2)$，$|x| \le 1$。$\square$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 阿贝尔定理 | 收敛点内部绝对收敛，发散点外部发散 |
| 收敛半径 | $R = 1/\rho = \lim\|a_n/a_{n+1}\|$ |
| 收敛区间 vs 收敛域 | 区间 $(-R,R)$ 不含端点，域要验端点 |
| 端点检验 | 代入后变成常数项级数，用已有方法判断 |
| 逐项求导 | $S'(x) = \sum na_nx^{n-1}$，半径不变 |
| 逐项积分 | $\int_0^x S(t)dt = \sum\frac{a_n}{n+1}x^{n+1}$，半径不变 |
| 求和策略 | 逐项求导/积分化为等比级数 |

> 1. 求收敛域**必须**检验端点，只写收敛区间扣分
> 2. 收敛半径公式 $R = \|a_n/a_{n+1}\|$ 要注意取绝对值
> 3. 逐项求导/积分不改变收敛半径，但可能改变端点敛散性
> 4. 幂级数求和是高频大题，逐项积分/求导是核心技巧
> 5. 对 $(x - x_0)$ 的幂级数，令 $t = x - x_0$ 转化为标准形式

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 48：正项级数及其审敛准则]] — 正项级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 51：函数展开成幂级数]] — 展开
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 52：傅里叶级数]] — 傅里叶
