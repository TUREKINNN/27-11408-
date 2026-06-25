---
title: "Lecture 4：数列极限的概念"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 数列极限, 极限定义, ε-N语言]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 4：数列极限的概念

> 数列极限是整个微积分的基石。本讲从直观理解出发，严格定义数列极限（$\varepsilon-N$ 语言），并通过大量例子说明如何用定义证明极限。

---

## 一、直观理解

### 1.1 什么是极限？

> 数列 $\{a_n\}$ 的极限为 $A$，意思是当 $n$ **充分大**时，$a_n$ 可以**任意接近** $A$。
>
> - "充分大"：存在某个 $N$，当 $n > N$ 时
> - "任意接近"：$|a_n - A|$ 可以小于任意给定的正数

**例子**：$a_n = \frac{1}{n}$

| $n$ | 1 | 10 | 100 | 1000 | 10000 |
|-----|---|----|----|------|-------|
| $a_n$ | 1 | 0.1 | 0.01 | 0.001 | 0.0001 |

可以看到 $a_n$ 越来越接近 $0$，我们说 $\lim_{n \to \infty} \frac{1}{n} = 0$。

### 1.2 几何意义

在数轴上，$a_n \to A$ 意味着从某项开始，所有 $a_n$ 都落在 $A$ 的 $\varepsilon$ 邻域 $(A - \varepsilon, A + \varepsilon)$ 内。

```
    ←——|——|——|——|——|——|——|——|——|——→
       a_N    a_{N+2}   A    a_{N+1}   a_{N+3}
              ←  ε  →←  ε  →
```

---

## 二、概念定义

### 2.1 数列极限的 $\varepsilon-N$ 定义

> 设 $\{a_n\}$ 为数列，$A$ 为常数。若对**任意给定**的 $\varepsilon > 0$，**存在**正整数 $N$，使得当 $n > N$ 时，都有
> $$|a_n - A| < \varepsilon$$
> 则称数列 $\{a_n\}$ **收敛**于 $A$，记为
> $$\lim_{n \to \infty} a_n = A$$
>
> 等价表述：$\forall \varepsilon > 0$，$\exists N \in \mathbb{N}^+$，$\forall n > N$：$|a_n - A| < \varepsilon$

**不收敛的数列称为发散数列**。

### 2.2 定义的深层理解

> 1. **$\varepsilon$ 的任意性**：$\varepsilon$ 可以任意小，这保证了 $a_n$ 可以任意接近 $A$
> 2. **$N$ 的存在性**：$N$ 依赖于 $\varepsilon$，通常 $\varepsilon$ 越小，$N$ 越大
> 3. **$N$ 不唯一**：只要找到一个满足条件的 $N$ 即可，更大的 $N$ 也满足
> 4. **$\forall n > N$**：不是某个特定的 $n$，而是从第 $N+1$ 项开始的**所有项**
> 5. **$|a_n - A| < \varepsilon$ 而非 $\leq$**：用 $<$ 和 $\leq$ 是等价的，但习惯用 $<$

### 2.3 用定义证明极限的步骤

> **第一步**：对任意给定的 $\varepsilon > 0$
>
> **第二步**：由 $|a_n - A| < \varepsilon$ 解出 $n > $ 某个关于 $\varepsilon$ 的表达式
>
> **第三步**：取 $N = $（该表达式的整数部分或上取整）
>
> **第四步**：验证当 $n > N$ 时 $|a_n - A| < \varepsilon$ 成立

---

## 三、用定义证明极限的例子

### 例 1：证明 $\lim_{n \to \infty} \frac{1}{n} = 0$

**证明**：

对任意 $\varepsilon > 0$，要使 $|\frac{1}{n} - 0| = \frac{1}{n} < \varepsilon$，只需 $n > \frac{1}{\varepsilon}$。

取 $N = [\frac{1}{\varepsilon}]$（取整），则当 $n > N$ 时，

$$|a_n - 0| = \frac{1}{n} < \frac{1}{N+1} \leq \frac{1}{\frac{1}{\varepsilon}} = \varepsilon$$

（严格来说 $\frac{1}{n} \leq \frac{1}{N+1} < \frac{1}{1/\varepsilon} = \varepsilon$）

所以 $\lim_{n \to \infty} \frac{1}{n} = 0$。$\blacksquare$

