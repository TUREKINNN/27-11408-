---
title: "Lecture 10：求极限"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 求极限, 洛必达法则, 泰勒展开]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 10：求极限

> 求极限是考研数学中**最核心的计算技能**。本讲系统总结求极限的**8 种常用方法**，并通过大量例题说明各种方法的适用场景和使用技巧。

---

## 一、方法一：基本极限（代入法）

### 1.1 原理

> 若 $f(x)$ 在 $x_0$ 处连续（或极限值可用四则运算直接算出），则：
> $$\lim_{x \to x_0} f(x) = f(x_0)$$
>
> 适用于：多项式、有理函数（分母不为零）、基本初等函数在其定义域内的极限。

### 1.2 例题

**例 1**：$\lim_{x \to 1} \frac{x^2 + 3x - 1}{x + 2} = \frac{1 + 3 - 1}{1 + 2} = 1$

**例 2**：$\lim_{x \to 0} e^x = e^0 = 1$

---

## 二、方法二：等价无穷小替换

### 2.1 核心公式

>
> $$\sin x \sim x, \quad \tan x \sim x, \quad \arcsin x \sim x, \quad \arctan x \sim x$$
> $$1 - \cos x \sim \frac{x^2}{2}, \quad \ln(1+x) \sim x, \quad e^x - 1 \sim x, \quad (1+x)^a - 1 \sim ax$$

### 2.2 使用规则

> 1. **整体替换**：替换必须针对整个因子（乘除因子或独立的无穷小）
> 2. **不能替换加减项**：$\sin x - x$ 不能将 $\sin x$ 替换为 $x$
> 3. **可替换条件**：替换后分子分母不同时为 0

### 2.3 例题

**例 3**：$\lim_{x \to 0} \frac{\sin 3x}{\ln(1+2x)} = \lim_{x \to 0} \frac{3x}{2x} = \frac{3}{2}$

**例 4**：$\lim_{x \to 0} \frac{e^{x^2} - 1}{1 - \cos x} = \lim_{x \to 0} \frac{x^2}{\frac{x^2}{2}} = 2$

**例 5**：$\lim_{x \to 0} \frac{\sqrt{1 + x\sin x} - 1}{\arctan^2 x} = \lim_{x \to 0} \frac{\frac{x\sin x}{2}}{x^2} = \lim_{x \to 0} \frac{\frac{x \cdot x}{2}}{x^2} = \frac{1}{2}$

---

## 三、方法三：有理运算法

### 3.1 适用场景

> 当极限是 $\frac{0}{0}$、$\frac{\infty}{\infty}$、$\infty - \infty$ 等不定式时，通过代数变形（因式分解、有理化、通分等）化为可直接求极限的形式。

### 3.2 常用技巧

> 1. **因式分解**：提取公因式、利用公式
> 2. **分子/分母有理化**：乘以共轭
> 3. **通分**：将 $\infty - \infty$ 型化为分式
> 4. **提公因式**：将最高次项提出
> 5. **变量替换**：令 $t = \frac{1}{x}$ 等

### 3.3 例题

**例 6**（因式分解）：$\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = \lim_{x \to 1} \frac{(x-1)(x+1)}{x-1} = \lim_{x \to 1} (x+1) = 2$

**例 7**（有理化）：$\lim_{x \to 0} \frac{\sqrt{1+x} - 1}{x} = \lim_{x \to 0} \frac{(\sqrt{1+x}-1)(\sqrt{1+x}+1)}{x(\sqrt{1+x}+1)} = \lim_{x \to 0} \frac{x}{x(\sqrt{1+x}+1)} = \frac{1}{2}$

**例 8**（通分）：$\lim_{x \to 0} \left(\frac{1}{x} - \frac{1}{\sin x}\right) = \lim_{x \to 0} \frac{\sin x - x}{x \sin x} = \lim_{x \to 0} \frac{-\frac{x^3}{6}}{x^2} = 0$

**例 9**（分子分母同除最高次）：$\lim_{x \to \infty} \frac{3x^2 + 2x - 1}{5x^2 - x + 3} = \lim_{x \to \infty} \frac{3 + \frac{2}{x} - \frac{1}{x^2}}{5 - \frac{1}{x} + \frac{3}{x^2}} = \frac{3}{5}$

---

## 四、方法四：洛必达法则（L'Hôpital）

### 4.1 定理表述

