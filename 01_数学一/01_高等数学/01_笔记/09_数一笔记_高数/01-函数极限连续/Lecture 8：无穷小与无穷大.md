---
title: "Lecture 8：无穷小与无穷大"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 无穷小, 无穷大, 等价无穷小]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 8：无穷小与无穷大

> 无穷小和无穷大是极限理论中的两个核心概念。无穷小是极限为零的变量，无穷大是绝对值趋向无穷的变量。本讲详细讲解两者的定义、关系、运算性质，以及考研中极为重要的**等价无穷小替换**。

---

## 一、无穷小的定义

### 1.1 定义

> 若 $\lim_{x \to x_0} f(x) = 0$，则称 $f(x)$ 为当 $x \to x_0$ 时的**无穷小量**（简称无穷小）。
>
> 类似地可以定义 $x \to \infty$、$x \to x_0^+$、$x \to x_0^-$ 等过程中的无穷小。
>
> 对数列：若 $\lim_{n \to \infty} a_n = 0$，则称 $\{a_n\}$ 为无穷小量。

### 1.2 关键理解

> 1. 无穷小是一个**变量**（函数或数列），不是一个固定的很小的数
> 2. 无穷小是相对于某个极限过程而言的：$f(x) = x - 1$ 在 $x \to 1$ 时是无穷小，但在 $x \to 0$ 时不是
> 3. **0 是唯一既是常数又是无穷小的量**（在任何极限过程中，恒为 0 的函数都是无穷小）
> 4. 无穷小不能与"很小的数"混淆：$10^{-100}$ 虽然很小，但它是常数，不是无穷小

### 1.3 无穷小与极限的关系

> $\lim_{x \to x_0} f(x) = A$ 的**充要条件**是 $f(x) = A + \alpha(x)$，其中 $\alpha(x)$ 是当 $x \to x_0$ 时的无穷小。
>
> 即：**极限等于常数 $\Leftrightarrow$ 函数等于常数加无穷小**。

**证明**：

（$\Rightarrow$）设 $\lim_{x \to x_0} f(x) = A$，令 $\alpha(x) = f(x) - A$，则 $\lim_{x \to x_0} \alpha(x) = A - A = 0$，故 $\alpha(x)$ 是无穷小。

（$\Leftarrow$）设 $f(x) = A + \alpha(x)$，$\lim_{x \to x_0} \alpha(x) = 0$，则 $\lim_{x \to x_0} f(x) = A + 0 = A$。$\square$

---

## 二、无穷小的运算性质

### 2.1 基本性质

> 1. **有限个无穷小的和仍是无穷小**：若 $\alpha, \beta$ 都是无穷小，则 $\alpha + \beta$ 也是无穷小
> 2. **有界函数与无穷小的乘积仍是无穷小**：若 $|f(x)| \leq M$，$\alpha(x)$ 是无穷小，则 $f(x) \cdot \alpha(x)$ 是无穷小
> 3. **有限个无穷小的乘积仍是无穷小**：若 $\alpha, \beta$ 都是无穷小，则 $\alpha \cdot \beta$ 也是无穷小
> 4. **常数与无穷小的乘积仍是无穷小**：$c \cdot \alpha$ 是无穷小

### 2.2 重要推论

> 1. $\sin\frac{1}{x}$ 有界（$|\sin\frac{1}{x}| \leq 1$），$x$ 是 $x \to 0$ 时的无穷小，故 $x \sin\frac{1}{x}$ 是无穷小
> 2. $\lim_{x \to 0} x \sin\frac{1}{x} = 0$（这不能用洛必达法则！）
> 3. **无穷小之和不一定是无穷小**（如果涉及无穷多个无穷小的和，需要具体分析）

### 2.3 无穷小的商（不定式）

> 两个无穷小的商不一定是无穷小！这是极限计算中的核心问题：
> - $\frac{0}{0}$ 型不定式：$\lim_{x \to 0} \frac{\sin x}{x} = 1$
> - $\frac{0}{0}$ 型不定式：$\lim_{x \to 0} \frac{x^2}{x} = 0$
> - $\frac{0}{0}$ 型不定式：$\lim_{x \to 0} \frac{x}{x^2} = \infty$
>
> 商的结果取决于两个无穷小"趋向 0 的速度"，这就是**无穷小阶的比较**。

