---
title: "Lecture 52：傅里叶级数"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 傅里叶级数, 傅里叶系数, 狄利克雷收敛定理, 奇偶函数展开]
difficulty: ★★★★★
exam_weight: ★★★★
created: 2026-06-16
---

# Lecture 52：傅里叶级数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★（数一特有考点，隔几年考一次） |
| **分值分布** | 约 4-10 分 |
| **题型** | 求傅里叶系数、写出傅里叶级数、利用狄利克雷定理求级数和 |
| **难度** | 较难 |

---

## 一、三角函数系与正交性

### 1.1 三角函数系

>
> $$1, \cos x, \sin x, \cos 2x, \sin 2x, \ldots, \cos nx, \sin nx, \ldots$$
>
> 即 $\{1, \cos nx, \sin nx\}_{n=1}^{\infty}$。

### 1.2 正交性

> 在区间 $[-\pi, \pi]$ 上（或任意长度为 $2\pi$ 的区间上），三角函数系中**任意两个不同函数**的乘积的积分为 $0$：
>
> $$\int_{-\pi}^{\pi} \cos nx \,dx = 0 \quad (n = 1, 2, 3, \ldots)$$
>
> $$\int_{-\pi}^{\pi} \sin nx \,dx = 0 \quad (n = 1, 2, 3, \ldots)$$
>
> $$\int_{-\pi}^{\pi} \cos mx \cos nx \,dx = 0 \quad (m \ne n)$$
>
> $$\int_{-\pi}^{\pi} \sin mx \sin nx \,dx = 0 \quad (m \ne n)$$
>
> $$\int_{-\pi}^{\pi} \cos mx \sin nx \,dx = 0 \quad (\forall m, n)$$
>
> 而自身平方的积分：
>
> $$\int_{-\pi}^{\pi} \cos^2 nx \,dx = \pi, \quad \int_{-\pi}^{\pi} \sin^2 nx \,dx = \pi \quad (n \ge 1)$$
>
> $$\int_{-\pi}^{\pi} 1^2 \,dx = 2\pi$$

> 正交性使得在计算傅里叶系数时，"交叉项"全部消失，只剩下"自相关"项。

---

## 二、周期为 $2\pi$ 的函数的傅里叶级数

### 2.1 傅里叶级数的定义

> 设 $f(x)$ 是以 $2\pi$ 为周期的函数，其**傅里叶级数**为：
>
> $$\boxed{f(x) \sim \frac{a_0}{2} + \sum_{n=1}^{\infty}(a_n \cos nx + b_n \sin nx)}$$
>
> 其中 $a_0, a_n, b_n$ 称为**傅里叶系数**。

### 2.2 傅里叶系数公式

>
> $$\boxed{a_0 = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\,dx}$$
>
> $$\boxed{a_n = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos nx\,dx \quad (n = 1, 2, 3, \ldots)}$$
>
> $$\boxed{b_n = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\sin nx\,dx \quad (n = 1, 2, 3, \ldots)}$$

> 假设 $f(x) = \dfrac{a_0}{2} + \sum(a_n\cos nx + b_n\sin nx)$，两边分别乘以 $1$、$\cos mx$、$\sin mx$ 后在 $[-\pi, \pi]$ 上积分，利用正交性即可得到系数公式。

### 2.3 积分区间的选择

> 由于 $f(x)$ 以 $2\pi$ 为周期，傅里叶系数的积分可以在**任意长度为 $2\pi$ 的区间**上计算：
>
> $$a_n = \frac{1}{\pi}\int_{c}^{c+2\pi} f(x)\cos nx\,dx$$
>
> 常用的区间选择：$[-\pi, \pi]$、$[0, 2\pi]$，取方便计算的那个。

---

## 三、狄利克雷收敛定理