> 设：
> 1. $\lim_{x \to x_0} f(x) = \lim_{x \to x_0} g(x) = 0$（$\frac{0}{0}$ 型）
> 2. $f(x)$、$g(x)$ 在 $x_0$ 的某去心邻域内可导，且 $g'(x) \neq 0$
> 3. $\lim_{x \to x_0} \frac{f'(x)}{g'(x)}$ 存在（或为 $\infty$）
>
> 则 $\lim_{x \to x_0} \frac{f(x)}{g(x)} = \lim_{x \to x_0} \frac{f'(x)}{g'(x)}$
>
> 对 $\frac{\infty}{\infty}$ 型也适用。

### 4.2 使用条件

> 1. **必须是 $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ 型**：其他不定式需先化为这两种形式
> 2. **$\lim\frac{f'}{g'}$ 必须存在**：如果 $\lim\frac{f'}{g'}$ 不存在（振荡），不能用洛必达
> 3. **可以反复使用**：如果 $\frac{f'}{g'}$ 仍是不定式，可以继续求导
> 4. **注意效率**：有时洛必达法则计算很繁琐，泰勒展开可能更简洁

### 4.3 例题

**例 10**：$\lim_{x \to 0} \frac{e^x - 1 - x}{x^2} \stackrel{\frac{0}{0}}{=} \lim_{x \to 0} \frac{e^x - 1}{2x} \stackrel{\frac{0}{0}}{=} \lim_{x \to 0} \frac{e^x}{2} = \frac{1}{2}$

**例 11**：$\lim_{x \to 0} \frac{x - \sin x}{x^3} \stackrel{\frac{0}{0}}{=} \lim_{x \to 0} \frac{1 - \cos x}{3x^2} = \lim_{x \to 0} \frac{\frac{x^2}{2}}{3x^2} = \frac{1}{6}$

**例 12**（$\infty \cdot 0$ 型先化为 $\frac{0}{0}$）：

$$\lim_{x \to 0^+} x \ln x = \lim_{x \to 0^+} \frac{\ln x}{\frac{1}{x}} \stackrel{\frac{\infty}{\infty}}{=} \lim_{x \to 0^+} \frac{\frac{1}{x}}{-\frac{1}{x^2}} = \lim_{x \to 0^+} (-x) = 0$$

---

## 五、方法五：泰勒展开（Taylor 公式）

### 5.1 常用泰勒展开（$x \to 0$）

>
> $$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots$$
> $$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots$$
> $$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \cdots$$
> $$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \cdots$$
> $$\frac{1}{1-x} = 1 + x + x^2 + x^3 + \cdots$$
> $$\frac{1}{1+x} = 1 - x + x^2 - x^3 + \cdots$$
> $$(1+x)^a = 1 + ax + \frac{a(a-1)}{2}x^2 + \cdots$$
> $$\tan x = x + \frac{x^3}{3} + \frac{2x^5}{15} + \cdots$$
> $$\arctan x = x - \frac{x^3}{3} + \frac{x^5}{5} - \cdots$$

### 5.2 使用技巧

> 1. **展开到足够的阶数**：分子分母展开后，最低次非零项必须保留
> 2. **"上下同阶"原则**：如果分母是 $x^n$，则分子也应展开到 $x^n$
> 3. **"加减抵消"原则**：如果 $\frac{0}{0}$ 型，分子的低次项会互相抵消，需要展开到不抵消的那一阶

### 5.3 例题

**例 13**：$\lim_{x \to 0} \frac{e^x - 1 - x}{x^2}$

$$e^x = 1 + x + \frac{x^2}{2} + o(x^2)$$
$$e^x - 1 - x = \frac{x^2}{2} + o(x^2)$$
$$\lim_{x \to 0} \frac{\frac{x^2}{2} + o(x^2)}{x^2} = \frac{1}{2}$$

**例 14**：$\lim_{x \to 0} \frac{\sin x - x + \frac{x^3}{6}}{x^5}$

$$\sin x = x - \frac{x^3}{6} + \frac{x^5}{120} + o(x^5)$$
$$\sin x - x + \frac{x^3}{6} = \frac{x^5}{120} + o(x^5)$$
$$\lim_{x \to 0} \frac{\frac{x^5}{120}}{x^5} = \frac{1}{120}$$

**例 15**：$\lim_{x \to 0} \frac{\cos x - e^{-\frac{x^2}{2}}}{x^4}$

