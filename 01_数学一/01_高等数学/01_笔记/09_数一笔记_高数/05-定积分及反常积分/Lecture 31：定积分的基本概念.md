---
title: "Lecture 31：定积分的基本概念"
chapter: "05-定积分及反常积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 定积分, 黎曼积分, 积分性质]
difficulty: ★★★☆☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 31：定积分的基本概念

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，是整个积分学的基础） |
| **分值分布** | 约 5-15 分（直接考定义理解或性质应用） |
| **题型** | 定义证明、性质应用、比较大小、估计积分值 |
| **难度** | 中等（概念理解类题较难，计算类题中等） |

---

## 一、定积分的定义

> 设函数 $f(x)$ 在 $[a, b]$ 上有界，对 $[a, b]$ 作任意分割：
>
> $$a = x_0 < x_1 < x_2 < \cdots < x_n = b$$
>
> 记 $\Delta x_i = x_i - x_{i-1}$，$\lambda = \max\limits_{1 \le i \le n}\{\Delta x_i\}$
>
> 在每个小区间 $[x_{i-1}, x_i]$ 上任取一点 $\xi_i$，作**黎曼和**：
>
> $$S_n = \sum_{i=1}^{n} f(\xi_i)\Delta x_i$$
>
> 若极限 $\lim\limits_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i)\Delta x_i$ 存在且与分割方式和 $\xi_i$ 的选取无关，则称 $f(x)$ 在 $[a, b]$ 上**可积**，此极限值称为 $f(x)$ 在 $[a, b]$ 上的**定积分**，记为：
>
> $$\boxed{\int_a^b f(x)\,\mathrm{d}x = \lim_{\lambda \to 0}\sum_{i=1}^{n} f(\xi_i)\Delta x_i}$$

**关键要素理解**：

| 符号 | 含义 |
|------|------|
| $\int$ | 积分号（求和符号 $\sum$ 的极限推广） |
| $a, b$ | 积分下限、上限 |
| $f(x)$ | 被积函数 |
| $x$ | 积分变量（哑变量，可替换为 $t$, $u$ 等） |
| $\mathrm{d}x$ | 积分微元 |

---

## 二、可积的充分条件

>
> **条件 1**：若 $f(x)$ 在 $[a, b]$ 上**连续**，则 $f(x)$ 在 $[a, b]$ 上可积。
>
> **条件 2**：若 $f(x)$ 在 $[a, b]$ 上**有界**且只有**有限个间断点**，则 $f(x)$ 在 $[a, b]$ 上可积。

> - 连续必可积，可积不一定连续
> - 有有限个第一类间断点的有界函数也可积
> - 无界函数不可积（在黎曼积分意义下）

---

## 三、定积分的几何意义

> $\displaystyle\int_a^b f(x)\,\mathrm{d}x$ 表示由曲线 $y = f(x)$、$x$ 轴、直线 $x = a$ 和 $x = b$ 所围成的**代数面积**。
>
> - $f(x) \ge 0$ 时：$\displaystyle\int_a^b f(x)\,\mathrm{d}x = $ 曲边梯形的面积
> - $f(x) \le 0$ 时：$\displaystyle\int_a^b f(x)\,\mathrm{d}x = -$（面积的绝对值）
> - $f(x)$ 有正有负时：正的部分与 $x$ 轴围的面积减去负的部分与 $x$ 轴围的面积

```
  y
  |   ╭──╮        f(x)>0 区域：积分为正
  |  ╱    ╲
  |─╱──────╲───── x 轴
  | ╱   ↑   ╲
  |╱    |    ╲   f(x)<0 区域：积分为负
  +----a-b----→ x
```


---

## 四、定积分的 6 条基本性质

设以下出现的定积分均存在。

### 性质 1：线性性质

>
> $$\int_a^b [\alpha f(x) + \beta g(x)]\,\mathrm{d}x = \alpha\int_a^b f(x)\,\mathrm{d}x + \beta\int_a^b g(x)\,\mathrm{d}x$$
>
> 其中 $\alpha$，$\beta$ 为常数。

### 性质 2：区间可加性

