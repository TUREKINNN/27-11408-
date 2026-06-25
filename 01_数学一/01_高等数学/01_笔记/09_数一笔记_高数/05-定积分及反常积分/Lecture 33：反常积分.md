---
title: "Lecture 33：反常积分"
chapter: "05-定积分及反常积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 反常积分, 无穷区间积分, 无界函数积分, P积分]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 33：反常积分

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，选择题高频考点） |
| **分值分布** | 约 4-10 分（选择题判敛散、计算题求值） |
| **题型** | 判断敛散性、计算反常积分值、Γ函数 |
| **难度** | 中等偏难（敛散性判断需要技巧） |

---

## 一、无穷区间上的反常积分

>
> **定义 1（上限无穷）**：
> $$\int_a^{+\infty} f(x)\,\mathrm{d}x = \lim_{b\to+\infty}\int_a^b f(x)\,\mathrm{d}x$$
>
> **定义 2（下限无穷）**：
> $$\int_{-\infty}^b f(x)\,\mathrm{d}x = \lim_{a\to-\infty}\int_a^b f(x)\,\mathrm{d}x$$
>
> **定义 3（两端无穷）**：
> $$\int_{-\infty}^{+\infty} f(x)\,\mathrm{d}x = \int_{-\infty}^c f(x)\,\mathrm{d}x + \int_c^{+\infty} f(x)\,\mathrm{d}x$$
>
> 其中 $c$ 为任意常数。**两个积分都收敛时，才称 $\int_{-\infty}^{+\infty}$ 收敛**。

若极限存在，则称反常积分**收敛**；若极限不存在，则称**发散**。

---

## 二、无界函数的反常积分（瑕积分）

>
> **情形 1（$b$ 为瑕点，即 $f(b) = \infty$）**：
> $$\int_a^b f(x)\,\mathrm{d}x = \lim_{\varepsilon\to 0^+}\int_a^{b-\varepsilon} f(x)\,\mathrm{d}x$$
>
> **情形 2（$a$ 为瑕点，即 $f(a) = \infty$）**：
> $$\int_a^b f(x)\,\mathrm{d}x = \lim_{\varepsilon\to 0^+}\int_{a+\varepsilon}^b f(x)\,\mathrm{d}x$$
>
> **情形 3（$c \in (a, b)$ 为瑕点）**：
> $$\int_a^b f(x)\,\mathrm{d}x = \int_a^c f(x)\,\mathrm{d}x + \int_c^b f(x)\,\mathrm{d}x$$
>
> 两个积分都收敛时，才称 $\int_a^b$ 收敛。

> 瑕积分的被积函数在区间内有**无穷间断点**（瑕点），表面形式与定积分相同，但本质不同！计算前**必须先判断有无瑕点**。

---

## 三、P 积分（重要判敛标准）

>
> **无穷区间上的 P 积分**：
> $$\boxed{\int_1^{+\infty}\frac{1}{x^p}\,\mathrm{d}x = \begin{cases} \text{收敛（值为 } \frac{1}{p-1}\text{）}, & p > 1 \\ \text{发散}, & p \le 1 \end{cases}}$$
>
> **瑕积分的 P 积分**（$x = 0$ 为瑕点）：
> $$\boxed{\int_0^1\frac{1}{x^p}\,\mathrm{d}x = \begin{cases} \text{收敛（值为 } \frac{1}{1-p}\text{）}, & p < 1 \\ \text{发散}, & p \ge 1 \end{cases}}$$
>
> **综合记忆**：
> $$\int_0^{+\infty}\frac{1}{x^p}\,\mathrm{d}x \quad \text{对任何 } p \text{ 都发散（两边不可能同时收敛）}$$

> **无穷区间**：$p > 1$ 收敛，"$\int_1^{+\infty}\frac{1}{x}$ 发散"（$p = 1$ 是临界）
> **瑕积分**：$p < 1$ 收敛，"$\int_0^1\frac{1}{x}$ 发散"（$p = 1$ 是临界）
>
> 注意：两个方向的条件**相反**！