### 例 2：证明 $\lim_{n \to \infty} \frac{n}{n+1} = 1$

**证明**：

对任意 $\varepsilon > 0$，要使 $|\frac{n}{n+1} - 1| = |\frac{-1}{n+1}| = \frac{1}{n+1} < \varepsilon$，

只需 $n + 1 > \frac{1}{\varepsilon}$，即 $n > \frac{1}{\varepsilon} - 1$。

取 $N = \max\{1, [\frac{1}{\varepsilon} - 1]\}$，则当 $n > N$ 时，

$$|\frac{n}{n+1} - 1| = \frac{1}{n+1} < \varepsilon$$

所以 $\lim_{n \to \infty} \frac{n}{n+1} = 1$。$\blacksquare$

### 例 3：证明 $\lim_{n \to \infty} \frac{n^2 + n}{2n^2 + 1} = \frac{1}{2}$

**证明**：

$$|\frac{n^2+n}{2n^2+1} - \frac{1}{2}| = |\frac{2(n^2+n) - (2n^2+1)}{2(2n^2+1)}| = |\frac{2n-1}{2(2n^2+1)}| = \frac{2n-1}{2(2n^2+1)}$$

当 $n \geq 1$ 时，$2n - 1 < 2n$，$2(2n^2+1) > 4n^2$，所以

$$\frac{2n-1}{2(2n^2+1)} < \frac{2n}{4n^2} = \frac{1}{2n}$$

要使 $\frac{1}{2n} < \varepsilon$，只需 $n > \frac{1}{2\varepsilon}$。

取 $N = [\frac{1}{2\varepsilon}] + 1$，则当 $n > N$ 时，$|a_n - \frac{1}{2}| < \varepsilon$。

所以 $\lim_{n \to \infty} \frac{n^2+n}{2n^2+1} = \frac{1}{2}$。$\blacksquare$

---

## 四、数列极限的基本性质

### 4.1 唯一性

> 若 $\lim_{n \to \infty} a_n = A$ 且 $\lim_{n \to \infty} a_n = B$，则 $A = B$。
>
> 即：**收敛数列的极限是唯一的**。

**证明思路**：反证法。假设 $A \neq B$，取 $\varepsilon = \frac{|A-B|}{2} > 0$，由极限定义找到矛盾。

### 4.2 收敛数列的有界性

> 若 $\lim_{n \to \infty} a_n = A$（有限），则数列 $\{a_n\}$ **有界**，即存在 $M > 0$，使得 $|a_n| \leq M$ 对所有 $n$ 成立。

**证明**：

取 $\varepsilon = 1$，存在 $N$，当 $n > N$ 时 $|a_n - A| < 1$，从而 $|a_n| < |A| + 1$。

取 $M = \max\{|a_1|, |a_2|, \ldots, |a_N|, |A|+1\}$，则对所有 $n$，$|a_n| \leq M$。

> 有界数列不一定收敛。反例：$a_n = (-1)^n$ 有界但不收敛。

### 4.3 收敛数列的保号性

> 若 $\lim_{n \to \infty} a_n = A > 0$，则存在 $N$，当 $n > N$ 时 $a_n > \frac{A}{2} > 0$。
>
> 更一般地：若 $A > 0$，则 $\exists N$，$\forall n > N$：$a_n > 0$。
>
> 若 $\lim_{n \to \infty} a_n = A < 0$，则 $\exists N$，$\forall n > N$：$a_n < 0$。

### 4.4 收敛数列的四则运算

> 设 $\lim_{n \to \infty} a_n = A$，$\lim_{n \to \infty} b_n = B$，则：
> 1. $\lim_{n \to \infty}(a_n \pm b_n) = A \pm B$
> 2. $\lim_{n \to \infty}(a_n \cdot b_n) = A \cdot B$
> 3. $\lim_{n \to \infty}\frac{a_n}{b_n} = \frac{A}{B}$（$B \neq 0$）
> 4. $\lim_{n \to \infty}(c \cdot a_n) = cA$（$c$ 为常数）

---

## 五、常用结论

### 5.1 常见数列极限

$$\lim_{n \to \infty} \frac{1}{n^k} = 0 \quad (k > 0)$$

$$\lim_{n \to \infty} q^n = 0 \quad (|q| < 1)$$