> 设 $f(x)$ 以 $2\pi$ 为周期，若 $f(x)$ 在一个周期内满足：
>
> **条件①**：$f(x)$ 连续，或只有**有限个第一类间断点**
>
> **条件②**：$f(x)$ 只有**有限个极值点**（即分段单调）
>
> 则 $f(x)$ 的傅里叶级数在每一点 $x$ 处收敛，且：
>
> $$\boxed{\frac{a_0}{2} + \sum_{n=1}^{\infty}(a_n\cos nx + b_n\sin nx) = \frac{f(x^-) + f(x^+)}{2}}$$
>
> 即收敛到 $\dfrac{f(x^-) + f(x^+)}{2}$（左极限与右极限的平均值）。

> - 在 $f(x)$ 的**连续点**处，傅里叶级数收敛到 $f(x)$ 本身
> - 在 $f(x)$ 的**间断点** $x_0$ 处，傅里叶级数收敛到 $\dfrac{f(x_0^-) + f(x_0^+)}{2}$
> - 特别地，在区间**端点** $x = \pm\pi$ 处，收敛到 $\dfrac{f(-\pi^+) + f(\pi^-)}{2}$

---

## 四、周期为 $2l$ 的函数的傅里叶级数

### 4.1 一般周期的情况

> 设 $f(x)$ 以 $2l$ 为周期，则其傅里叶级数为：
>
> $$\boxed{f(x) \sim \frac{a_0}{2} + \sum_{n=1}^{\infty}\left(a_n\cos\frac{n\pi x}{l} + b_n\sin\frac{n\pi x}{l}\right)}$$
>
> 傅里叶系数：
>
> $$\boxed{a_0 = \frac{1}{l}\int_{-l}^{l} f(x)\,dx}$$
>
> $$\boxed{a_n = \frac{1}{l}\int_{-l}^{l} f(x)\cos\frac{n\pi x}{l}\,dx \quad (n = 1, 2, 3, \ldots)}$$
>
> $$\boxed{b_n = \frac{1}{l}\int_{-l}^{l} f(x)\sin\frac{n\pi x}{l}\,dx \quad (n = 1, 2, 3, \ldots)}$$

> 将 $2\pi$ 的公式中的 $x$ 替换为 $\dfrac{\pi x}{l}$，$\cos nx$ 替换为 $\cos\dfrac{n\pi x}{l}$，积分区间 $[-\pi, \pi]$ 替换为 $[-l, l]$，前面的系数 $\dfrac{1}{\pi}$ 替换为 $\dfrac{1}{l}$。

### 4.2 狄利克雷定理的推广

狄利克雷收敛定理对周期 $2l$ 的情形同样适用，只需将 $\cos nx$、$\sin nx$ 替换为 $\cos\dfrac{n\pi x}{l}$、$\sin\dfrac{n\pi x}{l}$。

---

## 五、奇偶函数的傅里叶展开

### 5.1 奇函数和偶函数的傅里叶系数

>
> **偶函数**（$f(-x) = f(x)$）：
>
> $$\boxed{b_n = 0 \quad (\forall n \ge 1)}$$
>
> $$a_n = \frac{2}{\pi}\int_0^{\pi} f(x)\cos nx\,dx \quad \text{（或 } \frac{2}{l}\int_0^l f(x)\cos\frac{n\pi x}{l}\,dx\text{）}$$
>
> 展开为**余弦级数**：$f(x) \sim \dfrac{a_0}{2} + \displaystyle\sum_{n=1}^{\infty}a_n\cos nx$
>
> **奇函数**（$f(-x) = -f(x)$）：
>
> $$\boxed{a_n = 0 \quad (\forall n \ge 0)}$$
>
> $$b_n = \frac{2}{\pi}\int_0^{\pi} f(x)\sin nx\,dx \quad \text{（或 } \frac{2}{l}\int_0^l f(x)\sin\frac{n\pi x}{l}\,dx\text{）}$$
>
> 展开为**正弦级数**：$f(x) \sim \displaystyle\sum_{n=1}^{\infty}b_n\sin nx$

