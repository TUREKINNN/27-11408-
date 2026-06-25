---
title: "Lecture 11：无穷小量阶的比较"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 无穷小阶, 等价无穷小, 高阶无穷小]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 11：无穷小量阶的比较

> 无穷小量的阶的比较是极限理论的重要组成部分。两个无穷小趋向零的速度可能不同，通过比较它们的"阶"，可以精确描述无穷小之间的关系。本讲系统讲解同阶、等价、高阶、低阶、k 阶无穷小的概念及其应用。

---

## 一、基本概念

### 1.1 无穷小阶的比较定义

> 设 $\alpha(x)$ 和 $\beta(x)$ 都是 $x \to x_0$ 时的无穷小，且 $\alpha(x) \neq 0$。
>
> 1. **高阶无穷小**：若 $\lim_{x \to x_0} \frac{\beta(x)}{\alpha(x)} = 0$，则称 $\beta$ 是 $\alpha$ 的**高阶无穷小**，记为 $\beta = o(\alpha)$
> 2. **低阶无穷小**：若 $\lim_{x \to x_0} \frac{\beta(x)}{\alpha(x)} = \infty$，则称 $\beta$ 是 $\alpha$ 的**低阶无穷小**
> 3. **同阶无穷小**：若 $\lim_{x \to x_0} \frac{\beta(x)}{\alpha(x)} = c \neq 0$（$c$ 为有限非零常数），则称 $\beta$ 与 $\alpha$ 是**同阶无穷小**
> 4. **等价无穷小**：若 $\lim_{x \to x_0} \frac{\beta(x)}{\alpha(x)} = 1$，则称 $\beta$ 与 $\alpha$ 是**等价无穷小**，记为 $\beta \sim \alpha$
> 5. **k 阶无穷小**：若 $\lim_{x \to x_0} \frac{\beta(x)}{[\alpha(x)]^k} = c \neq 0$（$c$ 为有限非零常数），则称 $\beta$ 是关于 $\alpha$ 的 **k 阶无穷小**

### 1.2 各种关系的层次

>
> 等价无穷小 $\subset$ 同阶无穷小
>
> 高阶无穷小 = "更快趋向零"
> 低阶无穷小 = "更慢趋向零"
>
> $o(\alpha)$ 表示"比 $\alpha$ 更高阶的无穷小"，即趋向零更快的量

### 1.3 符号 $o(\cdot)$ 的精确含义

> $\beta = o(\alpha)$ 表示 $\frac{\beta}{\alpha} \to 0$，即 $\beta$ 是 $\alpha$ 的高阶无穷小。
>
> 在泰勒展开中：
> $$f(x) = a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n + o(x^n)$$
> 其中 $o(x^n)$ 表示比 $x^n$ 更高阶的项，即 $\frac{o(x^n)}{x^n} \to 0$。

---

## 二、以 $x \to 0$ 为基准的无穷小排列

### 2.1 标准无穷小的阶

>
> $$\cdots \ll x^5 \ll x^4 \ll x^3 \ll x^2 \ll x \ll \sqrt{x} \ll \cdots$$
>
> 具体到常见函数：
>
> | 函数 | 阶数 | 等价形式 |
> |------|------|---------|
> | $x - \sin x$ | 3 | $\frac{x^3}{6}$ |
> | $\tan x - x$ | 3 | $\frac{x^3}{3}$ |
> | $\tan x - \sin x$ | 3 | $\frac{x^3}{2}$ |
> | $1 - \cos x$ | 2 | $\frac{x^2}{2}$ |
> | $\ln(1+x) - x$ | 2 | $-\frac{x^2}{2}$ |
> | $e^x - 1 - x$ | 2 | $\frac{x^2}{2}$ |
> | $x - \arctan x$ | 3 | $\frac{x^3}{3}$ |
> | $\arcsin x - x$ | 3 | $\frac{x^3}{6}$ |
> | $(1+x)^a - 1 - ax$ | 2 | $\frac{a(a-1)}{2}x^2$ |

### 2.2 阶的确定方法

>
> **方法一**：利用泰勒展开
>
> 将函数展开到第一个非零项，该非零项的次数就是无穷小的阶。
>
> **方法二**：利用洛必达法则
>
> 反复计算 $\lim_{x \to 0} \frac{f(x)}{x^k}$，找到使极限为非零有限数的 $k$。

---

## 三、高阶无穷小的性质