$$\lim_{n \to \infty} \sqrt[n]{a} = 1 \quad (a > 0)$$

$$\lim_{n \to \infty} \sqrt[n]{n} = 1$$

$$\lim_{n \to \infty} \frac{a^n}{n!} = 0 \quad (a \text{ 为任意实数})$$

$$\lim_{n \to \infty} \frac{n^k}{a^n} = 0 \quad (a > 1, k > 0)$$

### 5.2 数列与子数列

> - 若 $\lim_{n \to \infty} a_n = A$，则 $\{a_n\}$ 的**任何**子数列也收敛于 $A$
> - 反过来：若能找到两个子数列收敛于不同的极限，则原数列发散
> - 例：$a_n = (-1)^n$，偶数项子列收敛于 $1$，奇数项子列收敛于 $-1$，所以 $\{a_n\}$ 发散

---

## 六、典型例题

### 例题 1：用定义证明

**题目**：用 $\varepsilon-N$ 定义证明 $\lim_{n \to \infty} \frac{3n+1}{2n-1} = \frac{3}{2}$

**证明**：

$$|\frac{3n+1}{2n-1} - \frac{3}{2}| = |\frac{2(3n+1) - 3(2n-1)}{2(2n-1)}| = |\frac{5}{2(2n-1)}| = \frac{5}{2(2n-1)}$$

当 $n \geq 1$ 时，$2n - 1 \geq n$，所以 $\frac{5}{2(2n-1)} \leq \frac{5}{2n}$。

要使 $\frac{5}{2n} < \varepsilon$，只需 $n > \frac{5}{2\varepsilon}$。

取 $N = [\frac{5}{2\varepsilon}] + 1$，则当 $n > N$ 时，

$$|\frac{3n+1}{2n-1} - \frac{3}{2}| < \frac{5}{2n} < \varepsilon$$

所以 $\lim_{n \to \infty} \frac{3n+1}{2n-1} = \frac{3}{2}$。$\blacksquare$

### 例题 2：利用子数列判断发散

**题目**：证明 $a_n = \sin\frac{n\pi}{2}$ 发散。

**证明**：

取子数列 $n_k = 4k$：$a_{4k} = \sin 2k\pi = 0 \to 0$

取子数列 $n_k = 4k+1$：$a_{4k+1} = \sin(2k\pi + \frac{\pi}{2}) = 1 \to 1$

因为两个子数列收敛于不同的极限，所以原数列 $\{a_n\}$ 发散。$\blacksquare$

### 例题 3：求数列极限

**题目**：求 $\lim_{n \to \infty} (\sqrt{n^2+n} - n)$

**解题步骤**：

分子有理化：
$$\sqrt{n^2+n} - n = \frac{(\sqrt{n^2+n} - n)(\sqrt{n^2+n} + n)}{\sqrt{n^2+n} + n} = \frac{n^2+n-n^2}{\sqrt{n^2+n}+n} = \frac{n}{\sqrt{n^2+n}+n}$$

$$= \frac{n}{n(\sqrt{1+\frac{1}{n}}+1)} = \frac{1}{\sqrt{1+\frac{1}{n}}+1} \to \frac{1}{\sqrt{1}+1} = \frac{1}{2}$$

所以 $\lim_{n \to \infty} (\sqrt{n^2+n} - n) = \frac{1}{2}$。

---

## 七、真题演练

### 真题 1（2003年 数一）

**题目**：设 $\{a_n\}$，$\{b_n\}$，$\{c_n\}$ 均为非负数列，且 $\lim_{n \to \infty} a_n = 0$，$\lim_{n \to \infty} b_n = 1$，$\lim_{n \to \infty} c_n = \infty$，则下列正确的是：

(A) $a_n < b_n$ 对所有 $n$ 成立

(B) $b_n < c_n$ 对所有 $n$ 成立

(C) $\lim_{n \to \infty} a_n c_n$ 不存在

(D) $\lim_{n \to \infty} b_n c_n$ 不存在

**解答**：

(A) 错：$a_n$ 和 $b_n$ 的大小关系不确定，可能有 $a_n > b_n$ 的项

(B) 错：同理，$b_n$ 和 $c_n$ 的大小关系不确定