$$\cos x = 1 - \frac{x^2}{2} + \frac{x^4}{24} + o(x^4)$$
$$e^{-\frac{x^2}{2}} = 1 + (-\frac{x^2}{2}) + \frac{(-\frac{x^2}{2})^2}{2} + o(x^4) = 1 - \frac{x^2}{2} + \frac{x^4}{8} + o(x^4)$$
$$\cos x - e^{-\frac{x^2}{2}} = \frac{x^4}{24} - \frac{x^4}{8} + o(x^4) = -\frac{x^4}{12} + o(x^4)$$
$$\lim_{x \to 0} \frac{-\frac{x^4}{12}}{x^4} = -\frac{1}{12}$$

---

## 六、方法六：定积分定义

### 6.1 核心公式

> $$\lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^{n} f\left(\frac{k}{n}\right) = \int_0^1 f(x) \, dx$$
>
> 更一般地：
> $$\lim_{n \to \infty} \frac{b-a}{n} \sum_{k=1}^{n} f\left(a + k \cdot \frac{b-a}{n}\right) = \int_a^b f(x) \, dx$$

### 6.2 识别方法

> 当极限是 $n$ 项之和的形式，且可以写成 $\frac{1}{n} \sum f(\frac{k}{n})$ 的形式时，用定积分定义。

### 6.3 例题

**例 16**：$\lim_{n \to \infty} \left(\frac{1}{n+1} + \frac{1}{n+2} + \cdots + \frac{1}{2n}\right)$

$$= \lim_{n \to \infty} \sum_{k=1}^{n} \frac{1}{n+k} = \lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^{n} \frac{1}{1 + \frac{k}{n}} = \int_0^1 \frac{1}{1+x} \, dx = \ln 2$$

**例 17**：$\lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^{n} \sin\frac{k\pi}{n} = \int_0^1 \sin(\pi x) \, dx = \left[-\frac{\cos\pi x}{\pi}\right]_0^1 = \frac{2}{\pi}$

**例 18**：$\lim_{n \to \infty} \left(\frac{n}{n^2+1^2} + \frac{n}{n^2+2^2} + \cdots + \frac{n}{n^2+n^2}\right)$

$$= \lim_{n \to \infty} \sum_{k=1}^{n} \frac{n}{n^2+k^2} = \lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^{n} \frac{1}{1+(\frac{k}{n})^2} = \int_0^1 \frac{1}{1+x^2} \, dx = \frac{\pi}{4}$$

---

## 七、方法七：夹逼准则

### 7.1 适用场景

> 适用于：含有振荡项（如 $\sin$、$\cos$）的 $n$ 项和或乘积，且无法用定积分定义的情况。

### 7.2 例题

**例 19**：$\lim_{n \to \infty} \left(\frac{n}{n^2+1} + \frac{n}{n^2+2} + \cdots + \frac{n}{n^2+n}\right)$

$$\frac{n \cdot n}{n^2+n} \leq S_n \leq \frac{n \cdot n}{n^2+1}$$
$$\frac{n^2}{n^2+n} \leq S_n \leq \frac{n^2}{n^2+1}$$

两个边界都趋向 1，故 $S_n \to 1$。

**例 20**：$\lim_{n \to \infty} \frac{1 \cdot 3 \cdot 5 \cdots (2n-1)}{2 \cdot 4 \cdot 6 \cdots (2n)}$

记 $a_n = \frac{1 \cdot 3 \cdot 5 \cdots (2n-1)}{2 \cdot 4 \cdot 6 \cdots (2n)}$，$b_n = \frac{2 \cdot 4 \cdot 6 \cdots (2n)}{3 \cdot 5 \cdot 7 \cdots (2n+1)}$

则 $a_n < b_n$（对应项比较），$a_n b_n = \frac{1}{2n+1}$

故 $a_n^2 < a_n b_n = \frac{1}{2n+1} \to 0$，即 $a_n \to 0$。

---

## 八、方法八：单调有界准则

### 8.1 适用场景

> 适用于：由递推关系 $a_{n+1} = f(a_n)$ 定义的数列求极限。
>
> 步骤：
> 1. 证明单调性（数学归纳法或差值法）
> 2. 证明有界性（数学归纳法）
> 3. 利用递推关系令 $A = f(A)$ 求极限值

### 8.2 例题

**例 21**：设 $a_1 = 1$，$a_{n+1} = \frac{1}{2}\left(a_n + \frac{2}{a_n}\right)$，求 $\lim a_n$。

**解**：