---

## 四、反常积分的比较判别法

> 设 $0 \le f(x) \le g(x)$，$x \ge a$：
>
> - 若 $\int_a^{+\infty}g(x)\,\mathrm{d}x$ **收敛**，则 $\int_a^{+\infty}f(x)\,\mathrm{d}x$ **收敛**
> - 若 $\int_a^{+\infty}f(x)\,\mathrm{d}x$ **发散**，则 $\int_a^{+\infty}g(x)\,\mathrm{d}x$ **发散**

> 设 $f(x) \ge 0$，若 $\lim\limits_{x\to+\infty}x^p f(x) = l$：
>
> - 当 $p > 1$，$0 \le l < +\infty$ 时，$\int_a^{+\infty}f(x)\,\mathrm{d}x$ **收敛**
> - 当 $p \le 1$，$0 < l \le +\infty$ 时，$\int_a^{+\infty}f(x)\,\mathrm{d}x$ **发散**
>
> 对瑕积分（$b$ 为瑕点）：若 $\lim\limits_{x\to b^-}(b-x)^p f(x) = l$：
>
> - 当 $0 < p < 1$，$0 \le l < +\infty$ 时，$\int_a^b f(x)\,\mathrm{d}x$ **收敛**
> - 当 $p \ge 1$，$0 < l \le +\infty$ 时，$\int_a^b f(x)\,\mathrm{d}x$ **发散**

---

## 五、绝对收敛与条件收敛

>
> - **绝对收敛**：$\int_a^{+\infty}|f(x)|\,\mathrm{d}x$ 收敛 → $\int_a^{+\infty}f(x)\,\mathrm{d}x$ 必收敛
> - **条件收敛**：$\int_a^{+\infty}f(x)\,\mathrm{d}x$ 收敛但 $\int_a^{+\infty}|f(x)|\,\mathrm{d}x$ 发散

**常见绝对收敛的例子**：$\int_1^{+\infty}\frac{\sin x}{x^2}\,\mathrm{d}x$（因 $\left|\frac{\sin x}{x^2}\right| \le \frac{1}{x^2}$，$p=2>1$ 收敛）

**常见条件收敛的例子**：$\int_1^{+\infty}\frac{\sin x}{x}\,\mathrm{d}x$（收敛但不绝对收敛）

---

## 六、常用反常积分公式

>
> $$\int_1^{+\infty}\frac{1}{x^p}\,\mathrm{d}x \quad (p > 1 \text{ 收敛})$$
>
> $$\int_0^{+\infty}e^{-x}\,\mathrm{d}x = 1$$
>
> $$\int_0^{+\infty}e^{-x^2}\,\mathrm{d}x = \frac{\sqrt{\pi}}{2}$$
>
> $$\Gamma(s) = \int_0^{+\infty}x^{s-1}e^{-x}\,\mathrm{d}x = (s-1)!\quad (s \text{ 为正整数})$$
>
> $$\Gamma\left(\frac{1}{2}\right) = \sqrt{\pi}$$

---

## 七、典型例题

### 例 1：无穷区间积分

**题目**：求 $\displaystyle\int_1^{+\infty}\frac{1}{x(1+x)}\,\mathrm{d}x$

**解**：

$$\frac{1}{x(1+x)} = \frac{1}{x} - \frac{1}{1+x}$$

$$\int_1^b\left(\frac{1}{x} - \frac{1}{1+x}\right)\mathrm{d}x = \ln x - \ln(1+x)\Big|_1^b = \ln\frac{b}{1+b} - \ln\frac{1}{2}$$

$$\lim_{b\to+\infty}\ln\frac{b}{1+b} = \ln 1 = 0$$

$$\int_1^{+\infty}\frac{1}{x(1+x)}\,\mathrm{d}x = 0 + \ln 2 = \ln 2$$

$$\boxed{\int_1^{+\infty}\frac{1}{x(1+x)}\,\mathrm{d}x = \ln 2}$$

---

### 例 2：判断敛散性

