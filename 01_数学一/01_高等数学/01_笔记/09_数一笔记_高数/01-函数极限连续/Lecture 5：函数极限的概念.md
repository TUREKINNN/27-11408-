---
title: "Lecture 5：函数极限的概念"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 函数极限, ε-δ语言, 单侧极限]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 5：函数极限的概念

> 函数极限是数列极限的推广，研究自变量趋向某一点或无穷时函数的变化趋势。本讲系统介绍函数极限的各种形式及其 $\varepsilon-\delta$ 定义。

---

## 一、函数极限的各种形式

### 1.1 六种极限形式

>
> | 类型 | 记号 | 含义 |
> |------|------|------|
> | $x \to x_0$ | $\lim_{x \to x_0} f(x) = A$ | $x$ 趋于有限值 $x_0$ |
> | $x \to x_0^+$ | $\lim_{x \to x_0^+} f(x) = A$ | $x$ 从右侧趋于 $x_0$（右极限） |
> | $x \to x_0^-$ | $\lim_{x \to x_0^-} f(x) = A$ | $x$ 从左侧趋于 $x_0$（左极限） |
> | $x \to +\infty$ | $\lim_{x \to +\infty} f(x) = A$ | $x$ 趋于正无穷 |
> | $x \to -\infty$ | $\lim_{x \to -\infty} f(x) = A$ | $x$ 趋于负无穷 |
> | $x \to \infty$ | $\lim_{x \to \infty} f(x) = A$ | $|x|$ 趋于无穷 |

---

## 二、$\varepsilon-\delta$ 定义

### 2.1 $x \to x_0$ 时的极限

> 设 $f(x)$ 在 $x_0$ 的某**去心邻域**内有定义，$A$ 为常数。若
> $$\forall \varepsilon > 0，\exists \delta > 0，\forall x：0 < |x - x_0| < \delta \Rightarrow |f(x) - A| < \varepsilon$$
> 则称 $x \to x_0$ 时 $f(x)$ 的极限为 $A$，记为 $\lim_{x \to x_0} f(x) = A$。

**关键点**：
- $0 < |x - x_0|$ 意味着 $x \neq x_0$，即极限与 $f(x_0)$ 的值无关
- $|x - x_0| < \delta$ 限制了 $x$ 在 $x_0$ 附近
- $|f(x) - A| < \varepsilon$ 保证了 $f(x)$ 接近 $A$

### 2.2 单侧极限

> $$\lim_{x \to x_0^+} f(x) = A \Leftrightarrow \forall \varepsilon > 0，\exists \delta > 0，\forall x：0 < x - x_0 < \delta \Rightarrow |f(x) - A| < \varepsilon$$

> $$\lim_{x \to x_0^-} f(x) = A \Leftrightarrow \forall \varepsilon > 0，\exists \delta > 0，\forall x：0 < x_0 - x < \delta \Rightarrow |f(x) - A| < \varepsilon$$

### 2.3 左右极限与极限的关系

> $$\lim_{x \to x_0} f(x) = A \Leftrightarrow \lim_{x \to x_0^+} f(x) = \lim_{x \to x_0^-} f(x) = A$$
>
> 即：**极限存在 $\Leftrightarrow$ 左右极限存在且相等**。

### 2.4 $x \to \infty$ 时的极限