---

## 三、无穷大的定义

### 3.1 定义

> 设 $f(x)$ 在 $x_0$ 的某个去心邻域内有定义。若对**任意给定**的正数 $M$（不论多大），**存在** $\delta > 0$，使得当 $0 < |x - x_0| < \delta$ 时，
> $$|f(x)| > M$$
> 则称 $f(x)$ 为当 $x \to x_0$ 时的**无穷大量**，记为 $\lim_{x \to x_0} f(x) = \infty$。

### 3.2 各种类型的无穷大

> - $\lim_{x \to x_0} f(x) = +\infty$：$\forall M > 0$，$\exists \delta > 0$，$0 < |x - x_0| < \delta$ 时 $f(x) > M$
> - $\lim_{x \to x_0} f(x) = -\infty$：$\forall M > 0$，$\exists \delta > 0$，$0 < |x - x_0| < \delta$ 时 $f(x) < -M$
> - $\lim_{x \to \infty} f(x) = \infty$：$\forall M > 0$，$\exists X > 0$，$|x| > X$ 时 $|f(x)| > M$

### 3.3 关键理解

> 1. 无穷大是一个**变量**，不是一个固定的很大的数
> 2. 无穷大是**发散**的（极限不存在），但习惯上用 $\lim f(x) = \infty$ 来表示这种特殊的发散方式
> 3. $\infty$ 不是一个数，不能进行通常的代数运算
> 4. 无穷大是相对于某个极限过程而言的

---

## 四、无穷小与无穷大的关系

### 4.1 基本关系

> 1. 若 $f(x)$ 是无穷小（$f(x) \neq 0$），则 $\frac{1}{f(x)}$ 是无穷大
> 2. 若 $f(x)$ 是无穷大，则 $\frac{1}{f(x)}$ 是无穷小
>
> 即：**无穷大的倒数是无穷小，非零无穷小的倒数是无穷大**。

### 4.2 无穷大的运算

> 1. **无穷大 $\times$ 非零常数 = 无穷大**
> 2. **无穷大 $\times$ 无穷大 = 无穷大**
> 3. **无穷大 $+$ 无穷大 = 无穷大**（同号）
> 4. **无穷大 $-$ 无穷大 = 不定**（$\infty - \infty$ 型）
> 5. **无穷大 $\times$ 无穷小 = 不定**（$0 \times \infty$ 型）

---

## 五、等价无穷小

### 5.1 定义

> 设 $\alpha(x)$ 和 $\beta(x)$ 都是 $x \to x_0$ 时的无穷小，且 $\alpha(x) \neq 0$。若
> $$\lim_{x \to x_0} \frac{\beta(x)}{\alpha(x)} = 1$$
> 则称 $\beta(x)$ 与 $\alpha(x)$ 是**等价无穷小**，记为 $\beta(x) \sim \alpha(x)$（$x \to x_0$）。

### 5.2 常用等价无穷小（$x \to 0$）

>
> $$\sin x \sim x$$
> $$\tan x \sim x$$
> $$\arcsin x \sim x$$
> $$\arctan x \sim x$$
> $$1 - \cos x \sim \frac{x^2}{2}$$
> $$\ln(1 + x) \sim x$$
> $$e^x - 1 \sim x$$
> $$(1 + x)^a - 1 \sim ax$$

### 5.3 等价无穷小的推广形式

> 若 $\alpha(x) \to 0$，则可以将上面的 $x$ 替换为 $\alpha(x)$：
>
> - $\sin\alpha \sim \alpha$
> - $\tan\alpha \sim \alpha$
> - $1 - \cos\alpha \sim \frac{\alpha^2}{2}$
> - $\ln(1 + \alpha) \sim \alpha$
> - $e^\alpha - 1 \sim \alpha$
> - $(1 + \alpha)^a - 1 \sim a\alpha$
>
> 例如：$\sin(x^2) \sim x^2$（$x \to 0$），$\ln(1 + \sin x) \sim \sin x \sim x$（$x \to 0$）