**题目**：判断 $\displaystyle\int_0^{+\infty}\frac{x}{1+x^2}\,\mathrm{d}x$ 的敛散性。

**解**：

$$\lim_{x\to+\infty}x\cdot\frac{x}{1+x^2} = \lim_{x\to+\infty}\frac{x^2}{1+x^2} = 1$$

由极限审敛法，$p = 1$，$l = 1 > 0$，故 $\int_0^{+\infty}\frac{x}{1+x^2}\,\mathrm{d}x$ **发散**。

---

### 例 3：瑕积分

**题目**：求 $\displaystyle\int_0^1\frac{1}{\sqrt{1-x}}\,\mathrm{d}x$

**解**：

$x = 1$ 为瑕点，$f(x) = \frac{1}{\sqrt{1-x}} = \frac{1}{(1-x)^{1/2}}$

$p = \frac{1}{2} < 1$，故积分**收敛**。

$$\int_0^1\frac{1}{\sqrt{1-x}}\,\mathrm{d}x = \lim_{\varepsilon\to 0^+}\int_0^{1-\varepsilon}\frac{\mathrm{d}x}{\sqrt{1-x}} = \lim_{\varepsilon\to 0^+}\left[-2\sqrt{1-x}\right]_0^{1-\varepsilon}$$

$$= \lim_{\varepsilon\to 0^+}\left(-2\sqrt{\varepsilon} + 2\right) = 2$$

$$\boxed{\int_0^1\frac{1}{\sqrt{1-x}}\,\mathrm{d}x = 2}$$

---

### 例 4：Γ函数

**题目**：求 $\displaystyle\int_0^{+\infty}x^2 e^{-x}\,\mathrm{d}x$

**解**：

这是 $\Gamma$ 函数：$\int_0^{+\infty}x^{3-1}e^{-x}\,\mathrm{d}x = \Gamma(3) = 2! = 2$

$$\boxed{\int_0^{+\infty}x^2 e^{-x}\,\mathrm{d}x = 2}$$

---

### 例 5：综合判断

**题目**：判断 $\displaystyle\int_0^1\frac{\ln x}{1-x}\,\mathrm{d}x$ 的敛散性。

**解**：

瑕点为 $x = 0$ 和 $x = 1$，需分段判断。

在 $x \to 0^+$ 处：$\frac{\ln x}{1-x} \sim \ln x$，$\int_0^1\ln x\,\mathrm{d}x = [x\ln x - x]_0^1 = -1$（收敛）

在 $x \to 1^-$ 处：$\frac{\ln x}{1-x} \to -1$（有限值），无瑕点。

故原积分**收敛**。

---

## 📝 总结

| 类型 | 定义 | 判敛标准 |
|------|------|----------|
| **无穷区间** | $\int_a^{+\infty}f(x)\mathrm{d}x = \lim\limits_{b\to+\infty}\int_a^b$ | $p > 1$ 收敛 |
| **瑕积分** | $\int_a^b f(x)\mathrm{d}x = \lim\limits_{\varepsilon\to 0^+}\int_{a+\varepsilon}^b$ | $p < 1$ 收敛 |
| **Γ函数** | $\Gamma(s) = \int_0^{+\infty}x^{s-1}e^{-x}\mathrm{d}x$ | $s > 0$ 收敛 |

> 1. 反常积分计算前**必须先判敛**，发散的积分不能用 N-L 公式直接算！
> 2. $\int_{-\infty}^{+\infty}$ **必须两端都收敛**才收敛，不能"正负抵消"
> 3. 瑕积分中**瑕点可能在区间内部**，需要分段处理
> 4. P 积分中无穷区间和瑕积分的敛散条件**正好相反**（$p > 1$ vs $p < 1$）
> 5. $\int_0^1 \frac{1}{x}\mathrm{d}x$ 是**瑕积分且发散**（$p = 1$），不要与 $\ln x$ 混淆

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 31：定积分的基本概念]] — 定积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 32：定积分的计算：积分上限的函数]] — 计算
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 50：幂级数]] — 级数