### 3.1 基本性质

>
> 设 $x \to 0$ 时：
>
> 1. $o(x^m) + o(x^n) = o(x^{\min(m,n)})$（$m, n > 0$）
> 2. $o(x^m) \cdot o(x^n) = o(x^{m+n})$
> 3. $x^m \cdot o(x^n) = o(x^{m+n})$
> 4. $o(cx^m) = o(x^m)$（$c \neq 0$ 为常数）

### 3.2 注意事项

> 1. **$o(\cdot)$ 不是具体的函数**，它代表一类函数（所有比 $\alpha$ 高阶的无穷小）
> 2. **$o(\alpha) + o(\alpha) = o(\alpha)$**：两个高阶无穷小的和仍是高阶无穷小
> 3. **$o(\alpha) - o(\alpha)$ 不一定等于 $0$**：两个不同的高阶无穷小相减不一定为零
> 4. **不能把 $o(\alpha)$ 当作 $0$ 来处理**：$f(x) + o(x^2)$ 不能简化为 $f(x)$

---

## 四、等价无穷小的深入讨论

### 4.1 等价无穷小的本质

> $\alpha \sim $\beta$（$x \to x_0$）意味着：
>
> $$\lim_{x \to x_0} \frac{\alpha - \beta}{\alpha} = \lim_{x \to x_0} \left(1 - \frac{\beta}{\alpha}\right) = 0$$
>
> 即 $\alpha - \beta = o(\alpha)$，等价无穷小之间的差是更高阶的无穷小。

### 4.2 等价无穷小的替换精度

> 等价无穷小替换相当于用泰勒展开的**第一项**来近似。
>
> 例如：$\sin x \sim x$ 相当于 $\sin x = x + o(x)$，即 $\sin x - x = o(x)$。
>
> 如果需要更高精度，需要用更高阶的泰勒展开：
> $$\sin x = x - \frac{x^3}{6} + o(x^3)$$

### 4.3 加减中的等价替换

>
> 在计算 $\frac{f(x) - g(x)}{h(x)}$ 时，如果 $f \sim f'$，$g \sim g'$，则：
>
> **可以替换**的条件：$f' - g' \neq 0$（即替换后不完全抵消）
>
> **不能替换**的情况：$f' - g' = 0$（替换后完全抵消），此时需要用更高阶的展开
>
> **例**：$\frac{\sin x - x}{x^3}$ 中 $\sin x \sim x$，替换后分子为 $x - x = 0$，无法求出极限，必须用 $\sin x = x - \frac{x^3}{6} + o(x^3)$

---

## 五、无穷小阶的比较在极限计算中的应用

### 5.1 确定极限值

>
> 若 $\alpha$ 是 $k$ 阶无穷小，$\beta$ 是 $m$ 阶无穷小（关于 $x \to 0$），则：
>
> - 若 $k < m$：$\frac{\beta}{\alpha} \to 0$
> - 若 $k = m$：$\frac{\beta}{\alpha} \to$ 非零有限数
> - 若 $k > m$：$\frac{\beta}{\alpha} \to \infty$

### 5.2 例题

**例 1**：确定 $\lim_{x \to 0} \frac{\tan x - \sin x}{x^3}$

**解**：$\tan x - \sin x \sim \frac{x^3}{2}$（3 阶无穷小），$x^3$ 也是 3 阶无穷小，故极限为 $\frac{1/2}{1} = \frac{1}{2}$。

**例 2**：确定 $\lim_{x \to 0} \frac{1 - \cos x}{x^3 + x^2}$

**解**：$1 - \cos x \sim \frac{x^2}{2}$（2 阶），$x^3 + x^2 \sim x^2$（2 阶），故极限为 $\frac{1/2}{1} = \frac{1}{2}$。

**例 3**：比较 $x - \sin x$ 和 $1 - \cos x$ 在 $x \to 0$ 时的阶

**解**：$x - \sin x \sim \frac{x^3}{6}$（3 阶），$1 - \cos x \sim \frac{x^2}{2}$（2 阶）

$$\lim_{x \to 0} \frac{x - \sin x}{1 - \cos x} = \lim_{x \to 0} \frac{\frac{x^3}{6}}{\frac{x^2}{2}} = \lim_{x \to 0} \frac{x}{3} = 0$$

故 $x - \sin x$ 是 $1 - \cos x$ 的高阶无穷小。

---

## 六、无穷小阶的比较与泰勒展开的关系