>
> $$\int_a^b f(x)\,\mathrm{d}x = \int_a^c f(x)\,\mathrm{d}x + \int_c^b f(x)\,\mathrm{d}x$$
>
> 其中 $c$ 可以在 $[a, b]$ 内，也可以在 $[a, b]$ 外（只要各段积分存在）。

### 性质 3：保号性（保序性）

> 若 $f(x) \ge 0$，$x \in [a, b]$，则：
>
> $$\int_a^b f(x)\,\mathrm{d}x \ge 0$$
>
> **推论**：若 $f(x) \ge g(x)$，$x \in [a, b]$，则：
>
> $$\int_a^b f(x)\,\mathrm{d}x \ge \int_a^b g(x)\,\mathrm{d}x$$
>
> **推论**：$\displaystyle\left|\int_a^b f(x)\,\mathrm{d}x\right| \le \int_a^b |f(x)|\,\mathrm{d}x$

### 性质 4：估值定理

> 设 $m \le f(x) \le M$，$x \in [a, b]$，则：
>
> $$\boxed{m(b - a) \le \int_a^b f(x)\,\mathrm{d}x \le M(b - a)}$$

**几何意义**：曲边梯形的面积介于以最小值和最大值为高的两个矩形面积之间。

### 性质 5：积分中值定理

> 若 $f(x)$ 在 $[a, b]$ 上连续，则至少存在一点 $\xi \in [a, b]$，使得：
>
> $$\boxed{\int_a^b f(x)\,\mathrm{d}x = f(\xi)(b - a)}$$
>
> 即 $f(\xi) = \dfrac{1}{b-a}\displaystyle\int_a^b f(x)\,\mathrm{d}x$，称为 $f(x)$ 在 $[a, b]$ 上的**平均值**。

**几何意义**：曲边梯形的面积等于以 $f(\xi)$ 为高、$[a, b]$ 为底的矩形面积。

### 性质 6：对称区间上的积分

>
> $$\int_{-a}^{a} f(x)\,\mathrm{d}x = \begin{cases} 0, & \text{若 } f(x) \text{ 为奇函数} \\ 2\displaystyle\int_0^a f(x)\,\mathrm{d}x, & \text{若 } f(x) \text{ 为偶函数} \end{cases}$$
>
> **更一般地**：
> $$\int_{-a}^{a} f(x)\,\mathrm{d}x = \int_0^a [f(x) + f(-x)]\,\mathrm{d}x$$

> 若 $f(x)$ 以 $T$ 为周期，则：
> $$\int_a^{a+T} f(x)\,\mathrm{d}x = \int_0^T f(x)\,\mathrm{d}x$$
> 即周期函数在一个周期上的积分与起点 $a$ 无关。

---

## 五、定积分与不定积分的区别

| 比较项 | 不定积分 $\int f(x)\mathrm{d}x$ | 定积分 $\int_a^b f(x)\mathrm{d}x$ |
|--------|------|------|
| **结果** | 函数族 $F(x) + C$ | 确定的数值 |
| **几何意义** | 积分曲线族 | 曲边梯形面积（代数面积） |
| **变量** | $x$ 是自变量 | $x$ 是哑变量（积分变量可替换） |
| **存在条件** | 需存在原函数 | $f(x)$ 可积即可 |

---

## 六、典型例题

### 例 1：利用定义求极限

**题目**：求 $\displaystyle\lim_{n\to\infty}\sum_{i=1}^{n}\frac{1}{n+i}$

**解**：

$$\sum_{i=1}^{n}\frac{1}{n+i} = \sum_{i=1}^{n}\frac{1}{n}\cdot\frac{1}{1 + \frac{i}{n}}$$

这是 $f(x) = \frac{1}{1+x}$ 在 $[0, 1]$ 上取 $\xi_i = \frac{i}{n}$，$\Delta x_i = \frac{1}{n}$ 的黎曼和：

$$\lim_{n\to\infty}\sum_{i=1}^{n}\frac{1}{n}\cdot\frac{1}{1 + \frac{i}{n}} = \int_0^1 \frac{1}{1+x}\,\mathrm{d}x = \ln(1+x)\Big|_0^1 = \ln 2$$