(C) 错：$a_n c_n$ 是 "$0 \cdot \infty$" 型不定式，可能收敛也可能发散

(D) 正确：$b_n \to 1 > 0$，由保号性，存在 $N$，当 $n > N$ 时 $b_n > \frac{1}{2}$，又 $c_n \to +\infty$，所以 $b_n c_n \to +\infty$（不存在有限极限）

**答案**：(D)

### 真题 2（2008年 数一）

**题目**：设函数 $f(x)$ 在 $(-\infty, +\infty)$ 上单调有界，$\{x_n\}$ 为数列，则下列命题正确的是：

(A) 若 $\{x_n\}$ 收敛，则 $\{f(x_n)\}$ 收敛

(B) 若 $\{x_n\}$ 单调，则 $\{f(x_n)\}$ 收敛

(C) 若 $\{f(x_n)\}$ 收敛，则 $\{x_n\}$ 收敛

(D) 若 $\{f(x_n)\}$ 单调，则 $\{x_n\}$ 收敛

**解答**：

(A) 若 $x_n \to x_0$，由 $f$ 单调有界，$f(x_n)$ 的子列应收敛到同一个值（因为 $f$ 单调，单侧极限存在），所以 $\{f(x_n)\}$ 收敛。✅

(B) $f$ 单调有界，$\{x_n\}$ 单调。若 $x_n$ 有界，则 $x_n$ 收敛，由(A)知 $f(x_n)$ 收敛；若 $x_n$ 无界单调增，$f(x_n)$ 单调有界故收敛。✅

(C) 反例：$f(x) = \arctan x$，$x_n = n$，$f(x_n) = \arctan n \to \frac{\pi}{2}$，但 $x_n$ 发散。❌

(D) 反例同(C)。❌

**答案**：(A)(B)

---

## 八、易错点提醒

> 1. **混淆"收敛"与"有界"**：有界是收敛的必要条件但非充分条件
> 2. **$N$ 的选取**：证明时 $N$ 必须是正整数，且 $N$ 只与 $\varepsilon$ 有关，不能依赖 $n$
> 3. **放缩方向**：证明 $|a_n - A| < \varepsilon$ 时，只能**放大** $|a_n - A|$，不能缩小
> 4. **$\varepsilon$ 的任意性**：不能取特定的 $\varepsilon$（如 $\varepsilon = 1$）来证明极限
> 5. **子数列方法**：要证明发散，只需找两个收敛到不同值的子数列；但要证明收敛，必须验证所有子数列

> - 形如 $\sqrt{n^2+n} - n$ 的极限不能直接代入 $\infty - \infty$，必须有理化
> - $\lim_{n \to \infty} q^n$ 在 $|q| > 1$ 时为 $\infty$（发散），不是极限为 $\infty$（极限不存在）
> - 数列极限中的 $n$ 只取正整数，与函数极限中 $x$ 可以取任意实数不同

---

## 补充内容

> 武忠祥《2021考研高等数学0基础课》讲义 (2)--1.3-1.4笔记小结

### 补充一：极限思想的起源——割圆术

> 极限的思想可以追溯到古代中国数学家刘徽的"割圆术"：
>
> 用圆内接正多边形逼近圆的面积：
> - 正六边形面积 $A_1$
> - 正十二边形面积 $A_2$
> - 正 $6 \times 2^{n-1}$ 边形面积 $A_n$
>
> 当 $n \to \infty$ 时，$A_n \to S$（圆的面积）
>
> 这就是数列极限的朴素思想：**用已知的量无限逼近未知的量**。

### 补充二：$\varepsilon-N$ 定义中 $\varepsilon$ 和 $N$ 的作用

>
> **$\varepsilon$ 的作用**：
> - $\varepsilon$ 具有**任意性**：对任意小的正数都要成立
> - $\varepsilon$ 具有**给定性**：证明过程中先给定，再找 $N$
> - $\varepsilon$ 可以任意小，这是极限精确性的保证
> - 但证明时不能取特殊的 $\varepsilon$（如 $\varepsilon = 1$）来证明
>
> **$N$ 的作用及 $N$ 与 $\varepsilon$ 的关系**：
> - $N$ 的作用是"分界"：$n > N$ 之后的所有项满足条件
> - $N$ 由 $\varepsilon$ 确定，通常 $\varepsilon$ 越小，$N$ 越大
> - $N$ 不唯一：找到一个即可，更大的也行
> - $N$ 只依赖于 $\varepsilon$，不能依赖于 $n$