> $$\lim_{x \to +\infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0，\exists X > 0，\forall x > X：|f(x) - A| < \varepsilon$$
>
> $$\lim_{x \to -\infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0，\exists X > 0，\forall x < -X：|f(x) - A| < \varepsilon$$
>
> $$\lim_{x \to \infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0，\exists X > 0，\forall |x| > X：|f(x) - A| < \varepsilon$$
>
> $\lim_{x \to \infty} f(x) = A \Leftrightarrow \lim_{x \to +\infty} f(x) = \lim_{x \to -\infty} f(x) = A$

---

## 三、函数极限的性质

### 3.1 唯一性

> 若 $\lim_{x \to x_0} f(x)$ 存在，则极限是唯一的。

### 3.2 局部有界性

> 若 $\lim_{x \to x_0} f(x) = A$，则存在 $\delta > 0$ 和 $M > 0$，使得当 $0 < |x - x_0| < \delta$ 时，$|f(x)| \leq M$。

**注意**：这只是"局部"有界，不是全局有界。

### 3.3 局部保号性

> 若 $\lim_{x \to x_0} f(x) = A > 0$，则存在 $\delta > 0$，当 $0 < |x - x_0| < \delta$ 时，$f(x) > \frac{A}{2} > 0$。
>
> 更一般地：若 $A > 0$，则在 $x_0$ 的某个去心邻域内 $f(x) > 0$。

### 3.4 四则运算法则

> 设 $\lim_{x \to x_0} f(x) = A$，$\lim_{x \to x_0} g(x) = B$，则：
> 1. $\lim[f(x) \pm g(x)] = A \pm B$
> 2. $\lim[f(x) \cdot g(x)] = A \cdot B$
> 3. $\lim \frac{f(x)}{g(x)} = \frac{A}{B}$（$B \neq 0$）
> 4. $\lim[c \cdot f(x)] = cA$（$c$ 为常数）
> 5. $\lim[f(x)]^n = A^n$（$n$ 为正整数）

---

## 四、常用结论

### 4.1 基本极限

$$\lim_{x \to 0} \frac{\sin x}{x} = 1$$

$$\lim_{x \to 0} \frac{e^x - 1}{x} = 1$$

$$\lim_{x \to 0} \frac{\ln(1+x)}{x} = 1$$

$$\lim_{x \to 0} \frac{(1+x)^a - 1}{x} = a$$

$$\lim_{x \to \infty} (1 + \frac{1}{x})^x = e$$

$$\lim_{x \to 0} \frac{\tan x}{x} = 1$$

$$\lim_{x \to 0} \frac{\arcsin x}{x} = 1$$

$$\lim_{x \to 0} \frac{\arctan x}{x} = 1$$

### 4.2 幂指函数极限

> 若 $\lim f(x) = 1$，$\lim g(x) = \infty$，则
> $$\lim f(x)^{g(x)} = e^{\lim g(x)[f(x)-1]}$$
>
> 特别地：
> $$\lim_{x \to 0} (1+x)^{\frac{1}{x}} = e$$
> $$\lim_{x \to \infty} (1+\frac{1}{x})^x = e$$

### 4.3 函数极限与数列极限的关系

> $\lim_{x \to x_0} f(x) = A$ 的**充要条件**是：对任意满足 $x_n \to x_0$（$x_n \neq x_0$）的数列 $\{x_n\}$，都有 $\lim_{n \to \infty} f(x_n) = A$。
>
> **应用**：
> - 用数列极限证函数极限存在
> - 用特殊数列证函数极限**不存在**（找两个不同数列使极限不同）

---

## 五、典型例题

### 例题 1：分段函数在分界点的极限

**题目**：设 $f(x) = \begin{cases} x^2 + 1, & x < 0 \\ 2x + 1, & x \geq 0 \end{cases}$，求 $\lim_{x \to 0} f(x)$。

**解题步骤**：

**左极限**：
$$\lim_{x \to 0^-} f(x) = \lim_{x \to 0^-} (x^2 + 1) = 0 + 1 = 1$$

**右极限**：
$$\lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} (2x + 1) = 0 + 1 = 1$$

因为 $\lim_{x \to 0^-} f(x) = \lim_{x \to 0^+} f(x) = 1$，所以 $\lim_{x \to 0} f(x) = 1$。

### 例题 2：含绝对值函数的极限

**题目**：讨论 $\lim_{x \to 0} \frac{|x|}{x}$。

**解题步骤**：

$$f(x) = \frac{|x|}{x} = \begin{cases} 1, & x > 0 \\ -1, & x < 0 \end{cases}$$

**左极限**：$\lim_{x \to 0^-} f(x) = -1$

**右极限**：$\lim_{x \to 0^+} f(x) = 1$

因为左右极限不相等，所以 $\lim_{x \to 0} \frac{|x|}{x}$ **不存在**。

### 例题 3：用 Heine 定理证极限不存在

**题目**：证明 $\lim_{x \to 0} \sin\frac{1}{x}$ 不存在。

**证明**：

取 $x_n = \frac{1}{2n\pi + \frac{\pi}{2}} \to 0$，则 $f(x_n) = \sin(2n\pi + \frac{\pi}{2}) = 1 \to 1$

取 $y_n = \frac{1}{2n\pi} \to 0$，则 $f(y_n) = \sin(2n\pi) = 0 \to 0$

两个数列趋于 $0$，但函数值的极限不同，所以 $\lim_{x \to 0} \sin\frac{1}{x}$ 不存在。$\blacksquare$

### 例题 4：用 $\varepsilon-\delta$ 证明极限

**题目**：用定义证明 $\lim_{x \to 2} (3x - 1) = 5$

**证明**：

对任意 $\varepsilon > 0$，要使 $|(3x-1) - 5| = |3x - 6| = 3|x-2| < \varepsilon$，

只需 $|x - 2| < \frac{\varepsilon}{3}$。

取 $\delta = \frac{\varepsilon}{3}$，则当 $0 < |x - 2| < \delta$ 时，

$$|(3x-1) - 5| = 3|x - 2| < 3 \cdot \frac{\varepsilon}{3} = \varepsilon$$

所以 $\lim_{x \to 2} (3x-1) = 5$。$\blacksquare$

---

## 六、真题演练

### 真题 1（2000年 数一）

**题目**：求 $\lim_{x \to 0} \frac{\sin x}{x + \sin x}$

**解答**：

$$\lim_{x \to 0} \frac{\sin x}{x + \sin x} = \lim_{x \to 0} \frac{\frac{\sin x}{x}}{1 + \frac{\sin x}{x}} = \frac{1}{1+1} = \frac{1}{2}$$

### 真题 2（2010年 数一）

**题目**：极限 $\lim_{x \to \infty} \left[\frac{x^2}{(x-a)(x+b)}\right]^x$

**解答**：

$$\frac{x^2}{(x-a)(x+b)} = \frac{x^2}{x^2 + (b-a)x - ab} = \frac{1}{1 + \frac{(b-a)x - ab}{x^2}}$$

$$= \frac{1}{1 + \frac{b-a}{x} - \frac{ab}{x^2}} \approx 1 - \frac{b-a}{x} + O(\frac{1}{x^2})$$

这是 $1^\infty$ 型：

$$\lim_{x \to \infty} \left[\frac{x^2}{(x-a)(x+b)}\right]^x = e^{\lim_{x \to \infty} x \cdot \left[\frac{x^2}{(x-a)(x+b)} - 1\right]}$$

$$= e^{\lim_{x \to \infty} x \cdot \frac{x^2 - (x-a)(x+b)}{(x-a)(x+b)}} = e^{\lim_{x \to \infty} x \cdot \frac{ax - bx + ab}{(x-a)(x+b)}}$$

$$= e^{\lim_{x \to \infty} \frac{(a-b)x^2 + abx}{(x-a)(x+b)}} = e^{a-b}$$

**答案**：$e^{a-b}$

### 真题 3（2016年 数一）

**题目**：$\lim_{x \to 0} \frac{\int_0^x t \ln(1+t\sin t) \, dt}{1 - \cos x^2}$

**解答**：

当 $x \to 0$ 时，$1 - \cos x^2 \sim \frac{(x^2)^2}{2} = \frac{x^4}{2}$

对分子用洛必达法则：
$$\lim_{x \to 0} \frac{x \ln(1+x\sin x)}{2x^3} \cdot 2 = \lim_{x \to 0} \frac{x \cdot x \sin x}{x^4} = \lim_{x \to 0} \frac{\sin x}{x} \cdot \frac{1}{1} = 1$$

（用到了 $\ln(1+t) \sim t$ 和 $\sin x \sim x$）

---

## 七、易错点提醒

> 1. **$0 < |x - x_0|$ 的含义**：函数极限与 $f(x_0)$ 无关，$f$ 甚至可以在 $x_0$ 处无定义
> 2. **左右极限必须分别计算**：分段函数、含绝对值函数、$e^{\frac{1}{x}}$ 类函数在分界点必须分别求左右极限
> 3. **$\infty$ 不是极限值**：$\lim_{x \to x_0} f(x) = \infty$ 表示极限不存在（趋于无穷），而不是极限等于无穷
> 4. **四则运算的前提**：使用四则运算前必须确认各部分极限存在
> 5. **Heine 定理的运用方向**：
>    - 找到一个子列极限不存在 $\Rightarrow$ 函数极限不存在 ✅
>    - 找到一个子列极限存在 $\not\Rightarrow$ 函数极限存在 ❌

> - $\lim_{x \to 0} e^{\frac{1}{x}}$：右极限为 $+\infty$，左极限为 $0$，所以极限不存在
> - $\lim_{x \to 0} \arctan\frac{1}{x}$：右极限为 $\frac{\pi}{2}$，左极限为 $-\frac{\pi}{2}$
> - $\lim_{x \to \infty} \frac{\sin x}{x} = 0$（有界乘无穷小），但 $\lim_{x \to 0} \frac{\sin x}{x} = 1$

---

## 补充内容

> 武忠祥《2021考研高等数学0基础课》讲义 (3)--1.5-1.6笔记小结

### 补充一：函数极限的统一定义

> $\lim f(x) = A \Leftrightarrow \forall \varepsilon > 0$，$\exists$ 时刻，从此时刻以后，恒有 $|f(x) - A| < \varepsilon$。
>
> 不同极限过程中"时刻"和"从此时刻以后"的含义：

| 过程 | $n \to \infty$ | $x \to \infty$ | $x \to +\infty$ | $x \to -\infty$ |
|------|:-:|:-:|:-:|:-:|
| 时刻 | $N$ | $N$ | $N$ | $N$ |
| 从此时刻以后 | $n > N$ | $|x| > N$ | $x > N$ | $x < -N$ |
| $f(x)$ | $|f(x) - A| < \varepsilon$ | $|f(x) - A| < \varepsilon$ | $|f(x) - A| < \varepsilon$ | $|f(x) - A| < \varepsilon$ |

| 过程 | $x \to x_0$ | $x \to x_0^+$ | $x \to x_0^-$ |
|------|:-:|:-:|:-:|
| 时刻 | $\delta$ | $\delta$ | $\delta$ |
| 从此时刻以后 | $0 < |x - x_0| < \delta$ | $0 < x - x_0 < \delta$ | $-\delta < x - x_0 < 0$ |
| $f(x)$ | $|f(x) - A| < \varepsilon$ | $|f(x) - A| < \varepsilon$ | $|f(x) - A| < \varepsilon$ |

### 补充二：$\varepsilon-\delta$ 定义的几何意义

> $\lim_{x \to x_0} f(x) = A$ 的几何意义：
>
> 对任意 $\varepsilon > 0$（无论多小），总存在 $\delta > 0$，使得当 $x$ 落在 $x_0$ 的 $\delta$ 邻域内（$x \neq x_0$）时，曲线 $y = f(x)$ 上对应的点全部落在水平带状区域 $(A - \varepsilon, A + \varepsilon)$ 内。
>
> 形象地说：**曲线 $y = f(x)$ 在 $x_0$ 附近被"夹"在两条水平线 $y = A - \varepsilon$ 和 $y = A + \varepsilon$ 之间**。

### 补充三：用 $\varepsilon-\delta$ 证明 $\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = 2$

>
> **证明**：
>
> 对任意 $\varepsilon > 0$，当 $x \neq 1$ 时：
> $$\left|\frac{x^2-1}{x-1} - 2\right| = \left|\frac{(x+1)(x-1)}{x-1} - 2\right| = |x + 1 - 2| = |x - 1|$$
>
> 要使 $|x - 1| < \varepsilon$，取 $\delta = \varepsilon$。
>
> 则当 $0 < |x - 1| < \delta$ 时：
> $$\left|\frac{x^2-1}{x-1} - 2\right| = |x - 1| < \delta = \varepsilon$$
>
> 故 $\lim_{x \to 1} \frac{x^2-1}{x-1} = 2$。$\blacksquare$
>
> > > 这里 $f(x) = \frac{x^2-1}{x-1}$ 在 $x = 1$ 处**无定义**，但极限仍然存在。
> > 这正说明**极限与函数在该点的值无关**。

### 补充四：$x \to \infty$ 时极限的严格定义

>
> $$\lim_{x \to +\infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0, \exists X > 0, \text{当 } x > X \text{ 时, 恒有 } |f(x) - A| < \varepsilon$$
>
> $$\lim_{x \to -\infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0, \exists X > 0, \text{当 } x < -X \text{ 时, 恒有 } |f(x) - A| < \varepsilon$$
>
> $$\lim_{x \to \infty} f(x) = A \Leftrightarrow \forall \varepsilon > 0, \exists X > 0, \text{当 } |x| > X \text{ 时, 恒有 } |f(x) - A| < \varepsilon$$

> 若 $\lim_{x \to \infty} f(x) = A$，则直线 $y = A$ 是曲线 $y = f(x)$ 的**水平渐近线**。
>
> 同样：
> - $\lim_{x \to +\infty} f(x) = A$ → 右侧有水平渐近线 $y = A$
> - $\lim_{x \to -\infty} f(x) = A$ → 左侧有水平渐近线 $y = A$

### 补充五：用定义证明 $\lim_{x \to \infty} \frac{\sin x}{x} = 0$

>
> **证明**：
>
> 对任意 $\varepsilon > 0$，要使 $\left|\frac{\sin x}{x} - 0\right| = \frac{|\sin x|}{|x|} \leq \frac{1}{|x|} < \varepsilon$，
>
> 只需 $|x| > \frac{1}{\varepsilon}$。
>
> 取 $X = \frac{1}{\varepsilon}$，则当 $|x| > X$ 时：
> $$\left|\frac{\sin x}{x}\right| \leq \frac{1}{|x|} < \frac{1}{X} = \varepsilon$$
>
> 故 $\lim_{x \to \infty} \frac{\sin x}{x} = 0$。$\blacksquare$

### 补充六：求极限的分式方法总结

>
> **1. $x \to x_0$ 时，代入法**：
> 若分母 $\neq 0$，直接代入。例如 $\lim_{x \to 1} \frac{x^2+x}{x^3-3x+5} = \frac{2}{3}$。
>
> **2. $x \to x_0$ 时，$\frac{0}{0}$ 型——约去零因子**：
> $$\lim_{x \to 1} \frac{x^2-x}{x^3-3x+2} = \lim_{x \to 1} \frac{x(x-1)}{(x-1)(x^2+x-2)} = \lim_{x \to 1} \frac{x}{x^2+x-2}$$
>
> **3. $x \to \infty$ 时——"抓大头"**：
> 分子分母同除最高次幂：
> $$\lim_{x \to \infty} \frac{a_n x^n + a_{n-1}x^{n-1} + \cdots}{b_m x^m + b_{m-1}x^{m-1} + \cdots} = \begin{cases} \frac{a_n}{b_m}, & n = m \\ 0, & n < m \\ \infty, & n > m \end{cases}$$

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 4：数列极限的概念]] — 数列极限
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 6：函数极限的性质]] — 极限性质
- Lecture 9：极限的概念、性质与存在准则 — 综合