### 6.1 核心联系

>
> 将 $f(x)$ 在 $x = 0$ 处展开：
> $$f(x) = a_1 x + a_2 x^2 + a_3 x^3 + \cdots + a_n x^n + o(x^n)$$
>
> - $f(x)$ 的阶 = 第一个非零系数对应的幂次
> - 若 $a_1 \neq 0$：$f(x)$ 是 1 阶无穷小，$f(x) \sim a_1 x$
> - 若 $a_1 = 0$，$a_2 \neq 0$：$f(x)$ 是 2 阶无穷小，$f(x) \sim a_2 x^2$
> - 一般地，若 $a_1 = a_2 = \cdots = a_{k-1} = 0$，$a_k \neq 0$：$f(x)$ 是 $k$ 阶无穷小

### 6.2 例题

**例 4**：求 $f(x) = \cos x - 1 + \frac{x^2}{2}$ 在 $x \to 0$ 时的阶

**解**：

$$\cos x = 1 - \frac{x^2}{2} + \frac{x^4}{24} + o(x^4)$$

$$f(x) = \cos x - 1 + \frac{x^2}{2} = \frac{x^4}{24} + o(x^4)$$

故 $f(x)$ 是 4 阶无穷小，$f(x) \sim \frac{x^4}{24}$。

**例 5**：求 $g(x) = e^x - \sin x - 1 - x + \frac{x^2}{2}$ 在 $x \to 0$ 时的阶

**解**：

$$e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$$
$$\sin x = x - \frac{x^3}{6} + o(x^3)$$

$$g(x) = (1 + x + \frac{x^2}{2} + \frac{x^3}{6}) - (x - \frac{x^3}{6}) - 1 - x + \frac{x^2}{2} + o(x^3)$$

$$= \cancel{1} + \cancel{x} + \frac{x^2}{2} + \frac{x^3}{6} - \cancel{x} + \frac{x^3}{6} - \cancel{1} - x + \frac{x^2}{2} + o(x^3)$$

$$= x^2 + \frac{x^3}{3} - x + o(x^3)$$

等等，让我重新算。$e^x - \sin x - 1 - x + \frac{x^2}{2}$：

$e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$

$e^x - 1 = x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$

$e^x - 1 - x = \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$

$e^x - 1 - x + \frac{x^2}{2} = x^2 + \frac{x^3}{6} + o(x^3)$

$e^x - \sin x - 1 - x + \frac{x^2}{2} = x^2 + \frac{x^3}{6} - x + \frac{x^3}{6} + o(x^3)$

嗯，这个函数在 $x \to 0$ 时趋向 $0$？让我验证：$g(0) = 1 - 0 - 1 - 0 + 0 = 0$。$g'(x) = e^x - \cos x - 1 + x$，$g'(0) = 1 - 1 - 1 + 0 = -1 \neq 0$。

所以 $g(x) \sim -x$（1 阶无穷小）。这个题设不太对，让我换一个。

**例 5（修正）**：求 $g(x) = e^x - \cos x - x$ 在 $x \to 0$ 时的阶

$g(0) = 1 - 1 - 0 = 0$

$g'(x) = e^x + \sin x - 1$，$g'(0) = 1 + 0 - 1 = 0$

$g''(x) = e^x + \cos x$，$g''(0) = 1 + 1 = 2 \neq 0$

故 $g(x) \sim \frac{2}{2}x^2 = x^2$，是 2 阶无穷小。

---

## 七、综合例题

### 例 6：含参数的无穷小阶

**题目**：当 $x \to 0$ 时，$(1 + ax^2)^{\frac{1}{3}} - 1$ 与 $\cos x - 1$ 是等价无穷小，求 $a$。

**解**：

$(1 + ax^2)^{\frac{1}{3}} - 1 \sim \frac{1}{3} \cdot ax^2 = \frac{a}{3}x^2$

$\cos x - 1 \sim -\frac{x^2}{2}$

由等价关系：$\frac{a}{3} = -\frac{1}{2}$，故 $a = -\frac{3}{2}$。

### 例 7：无穷小的阶的证明

**题目**：证明 $x \to 0$ 时，$\tan x - x \sim \frac{x^3}{3}$。

**证明**：

$$\lim_{x \to 0} \frac{\tan x - x}{\frac{x^3}{3}} = 3 \lim_{x \to 0} \frac{\tan x - x}{x^3}$$