### 5.4 等价无穷小替换定理

> 设 $\alpha \sim \alpha'$，$\beta \sim \beta'$（$x \to x_0$），且 $\lim_{x \to x_0} \frac{\beta'}{\alpha'}$ 存在，则
> $$\lim_{x \to x_0} \frac{\beta}{\alpha} = \lim_{x \to x_0} \frac{\beta'}{\alpha'}$$

**证明**：

$$\lim_{x \to x_0} \frac{\beta}{\alpha} = \lim_{x \to x_0} \frac{\beta}{\beta'} \cdot \frac{\beta'}{\alpha'} \cdot \frac{\alpha'}{\alpha} = 1 \cdot \lim_{x \to x_0} \frac{\beta'}{\alpha'} \cdot 1 = \lim_{x \to x_0} \frac{\beta'}{\alpha'}$$

$\square$

### 5.5 等价无穷小替换的使用规则

> 1. **只能替换乘除因子中的无穷小**，不能替换加减中的无穷小
> 2. 例如：$\lim_{x \to 0} \frac{\sin x - x}{x^3}$ **不能**将 $\sin x$ 替换为 $x$（会得到 $\frac{0}{x^3} = 0$，错误！）
> 3. 正确做法：$\sin x - x \sim -\frac{x^3}{6}$（需要泰勒展开）

### 5.6 更多等价无穷小的推导

> 利用 $\lim_{x \to 0} \frac{f(x)}{g(x)} = 1$ 来验证等价关系。

**例**：推导 $x - \sin x \sim \frac{x^3}{6}$

$$\lim_{x \to 0} \frac{x - \sin x}{x^3} \stackrel{\text{洛必达}}{=} \lim_{x \to 0} \frac{1 - \cos x}{3x^2} = \lim_{x \to 0} \frac{\frac{x^2}{2}}{3x^2} = \frac{1}{6}$$

故 $x - \sin x \sim \frac{x^3}{6}$。

**常用加减中的等价无穷小**：

$$x - \sin x \sim \frac{x^3}{6}$$
$$\tan x - x \sim \frac{x^3}{3}$$
$$\tan x - \sin x \sim \frac{x^3}{2}$$
$$\arcsin x - x \sim \frac{x^3}{6}$$
$$x - \arctan x \sim \frac{x^3}{3}$$
$$x - \ln(1+x) \sim \frac{x^2}{2}$$

---

## 六、无穷大的比较

### 6.1 常见的无穷大阶次（$x \to +\infty$）

> $$\ln x \ll x^a \ll a^x \ll x! \ll x^x$$
>
> 其中 $a > 1$，$0 < a_0 < a_1$。
>
> 更精确地：
> $$\ln x \ll \ln^2 x \ll \cdots \ll x^{0.01} \ll x^{0.1} \ll x \ll x^2 \ll \cdots \ll 2^x \ll 3^x \ll \cdots \ll x! \ll x^x$$

### 6.2 应用

> - $\lim_{x \to +\infty} \frac{\ln x}{x^a} = 0$（$a > 0$）
> - $\lim_{x \to +\infty} \frac{x^a}{e^x} = 0$（$a > 0$）
> - $\lim_{x \to +\infty} \frac{a^x}{x^x} = 0$（$a > 0$）

---

## 七、典型例题

### 例 1：等价无穷小替换求极限

**题目**：求 $\lim_{x \to 0} \frac{\tan x - \sin x}{x^3}$

**解**：

$$\frac{\tan x - \sin x}{x^3} = \frac{\sin x}{x^3} \cdot \frac{1 - \cos x}{\cos x}$$

利用等价无穷小：$\sin x \sim x$，$1 - \cos x \sim \frac{x^2}{2}$，$\cos x \to 1$：

$$= \frac{x}{x^3} \cdot \frac{\frac{x^2}{2}}{1} = \frac{1}{x^2} \cdot \frac{x^2}{2} = \frac{1}{2}$$