由均值不等式：$a_{n+1} = \frac{1}{2}\left(a_n + \frac{2}{a_n}\right) \geq \sqrt{a_n \cdot \frac{2}{a_n}} = \sqrt{2}$（$n \geq 2$）

$a_{n+1} - a_n = \frac{1}{2}\left(\frac{2}{a_n} - a_n\right) = \frac{2 - a_n^2}{2a_n}$

当 $a_n > \sqrt{2}$ 时，$a_{n+1} - a_n < 0$，单调递减。

$a_2 = \frac{1}{2}(1 + 2) = \frac{3}{2} > \sqrt{2}$，之后单调递减且有下界 $\sqrt{2}$。

令 $A = \frac{1}{2}(A + \frac{2}{A})$，$A^2 = 2$，$A = \sqrt{2}$。

---

## 九、八种方法的选择策略

>
> | 不定式类型 | 首选方法 | 备选方法 |
> |-----------|---------|---------|
> | $\frac{0}{0}$（简单） | 等价无穷小 | 有理运算 |
> | $\frac{0}{0}$（复杂） | 泰勒展开 | 洛必达 |
> | $\frac{\infty}{\infty}$ | 同除最高次 | 洛必达 |
> | $0 \times \infty$ | 化为分式 | 等价替换 |
> | $\infty - \infty$ | 通分/有理化 | 化为分式 |
> | $1^\infty$ | 凑 $(1+u)^{1/u}$ | 取对数 |
> | $\infty^0$ 或 $0^0$ | 取对数 | 凑指数形式 |
> | $n$ 项和 | 夹逼/定积分定义 | — |
> | 递推数列 | 单调有界准则 | — |

---

## 十、综合例题

### 例 22：$1^\infty$ 型极限

**题目**：求 $\lim_{x \to 0} \left(\frac{\sin x}{x}\right)^{\frac{1}{x^2}}$

**解**：

令 $L = \lim_{x \to 0} \left(\frac{\sin x}{x}\right)^{\frac{1}{x^2}}$

$$\ln L = \lim_{x \to 0} \frac{1}{x^2} \ln\frac{\sin x}{x} = \lim_{x \to 0} \frac{\ln\frac{\sin x}{x}}{x^2}$$

由泰勒展开：$\frac{\sin x}{x} = 1 - \frac{x^2}{6} + o(x^2)$

$$\ln\frac{\sin x}{x} = \ln\left(1 - \frac{x^2}{6} + o(x^2)\right) \sim -\frac{x^2}{6} + o(x^2)$$

$$\ln L = \lim_{x \to 0} \frac{-\frac{x^2}{6}}{x^2} = -\frac{1}{6}$$

故 $L = e^{-\frac{1}{6}}$。

### 例 23：综合运用

**题目**：求 $\lim_{x \to 0} \frac{e^x \sin x - x(1+x)}{x^3}$

**解**（泰勒展开法）：

$$e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$$
$$\sin x = x - \frac{x^3}{6} + o(x^3)$$
$$e^x \sin x = \left(1 + x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)\right)\left(x - \frac{x^3}{6} + o(x^3)\right)$$

展开（保留到 $x^3$ 项）：
$$= x + x^2 + \frac{x^3}{2} + \frac{x^3}{6} - \frac{x^3}{6} + o(x^3) = x + x^2 + \frac{x^3}{2} + o(x^3)$$

等一下，让我仔细展开：

$e^x \sin x$：取 $e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + o(x^3)$，$\sin x = x - \frac{x^3}{6} + o(x^3)$

$$e^x \sin x = (1)(x) + (1)(-\frac{x^3}{6}) + (x)(x) + (\frac{x^2}{2})(x) + o(x^3)$$
$$= x - \frac{x^3}{6} + x^2 + \frac{x^3}{2} + o(x^3)$$
$$= x + x^2 + \frac{x^3}{3} + o(x^3)$$

$$e^x \sin x - x(1+x) = x + x^2 + \frac{x^3}{3} - x - x^2 + o(x^3) = \frac{x^3}{3} + o(x^3)$$

$$\lim_{x \to 0} \frac{\frac{x^3}{3}}{x^3} = \frac{1}{3}$$

---

## 十一、易错点提醒