> - 偶函数 → 只有余弦项（$b_n = 0$）
> - 奇函数 → 只有正弦项（$a_n = 0$）
> - 积分区间从 $[-\pi, \pi]$ 简化为 $[0, \pi]$，前面乘 $2$

### 5.2 非奇非偶函数的奇延拓与偶延拓

> 若 $f(x)$ 定义在 $[0, l]$ 上（不是整个周期），可以进行延拓：
>
> **奇延拓**：定义
>
> $$F(x) = \begin{cases} f(x), & 0 \le x \le l \\ -f(-x), & -l \le x < 0 \end{cases}$$
>
> 则 $F(x)$ 为奇函数，展开为**正弦级数**。
>
> **偶延拓**：定义
>
> $$F(x) = \begin{cases} f(x), & 0 \le x \le l \\ f(-x), & -l \le x < 0 \end{cases}$$
>
> 则 $F(x)$ 为偶函数，展开为**余弦级数**。

> 在 $[0, l]$ 上，延拓后得到的正弦级数和余弦级数都收敛到 $f(x)$（在 $f$ 的连续点处）。两者在 $[0, l]$ 上的收敛结果相同，但级数表达式不同。
>
> 在端点 $x = 0$ 和 $x = l$ 处要注意：
> - 奇延拓在端点处级数收敛到 $0$
> - 偶延拓在端点处级数收敛到 $f(0)$ 或 $f(l)$

---

## 六、经典例题

### 6.1 周期 $2\pi$ 的傅里叶展开

**【例1】** 设 $f(x) = x$（$-\pi < x < \pi$），以 $2\pi$ 为周期延拓，求其傅里叶级数。

**解**：$f(x) = x$ 是**奇函数**，故 $a_n = 0$。

$$b_n = \frac{2}{\pi}\int_0^{\pi} x\sin nx\,dx$$

分部积分：

$$= \frac{2}{\pi}\left[-\frac{x\cos nx}{n}\bigg|_0^{\pi} + \frac{1}{n}\int_0^{\pi}\cos nx\,dx\right] = \frac{2}{\pi}\left[-\frac{\pi\cos n\pi}{n} + \frac{\sin nx}{n^2}\bigg|_0^{\pi}\right]$$

$$= \frac{2}{\pi}\cdot\left(-\frac{\pi(-1)^n}{n}\right) = \frac{2(-1)^{n+1}}{n}$$

故：

$$f(x) \sim \sum_{n=1}^{\infty}\frac{2(-1)^{n+1}}{n}\sin nx = 2\left(\sin x - \frac{\sin 2x}{2} + \frac{\sin 3x}{3} - \cdots\right)$$

由狄利克雷定理：

- 在 $(-\pi, \pi)$ 内 $f(x) = x$（连续点），级数收敛到 $x$
- 在 $x = \pm\pi$ 处，收敛到 $\dfrac{f(-\pi^+) + f(\pi^-)}{2} = \dfrac{-\pi + \pi}{2} = 0$

> 令 $x = \dfrac{\pi}{2}$：
>
> $$\frac{\pi}{2} = 2\left(1 - \frac{1}{3} + \frac{1}{5} - \cdots\right) \quad \Rightarrow \quad 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \cdots = \frac{\pi}{4}$$

$\square$

**【例2】** 设 $f(x) = x^2$（$-\pi \le x \le \pi$），以 $2\pi$ 为周期延拓，求其傅里叶级数。

**解**：$f(x) = x^2$ 是**偶函数**，故 $b_n = 0$。

$$a_0 = \frac{2}{\pi}\int_0^{\pi}x^2\,dx = \frac{2}{\pi}\cdot\frac{\pi^3}{3} = \frac{2\pi^2}{3}$$

$$a_n = \frac{2}{\pi}\int_0^{\pi}x^2\cos nx\,dx$$

两次分部积分：