故 $\lim_{x \to 0} \frac{\tan x - \sin x}{x^3} = \frac{1}{2}$。

### 例 2：利用无穷小与无穷大关系

**题目**：求 $\lim_{x \to 0} x \cdot \cot x$

**解**：

$$x \cdot \cot x = \frac{x}{\tan x} \sim \frac{x}{x} = 1$$

故 $\lim_{x \to 0} x \cot x = 1$。

### 例 3：无穷大的极限

**题目**：求 $\lim_{x \to 0} \frac{1}{x \sin x}$

**解**：

当 $x \to 0$ 时，$x \sin x \sim x \cdot x = x^2 \to 0$（无穷小）

故 $\frac{1}{x \sin x} \to +\infty$（无穷大的倒数关系，注意 $x \sin x > 0$ 在 $x$ 接近 0 时成立）

### 例 4：含参等价无穷小

**题目**：若 $x \to 0$ 时，$(1 + ax^2)^{\frac{1}{3}} - 1 \sim \cos x - 1$，求 $a$。

**解**：

左边：$(1 + ax^2)^{\frac{1}{3}} - 1 \sim \frac{1}{3} \cdot ax^2 = \frac{a}{3}x^2$

右边：$\cos x - 1 \sim -\frac{x^2}{2}$

由等价关系：$\frac{a}{3}x^2 \sim -\frac{x^2}{2}$，故 $\frac{a}{3} = -\frac{1}{2}$，$a = -\frac{3}{2}$。

### 例 5：无穷小阶数的判断

**题目**：当 $x \to 0$ 时，$f(x) = x - \sin x$ 是 $x$ 的几阶无穷小？

**解**：

$$\lim_{x \to 0} \frac{x - \sin x}{x^k} \stackrel{\text{洛必达}}{=} \lim_{x \to 0} \frac{1 - \cos x}{kx^{k-1}}$$

当 $k = 3$ 时：$\lim_{x \to 0} \frac{1 - \cos x}{3x^2} = \lim_{x \to 0} \frac{\frac{x^2}{2}}{3x^2} = \frac{1}{6} \neq 0$

故 $f(x) = x - \sin x$ 是 $x$ 的 **3 阶无穷小**，且 $x - \sin x \sim \frac{x^3}{6}$。

---

## 八、易错点提醒

>
> 1. **无穷小不是 0**：无穷小是趋向 0 的变量，不是常数 0（但 0 是特殊的无穷小）
> 2. **等价无穷小替换只能在乘除中**：$\frac{\sin x - x}{x^3}$ 中不能将 $\sin x$ 替换为 $x$
> 3. **无穷大不是极限**：$\lim f(x) = \infty$ 表示 $f(x)$ 发散，只是发散的一种特殊方式
> 4. **$\infty - \infty$ 是不定式**：两个无穷大的差不一定有意义
> 5. **$0 \times \infty$ 是不定式**：无穷小与无穷大的乘积不一定是无穷小或无穷大
> 6. **等价无穷小替换的推广**：$(1+u)^a - 1 \sim au$ 中 $u$ 可以是任何趋向 0 的表达式
> 7. **加减中的等价替换**：只有当替换后不为 0 时才能替换（精确到足够高阶）
> 8. **无穷大之间不能比较大小**：$\lim f(x) = +\infty$，$\lim g(x) = +\infty$，但 $f(x)$ 和 $g(x)$ 的增长速度可能不同

---

## 补充内容

> 武忠祥《2021考研高等数学0基础课》讲义 (6)--1.9-1.10笔记小结（极限存在法则与两个重要极限）

### 补充一：夹逼准则的详细描述

> 如果数列 $\{x_n\}$、$\{y_n\}$ 及 $\{z_n\}$ 满足：
> (1) 存在 $N$，当 $n > N$ 时，$x_n \leq y_n \leq z_n$
> (2) $\lim_{n \to \infty} x_n = \lim_{n \to \infty} z_n = a$
>
> 则 $\lim_{n \to \infty} y_n = a$。