由洛必达法则：

$$= 3 \lim_{x \to 0} \frac{\sec^2 x - 1}{3x^2} = \lim_{x \to 0} \frac{\tan^2 x}{x^2} = 1$$

或由泰勒展开：$\tan x = x + \frac{x^3}{3} + o(x^3)$，故 $\tan x - x = \frac{x^3}{3} + o(x^3) \sim \frac{x^3}{3}$。$\square$

### 例 8：确定复合函数的阶

**题目**：求 $f(x) = e^{\sin x} - e^x$ 在 $x \to 0$ 时的阶。

**解**：

$$f(x) = e^{\sin x} - e^x = e^x(e^{\sin x - x} - 1)$$

由于 $e^x \to 1$，$\sin x - x \sim -\frac{x^3}{6}$，$e^u - 1 \sim u$（$u \to 0$）：

$$f(x) \sim 1 \cdot (-\frac{x^3}{6}) = -\frac{x^3}{6}$$

故 $f(x)$ 是 3 阶无穷小。

---

## 八、常用结论汇总

### 8.1 等价无穷小速查表

>
> **基本等价**：
>
> | 原式 | 等价无穷小 | 阶数 |
> |------|-----------|------|
> | $\sin x$ | $x$ | 1 |
> | $\tan x$ | $x$ | 1 |
> | $\arcsin x$ | $x$ | 1 |
> | $\arctan x$ | $x$ | 1 |
> | $1 - \cos x$ | $\frac{x^2}{2}$ | 2 |
> | $\ln(1+x)$ | $x$ | 1 |
> | $e^x - 1$ | $x$ | 1 |
> | $(1+x)^a - 1$ | $ax$ | 1 |
>
> **加减中的等价**：
>
> | 原式 | 等价无穷小 | 阶数 |
> |------|-----------|------|
> | $x - \sin x$ | $\frac{x^3}{6}$ | 3 |
> | $\tan x - x$ | $\frac{x^3}{3}$ | 3 |
> | $\tan x - \sin x$ | $\frac{x^3}{2}$ | 3 |
> | $x - \arctan x$ | $\frac{x^3}{3}$ | 3 |
> | $\arcsin x - x$ | $\frac{x^3}{6}$ | 3 |
> | $x - \ln(1+x)$ | $\frac{x^2}{2}$ | 2 |
> | $e^x - 1 - x$ | $\frac{x^2}{2}$ | 2 |
> | $(1+x)^a - 1 - ax$ | $\frac{a(a-1)}{2}x^2$ | 2 |

---

## 九、易错点提醒

>
> 1. **高阶无穷小不能随便丢弃**：$f(x) = x + o(x)$ 不能写成 $f(x) = x$（但 $f(x) \sim x$ 是对的）
> 2. **$o(\alpha) + o(\alpha) = o(\alpha)$ 但 $o(\alpha) - o(\alpha)$ 不一定为 0**
> 3. **等价无穷小替换只在乘除中有效**：加减中的替换可能完全抵消
> 4. **确定无穷小的阶时**：要展开到第一个非零项
> 5. **k 阶无穷小的 k 只能是正数**：$k > 0$
> 6. **同阶无穷小的比值是非零有限常数**：不一定是 1（等价无穷小才要求是 1）
> 7. **无穷小的阶是相对某个基准而言的**：通常以 $x$（或 $x - x_0$）为基准

---

## 补充内容

> 以下内容补充自武忠祥教授《2021考研高等数学0基础课》课件 PDF (7)--1.11笔记小结

### 12.1 无穷小的比较（武忠祥教授讲解）

#### 1. 无穷小量的定义

> 若 $\lim_{x\to x_0}f(x) = 0$，则称 $f(x)$ 为当 $x\to x_0$ 时的无穷小量。

#### 2. 无穷小比较的五种情况