$$= \frac{2}{\pi}\left[\frac{x^2\sin nx}{n}\bigg|_0^{\pi} - \frac{2}{n}\int_0^{\pi}x\sin nx\,dx\right] = \frac{2}{\pi}\left[0 - \frac{2}{n}\left(-\frac{\pi\cos n\pi}{n}\right)\right] = \frac{4(-1)^n}{n^2}$$

故：

$$f(x) \sim \frac{\pi^2}{3} + \sum_{n=1}^{\infty}\frac{4(-1)^n}{n^2}\cos nx = \frac{\pi^2}{3} - 4\cos x + \cos 2x - \frac{4\cos 3x}{9} + \cdots$$

> 令 $x = 0$：$0 = \dfrac{\pi^2}{3} - 4\left(1 + \dfrac{1}{4} + \dfrac{1}{9} + \cdots\right)$
>
> $$\sum_{n=1}^{\infty}\frac{1}{n^2} = \frac{\pi^2}{6}$$
>
> 令 $x = \pi$：$\pi^2 = \dfrac{\pi^2}{3} + 4\left(1 + \dfrac{1}{4} + \dfrac{1}{9} + \cdots\right)$，同样得到 $\displaystyle\sum\frac{1}{n^2} = \frac{\pi^2}{6}$。

$\square$

### 6.2 周期 $2l$ 的傅里叶展开

**【例3】** 设 $f(x) = x$（$0 \le x \le 1$），将 $f(x)$ 展开为正弦级数。

**解**：对 $f(x)$ 做奇延拓，$l = 1$。

$$b_n = \frac{2}{1}\int_0^1 x\sin n\pi x\,dx$$

分部积分：

$$= 2\left[-\frac{x\cos n\pi x}{n\pi}\bigg|_0^1 + \frac{1}{n\pi}\int_0^1\cos n\pi x\,dx\right]$$

$$= 2\left[-\frac{\cos n\pi}{n\pi} + \frac{\sin n\pi x}{(n\pi)^2}\bigg|_0^1\right] = 2\cdot\frac{(-1)^{n+1}}{n\pi}$$

$$f(x) \sim \sum_{n=1}^{\infty}\frac{2(-1)^{n+1}}{n\pi}\sin n\pi x$$

在 $[0, 1]$ 上级数收敛到 $x$（在内部连续点处）。

在 $x = 0$ 和 $x = 1$ 处，奇延拓使级数收敛到 $0$。$\square$

**【例4】** 将 $f(x) = x$（$0 \le x \le 1$）展开为余弦级数。

**解**：对 $f(x)$ 做偶延拓，$l = 1$。

$$a_0 = \frac{2}{1}\int_0^1 x\,dx = 1$$

$$a_n = \frac{2}{1}\int_0^1 x\cos n\pi x\,dx = 2\left[\frac{x\sin n\pi x}{n\pi}\bigg|_0^1 - \frac{1}{n\pi}\int_0^1\sin n\pi x\,dx\right]$$

$$= 2\left[0 + \frac{\cos n\pi x}{(n\pi)^2}\bigg|_0^1\right] = \frac{2[(-1)^n - 1]}{(n\pi)^2}$$

当 $n$ 为偶数时 $a_n = 0$；当 $n$ 为奇数时 $a_n = -\dfrac{4}{(n\pi)^2}$。

$$f(x) \sim \frac{1}{2} - \sum_{k=0}^{\infty}\frac{4}{(2k+1)^2\pi^2}\cos(2k+1)\pi x$$

$$= \frac{1}{2} - \frac{4}{\pi^2}\left(\cos\pi x + \frac{\cos 3\pi x}{9} + \frac{\cos 5\pi x}{25} + \cdots\right) \quad \square$$

---

## 七、傅里叶级数的收敛性总结