> 如果：
> (1) 当 $x \in \mathring{U}(x_0, \delta)$ 时，$f(x) \leq g(x) \leq h(x)$
> (2) $\lim_{x \to x_0} f(x) = \lim_{x \to x_0} h(x) = a$
>
> 则 $\lim_{x \to x_0} g(x) = a$。

### 补充二：夹逼准则经典例题

> 求 $\lim_{n \to \infty}\left[\frac{1}{\sqrt{n^2+1}} + \frac{1}{\sqrt{n^2+2}} + \cdots + \frac{1}{\sqrt{n^2+n}}\right]$
>
> **解**：记 $S_n = \sum_{k=1}^{n}\frac{1}{\sqrt{n^2+k}}$
>
> 由于 $\sqrt{n^2+1} \leq \sqrt{n^2+k} \leq \sqrt{n^2+n}$，故
> $$\frac{n}{\sqrt{n^2+n}} \leq S_n \leq \frac{n}{\sqrt{n^2+1}}$$
>
> 而 $\lim_{n \to \infty}\frac{n}{\sqrt{n^2+n}} = \lim_{n \to \infty}\frac{1}{\sqrt{1+\frac{1}{n}}} = 1$
>
> $\lim_{n \to \infty}\frac{n}{\sqrt{n^2+1}} = \lim_{n \to \infty}\frac{1}{\sqrt{1+\frac{1}{n^2}}} = 1$
>
> 由夹逼准则，原极限 $= 1$。

> 求 $\lim_{x \to +\infty} (2 + \sin x)^{\frac{1}{x}}$
>
> **解**：由于 $1 \leq 2 + \sin x \leq 3$，故
> $$1 \leq (2 + \sin x)^{\frac{1}{x}} \leq 3^{\frac{1}{x}}$$
>
> 而 $\lim_{x \to +\infty} 3^{\frac{1}{x}} = 1$，由夹逼准则得原极限 $= 1$。

### 补充三：第一个重要极限 $\lim_{x \to 0} \frac{\sin x}{x} = 1$

>
> 当 $0 < x < \frac{\pi}{2}$ 时，考虑单位圆中的几何关系：
>
> 在单位圆中，设圆心角为 $x$（弧度），则：
> - 三角形 OAB 的面积 = $\frac{1}{2}\sin x$
> - 扇形 OAB 的面积 = $\frac{1}{2}x$
> - 三角形 OAC 的面积 = $\frac{1}{2}\tan x$
>
> 由面积关系：$\frac{1}{2}\sin x < \frac{1}{2}x < \frac{1}{2}\tan x$
>
> 即 $\sin x < x < \tan x$（$0 < x < \frac{\pi}{2}$）
>
> 各部分除以 $\sin x > 0$：
> $$1 < \frac{x}{\sin x} < \frac{1}{\cos x}$$
>
> 取倒数（不等号反向）：
> $$\cos x < \frac{\sin x}{x} < 1$$
>
> 由 $\lim_{x \to 0} \cos x = 1$，$\lim_{x \to 0} 1 = 1$，根据夹逼准则：
> $$\lim_{x \to 0} \frac{\sin x}{x} = 1$$
>
> 由奇函数性质，$x < 0$ 时也成立。$\blacksquare$

> $$\lim_{\Delta \to 0} \frac{\sin \Delta}{\Delta} = 1 \quad (\Delta \neq 0)$$
>
> 其中 $\Delta$ 可以是任何趋向 $0$ 的表达式。
>
> **应用举例**：
> - $\lim_{x \to 0} \frac{\sin(x^2)}{x^2} = 1$
> - $\lim_{x \to \infty} x \sin\frac{1}{x} = \lim_{x \to \infty} \frac{\sin\frac{1}{x}}{\frac{1}{x}} = 1$
> - $\lim_{x \to 0} \frac{\tan x}{x} = \lim_{x \to 0} \frac{\sin x}{x} \cdot \frac{1}{\cos x} = 1$
> - $\lim_{x \to 0} \frac{1 - \cos x}{x^2} = \lim_{x \to 0} \frac{2\sin^2\frac{x}{2}}{x^2} = \frac{1}{2}$
> - $\lim_{x \to 0} \frac{\arctan x}{x} = 1$（令 $t = \arctan x$，则 $x = \tan t$）