$$\boxed{\lim_{n\to\infty}\sum_{i=1}^{n}\frac{1}{n+i} = \ln 2}$$

---

### 例 2：比较积分大小

**题目**：比较 $\displaystyle I_1 = \int_0^1 x\,\mathrm{d}x$，$I_2 = \int_0^1 x^2\,\mathrm{d}x$，$I_3 = \int_0^1 \sqrt{x}\,\mathrm{d}x$ 的大小。

**解**：

在 $[0, 1]$ 上，$x^2 \le x \le \sqrt{x}$（当 $0 < x < 1$ 时严格不等）

由保号性：$I_2 < I_1 < I_3$

验证：$I_1 = \frac{1}{2}$，$I_2 = \frac{1}{3}$，$I_3 = \frac{2}{3}$，确实 $\frac{1}{3} < \frac{1}{2} < \frac{2}{3}$。

---

### 例 3：估值

**题目**：估计 $\displaystyle\int_1^4 \frac{1}{1+x^2}\,\mathrm{d}x$ 的范围。

**解**：

$f(x) = \frac{1}{1+x^2}$ 在 $[1, 4]$ 上单调递减，故：

$$m = f(4) = \frac{1}{17}, \quad M = f(1) = \frac{1}{2}$$

由估值定理：

$$\frac{1}{17}\times 3 \le \int_1^4 \frac{1}{1+x^2}\,\mathrm{d}x \le \frac{1}{2}\times 3$$

$$\boxed{\frac{3}{17} \le \int_1^4 \frac{1}{1+x^2}\,\mathrm{d}x \le \frac{3}{2}}$$

---

### 例 4：奇偶性应用

**题目**：求 $\displaystyle\int_{-\pi}^{\pi} (x^3\cos x + x^2\sin x)\,\mathrm{d}x$

**解**：

- $x^3\cos x$：$x^3$ 是奇函数，$\cos x$ 是偶函数，乘积为**奇函数** → 积分为 $0$
- $x^2\sin x$：$x^2$ 是偶函数，$\sin x$ 是奇函数，乘积为**奇函数** → 积分为 $0$

$$\boxed{\int_{-\pi}^{\pi} (x^3\cos x + x^2\sin x)\,\mathrm{d}x = 0}$$

---

### 例 5：积分中值定理应用

**题目**：设 $f(x)$ 在 $[0, 1]$ 上连续，且 $\int_0^1 f(x)\,\mathrm{d}x = 0$，证明存在 $\xi \in (0, 1)$ 使 $f(\xi) = 0$。

**证明**：

由积分中值定理，存在 $\xi \in [0, 1]$ 使：

$$f(\xi) = \frac{1}{1-0}\int_0^1 f(x)\,\mathrm{d}x = 0$$

若 $\xi \in (0, 1)$ 则直接得证。若 $\xi = 0$ 或 $\xi = 1$，可结合连续性和反证法进一步证明存在 $\xi \in (0, 1)$。

---

## 📝 总结

| 知识点 | 要点 |
|--------|------|
| **定积分定义** | 黎曼和的极限 $\lim\limits_{\lambda\to 0}\sum f(\xi_i)\Delta x_i$ |
| **几何意义** | 曲边梯形的代数面积（有正有负） |
| **6 条性质** | 线性、区间可加、保号、估值、积分中值、奇偶性 |
| **可积条件** | 连续必可积；有界+有限间断点可积 |
| **核心定理** | 积分中值定理 $\int_a^b f(x)\mathrm{d}x = f(\xi)(b-a)$ |

> 1. 定积分的结果是**数值**，不是函数
> 2. 积分变量是**哑变量**，$\int_a^b f(x)\mathrm{d}x = \int_a^b f(t)\mathrm{d}t$
> 3. 保号性要求 $f(x) \ge 0$ 在**整个区间**上成立
> 4. 积分中值定理中 $\xi \in [a, b]$（闭区间），加强版才说 $\xi \in (a, b)$

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 32：定积分的计算：积分上限的函数]] — 计算
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 33：反常积分]] — 反常积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 28：不定积分]] — 不定积分