>
> 设 $\alpha(x)$ 和 $\beta(x)$ 都是 $x \to x_0$ 时的无穷小，且 $\alpha(x) \neq 0$。
>
> 1. **高阶无穷小**：若 $\lim\frac{\alpha(x)}{\beta(x)}=0$，则称 $\alpha(x)$ 是 $\beta(x)$ 的高阶无穷小，记为 $\alpha(x) = o(\beta(x))$
>
> 2. **低阶无穷小**：若 $\lim \frac{\alpha(x)}{\beta(x)} = \infty$，则称 $\alpha(x)$ 是 $\beta(x)$ 的低阶无穷小
>
> 3. **同阶无穷小**：若 $\lim \frac{\alpha(x)}{\beta(x)} = a \neq 0$，则称 $\alpha(x)$ 与 $\beta(x)$ 是同阶无穷小
>
> 4. **等价无穷小**：若 $\lim \frac{\alpha(x)}{\beta(x)} = 1$，则称 $\alpha(x)$ 与 $\beta(x)$ 是等价无穷小，记为 $\alpha(x)\sim \beta(x)$
>
> 5. **k 阶无穷小**：若 $\lim \frac{\alpha(x)}{[\beta(x)]^k} = a \neq 0, k > 0$，则称 $\alpha(x)$ 是 $\beta(x)$ 的 k 阶无穷小

### 12.2 等价无穷小的充要条件

> $\alpha(x)\sim \beta(x)$ 的充要条件是 $\alpha(x) = \beta(x) + o(\beta(x))$

**证明思路**：
- 若 $\alpha \sim \beta$，则 $\lim\frac{\alpha - \beta}{\beta} = \lim\frac{\alpha}{\beta} - 1 = 0$，即 $\alpha - \beta = o(\beta)$
- 反之，若 $\alpha = \beta + o(\beta)$，则 $\lim\frac{\alpha}{\beta} = \lim\frac{\beta + o(\beta)}{\beta} = 1$

### 12.3 等价无穷小代换定理

> 设 $\alpha(x) \sim \alpha_{1}(x)$，$\beta(x) \sim \beta_{1}(x)$，且 $\lim \frac{\alpha_{1}(x)}{\beta_{1}(x)}$ 存在，则
> $$\lim \frac{\alpha(x)}{\beta(x)} = \lim \frac{\alpha_{1}(x)}{\beta_{1}(x)}$$

**代换原则**：乘除关系可以换

若 $\alpha \sim \alpha_{1},\beta \sim \beta_{1}$，则
$$\lim \frac{\alpha}{\beta} = \lim \frac{\alpha_{1}}{\beta} = \lim \frac{\alpha}{\beta_{1}} = \lim \frac{\alpha_{1}}{\beta_{1}}$$

### 12.4 常用的等价无穷小

>
> $$x \sim \sin x \sim \tan x \sim \arcsin x \sim \arctan x$$
>
> $$\sqrt[n]{1 + x} - 1 \sim \frac{1}{n} x, \quad 1 - \cos x \sim \frac{1}{2} x^{2}$$

### 12.5 典型例题

**例1** 证明：当 $x \to 0$ 时，$\sqrt[n]{1 + x} - 1 \sim \frac{1}{n}x$

**例2** 求下列极限：

1) $\lim_{x\to0}\frac{\sin3x}{\arctan2x}$

2) $\lim_{x\to0}\frac{\arcsin2x}{x+x^{2}}$

3) $\lim_{x\to0}\frac{\sqrt[3]{1+2x^{2}}-1}{1-\cos x}$

4) $\lim_{x\to0}\frac{\sin x-\tan x}{x^{3}}$

### 12.6 内容小结

>
> **1. 无穷小的比较**：
> 设 $\alpha, \beta$ 对同一自变量的变化过程为无穷小，且 $\alpha \neq 0$
> $$\lim{\frac{\beta}{\alpha}} = \begin{cases} 0, & \beta \text{是} \alpha \text{的高阶无穷小} \\ \infty, & \beta \text{是} \alpha \text{的低阶无穷小} \\ C(\neq 0), & \beta \text{是} \alpha \text{的同阶无穷小} \\ 1, & \beta \text{是} \alpha \text{的等价无穷小} \end{cases}$$
>
> $$\lim{\frac{\beta}{\alpha^{k}}} = C \neq 0, \qquad \beta \text{是} \alpha \text{的} k \text{阶无穷小}$$
>
> **2. 等价无穷小代换**：
> - 代换原则：乘除关系可以换
> - 常用的等价无穷小：当 $x \to 0$ 时
> $$x \sim \sin x \sim \tan x \sim \arcsin x \sim \arctan x$$
> $$\sqrt[n]{1 + x} - 1 \sim \frac{1}{n} x, \quad 1 - \cos x \sim \frac{1}{2} x^{2}$$

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 8：无穷小与无穷大]] — 无穷小
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 10：求极限]] — 求极限
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 12：函数的连续性]] — 连续性