### 补充四：单调有界准则证明 $(1+\frac{1}{n})^n$ 收敛

>
> 令 $a_n = (1 + \frac{1}{n})^n$。
>
> **第一步：证明单调递增**
>
> $a_n = \underbrace{(1+\frac{1}{n})(1+\frac{1}{n})\cdots(1+\frac{1}{n})}_{n \text{ 个}} \cdot 1$
>
> 这是 $n+1$ 个正数的乘积，由均值不等式：
> $$\sqrt[n+1]{a_n} \leq \frac{n \cdot (1+\frac{1}{n}) + 1}{n+1} = \frac{n+1+1}{n+1} = 1 + \frac{1}{n+1}$$
>
> 故 $a_n \leq (1 + \frac{1}{n+1})^{n+1} = a_{n+1}$，单调递增。
>
> **第二步：证明有上界**
>
> $\frac{1}{4}a_n = \frac{1}{2} \cdot \frac{1}{2} \cdot (1+\frac{1}{n})^n < \left(\frac{n+1+1}{n+2}\right)^{n+2} < 1$
>
> 故 $a_n < 4$，有上界。
>
> 由单调有界准则，$\{a_n\}$ 收敛。此极限定义为 **$e$**（自然对数的底）。

### 补充五：第二个重要极限

>
> **数列形式**：$\lim_{n \to \infty}\left(1 + \frac{1}{n}\right)^n = e$
>
> **函数形式**：$\lim_{x \to \infty}\left(1 + \frac{1}{x}\right)^x = e$
>
> **等价形式**：$\lim_{x \to 0}(1 + x)^{\frac{1}{x}} = e$
>
> **推广**：$\lim_{\Delta \to 0}(1 + \Delta)^{\frac{1}{\Delta}} = e$（$\Delta \neq 0$）

### 补充六：$1^\infty$ 型不定式的处理

> 若 $\lim f(x) = 1$，$\lim g(x) = \infty$，则
> $$\lim f(x)^{g(x)} = e^{\lim g(x)[f(x)-1]}$$
>
> 这个公式的本质来自第二个重要极限：$(1+u)^{\frac{1}{u}} \to e$。
>
> **例子**：
> $$\lim_{x \to \infty}\left(\frac{x+1}{x}\right)^x = \lim_{x \to \infty}\left(1 + \frac{1}{x}\right)^x = e$$
>
> $$\lim_{x \to 0}(1 + 2x)^{\frac{1}{x}} = e^{\lim_{x \to 0}\frac{2x}{x}} = e^2$$

### 补充七：无穷小与无穷大的严格定义对比

>
> **无穷小**：$\lim_{x \to x_0} f(x) = 0$ → 称 $f(x)$ 为 $x \to x_0$ 时的无穷小量
>
> **无穷大**：$\forall M > 0$，$\exists \delta > 0$，当 $0 < |x - x_0| < \delta$ 时，$|f(x)| > M$ → 称 $f(x)$ 为 $x \to x_0$ 时的无穷大量
>
> **正无穷大**：$\lim_{x \to x_0} f(x) = +\infty$（只要求 $f(x) > M$）
>
> **负无穷大**：$\lim_{x \to x_0} f(x) = -\infty$（只要求 $f(x) < -M$）
>
> ⚠️ **无穷大是发散的**（极限不存在），但用 $\lim f(x) = \infty$ 表示这种特殊的发散方式。

### 补充八：无穷小与函数极限的关系

> $$\lim f(x) = A \Leftrightarrow f(x) = A + \alpha(x), \quad \text{其中} \lim \alpha(x) = 0$$
>
> 即：**极限存在 $\Leftrightarrow$ 函数 = 常数 + 无穷小**
>
> 这个定理将极限问题转化为无穷小问题，是极限理论的基础。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 4：数列极限的概念]] — 极限概念
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 11：无穷小量阶的比较]] — 阶的比较
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 10：求极限]] — 求极限