>
> | 点的位置 | 收敛值 |
> |----------|--------|
> | 连续点 $x_0$ | $f(x_0)$ |
> | 第一类间断点 $x_0$ | $\dfrac{f(x_0^-) + f(x_0^+)}{2}$ |
> | 区间端点（周期延拓后） | $\dfrac{f(-\pi^+) + f(\pi^-)}{2}$（周期 $2\pi$ 时） |
> | 奇延拓端点 | $0$ |

---

## 八、考研真题精选

### 【真题1】（2017年数一·填空·4分）

**题目**：设 $f(x) = \begin{cases} 1, & 0 \le x < \pi \\ 0, & -\pi \le x < 0 \end{cases}$，以 $2\pi$ 为周期延拓，则在 $x = 0$ 处傅里叶级数收敛到____。

**解**：$x = 0$ 是第一类间断点。

$$\frac{f(0^-) + f(0^+)}{2} = \frac{0 + 1}{2} = \frac{1}{2}$$

**答案**：$\dfrac{1}{2}$ $\square$

### 【真题2】（解答题·10分）

**题目**：设 $f(x) = |x|$（$-\pi \le x \le \pi$），求其傅里叶级数，并利用结果求 $\displaystyle\sum_{n=0}^{\infty}\frac{1}{(2n+1)^2}$。

**解**：$f(x) = |x|$ 是**偶函数**，$b_n = 0$。

$$a_0 = \frac{2}{\pi}\int_0^{\pi}x\,dx = \pi$$

$$a_n = \frac{2}{\pi}\int_0^{\pi}x\cos nx\,dx = \frac{2}{\pi}\cdot\frac{(-1)^n - 1}{n^2}$$

当 $n$ 为偶数：$a_n = 0$；$n$ 为奇数：$a_n = -\dfrac{4}{n^2\pi}$。

$$|x| \sim \frac{\pi}{2} - \frac{4}{\pi}\sum_{k=0}^{\infty}\frac{\cos(2k+1)x}{(2k+1)^2}$$

令 $x = 0$：

$$0 = \frac{\pi}{2} - \frac{4}{\pi}\sum_{k=0}^{\infty}\frac{1}{(2k+1)^2}$$

$$\sum_{k=0}^{\infty}\frac{1}{(2k+1)^2} = \frac{\pi^2}{8} \quad \square$$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 三角函数系正交性 | 不同函数乘积积分为 $0$，是推导系数的基础 |
| 傅里叶系数（$2\pi$） | $a_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\cos nx\,dx$，$b_n = \frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\sin nx\,dx$ |
| 傅里叶系数（$2l$） | $\cos\frac{n\pi x}{l}$，$\sin\frac{n\pi x}{l}$，系数前为 $\frac{1}{l}$ |
| 狄利克雷定理 | 连续点收敛到 $f(x)$，间断点收敛到 $\frac{f(x^-)+f(x^+)}{2}$ |
| 奇函数展开 | $a_n = 0$，只含正弦项 |
| 偶函数展开 | $b_n = 0$，只含余弦项 |
| 奇/偶延拓 | 定义在半区间上的函数可做奇延拓或偶延拓 |

> 1. 傅里叶系数公式中 $\dfrac{1}{\pi}$（周期 $2\pi$）或 $\dfrac{1}{l}$（周期 $2l$）不要漏
> 2. $a_0$ 的公式是 $\dfrac{1}{\pi}\int_{-\pi}^{\pi}f(x)dx$，展开式中写 $\dfrac{a_0}{2}$
> 3. 狄利克雷定理在间断点处收敛到左右极限的**平均值**，不是 $f(x_0)$
> 4. 奇偶函数的傅里叶系数可以利用对称性将积分区间减半并乘 $2$
> 5. 端点处的收敛值取决于延拓方式：奇延拓端点为 $0$，偶延拓端点为 $f(0)$ 或 $f(l)$
> 6. 利用特殊点的值可以求出某些数项级数的和（如 $\sum\frac{1}{n^2} = \frac{\pi^2}{6}$）

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 50：幂级数]] — 幂级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 51：函数展开成幂级数]] — 展开