### 补充三：用定义证明 $\lim_{n \to \infty} q^n = 0$（$|q| < 1$）

>
> **当 $q = 0$ 时**：$q^n = 0$，极限显然为 $0$。
>
> **当 $0 < |q| < 1$ 时**：令 $|q| = \frac{1}{1+h}$（$h > 0$），则
> $$|q^n - 0| = |q|^n = \frac{1}{(1+h)^n}$$
>
> 由 Bernoulli 不等式：$(1+h)^n \geq 1 + nh$，故
> $$|q^n| \leq \frac{1}{1+nh} < \frac{1}{nh}$$
>
> 要使 $\frac{1}{nh} < \varepsilon$，只需 $n > \frac{1}{h\varepsilon}$。
>
> 取 $N = \left[\frac{1}{h\varepsilon}\right] + 1$，则当 $n > N$ 时 $|q^n| < \varepsilon$。
>
> 故 $\lim_{n \to \infty} q^n = 0$。$\blacksquare$

### 补充四：用定义证明 $\lim_{n \to \infty} \sqrt[n]{n} = 1$

>
> 令 $\sqrt[n]{n} = 1 + h_n$（$h_n > 0$），则
> $$n = (1+h_n)^n \geq 1 + nh_n + \frac{n(n-1)}{2}h_n^2 \geq \frac{n(n-1)}{2}h_n^2$$
>
> 故 $h_n^2 \leq \frac{2}{n-1}$（$n \geq 2$），即 $0 < h_n \leq \sqrt{\frac{2}{n-1}}$。
>
> 要使 $h_n < \varepsilon$，只需 $\sqrt{\frac{2}{n-1}} < \varepsilon$，即 $n > \frac{2}{\varepsilon^2} + 1$。
>
> 取 $N = \left[\frac{2}{\varepsilon^2}\right] + 2$，则当 $n > N$ 时 $|\sqrt[n]{n} - 1| < \varepsilon$。
>
> 故 $\lim_{n \to \infty} \sqrt[n]{n} = 1$。$\blacksquare$

### 补充五：收敛数列与子数列的充要条件

> $$\lim_{n \to \infty} x_n = a \Leftrightarrow \lim_{k \to \infty} x_{2k-1} = \lim_{k \to \infty} x_{2k} = a$$
>
> 即：数列收敛 $\Leftrightarrow$ **奇数项子列**和**偶数项子列**都收敛于同一极限。
>
> **推广**：数列收敛 $\Leftrightarrow$ **任意**子数列都收敛于同一极限。

> 要证明数列发散，只需找到**两个子数列收敛到不同值**，或者找到一个**发散的子数列**。
>
> 例如：$x_n = (-1)^n$，奇数项子列 $\to -1$，偶数项子列 $\to 1$，故发散。

### 补充六：保号性的推论（重要补充）

> 如果存在 $N > 0$，当 $n > N$ 时 $x_n \geq 0$（或 $x_n \leq 0$），且 $\lim_{n \to \infty} x_n = a$，则
> $$a \geq 0 \quad (\text{或 } a \leq 0)$$
>
> ⚠️ 注意：这里是**非严格**不等号！即使 $x_n > 0$ 对所有 $n$ 成立，也只能推出 $a \geq 0$，不能推出 $a > 0$。
>
> **反例**：$x_n = \frac{1}{n} > 0$，但 $\lim x_n = 0$。

### 补充七：更多典型数列极限

>
> **例**：$x_n = \frac{n + (-1)^{n-1}}{n}$，求 $\lim x_n$。
>
> $$x_n = 1 + \frac{(-1)^{n-1}}{n}$$
>
> 由于 $\left|\frac{(-1)^{n-1}}{n}\right| = \frac{1}{n} \to 0$，故 $x_n \to 1$。
>
> 这个例子说明：即使数列项中有振荡因子 $(-1)^{n-1}$，只要它被"压制"（除以 $n$），极限仍然存在。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 5：函数极限的概念]] — 函数极限
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 7：数列极限存在准则]] — 存在准则
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 10：求极限]] — 求极限方法