>
> 1. **等价无穷小替换只能在乘除中**：加减中的替换可能出错
> 2. **洛必达法则的前提**：必须是 $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ 型，且 $\lim\frac{f'}{g'}$ 要存在
> 3. **泰勒展开的阶数**：要展开到足够阶，否则可能遗漏关键项
> 4. **$1^\infty$ 型的标准形式**：$\lim f(x)^{g(x)} = e^{\lim g(x)[f(x)-1]}$（当 $f \to 1$，$g \to \infty$）
> 5. **定积分定义的识别**：必须能写成 $\frac{1}{n}\sum f(\frac{k}{n})$ 的形式
> 6. **有理化时不要忘记共轭**：$\sqrt{a} - \sqrt{b}$ 乘以 $\sqrt{a} + \sqrt{b}$
> 7. **$\infty^0$ 和 $0^0$ 型**：取对数化为 $0 \times \infty$ 型，再化为分式

---

## 补充内容

> 以下内容补充自武忠祥教授《2021考研高等数学0基础课》课件 PDF (6)--1.9-1.10笔记小结 及 PDF (9)--1.13笔记小结

### 11.1 两个重要极限的求极限应用

>
> **第一个重要极限**：
> $$\lim_{x\to 0}\frac{\sin x}{x} = 1$$
> 更一般地：$\lim_{x\to \Delta}\frac{\sin\Delta}{\Delta} = 1$（其中 $\Delta \neq 0$ 且 $\Delta \to 0$）
>
> **第二个重要极限**：
> $$\lim_{x\to \infty}(1 + \frac{1}{x})^x = e$$
> 等价形式：$\lim_{x\to 0}(1 + x)^{\frac{1}{x}} = e$

#### 相关极限

1. $\lim_{x\to0}\frac{\tan x}{x} = 1$
2. $\lim_{x\to0}\frac{1-\cos x}{x^{2}} = \frac{1}{2}$
3. $\lim_{x\to0}\frac{\arctan x}{x} = 1$
4. $\lim_{x\to0}\frac{\arcsin x}{x} = 1$

### 11.2 $1^{\infty}$ 型极限的求法

> 若 $\lim \alpha(x) = 0$，$\lim \beta(x) = \infty$，且 $\lim \alpha(x)\beta(x) = A$
> 则 $\lim (1 + \alpha(x))^{\beta(x)} = e^{A}$

**求解三步法**：
1. 写标准形式：原式 $= \lim [1 + \alpha(x)]^{\beta(x)}$
2. 求极限：$\lim \alpha(x)\beta(x) = A$
3. 写结果：原式 $= e^{A}$

#### 典型例题

**例** 求极限 $\lim_{x\to0}\left(\sqrt{1+x^{2}}\right)^{\frac{1}{\ln(1+x^{2})}}$

### 11.3 常用等价无穷小汇总

>
> **基本等价无穷小**：
> $$x \sim \sin x \sim \tan x \sim \arcsin x \sim \arctan x \sim e^x - 1 \sim \ln(1+x)$$
>
> **幂函数相关**：
> $$\sqrt[n]{1+x} - 1 \sim \frac{1}{n}x$$
> $$(1+x)^{\alpha} - 1 \sim \alpha x$$
>
> **三角函数相关**：
> $$1 - \cos x \sim \frac{1}{2}x^2$$
>
> **指数对数相关**：
> $$a^x - 1 \sim x\ln a$$

### 11.4 极限存在法则

>
> **准则 1（夹逼准则）**：
> 如果数列 $\{x_{n}\},\{y_{n}\}$ 及 $\{z_{n}\}$ 满足：
> 1. 存在 $N$，当 $n > N$ 时，$x_{n} \leq y_{n} \leq z_{n}$
> 2. $\lim_{n\to \infty}x_n = \lim_{n\to \infty}z_n = a$
>
> 则 $\lim_{n\to \infty}y_n = a$
>
> **准则 2（单调有界准则）**：
> 单调有界数列必有极限。
> 即：单调增有上界的数列必有极限；单调减有下界的数列必有极限。

### 11.5 补充例题

**例1** 求极限 $\lim_{n\to\infty}\left[\frac{1}{\sqrt{n^{2}+1}}+\frac{1}{\sqrt{n^{2}+2}}+\cdots+\frac{1}{\sqrt{n^{2}+n}}\right]$

**例2** 求极限 $\lim_{x\to+\infty}(2+\sin x)^{\frac{1}{x}}$

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 7：数列极限存在准则]] — 夹逼准则
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 8：无穷小与无穷大]] — 无穷小
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 11：无穷小量阶的比较]] — 阶的比较
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/公式合集]] — 泰勒公式
