---
title: "Lecture 22：洛必达法则"
chapter: "03-微分中值定理与导数应用"
tags: [考研, 数学一, 高等数学, 考研数学一, 洛必达法则, 不定式]
difficulty: ★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 22：洛必达法则

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（求极限的核心工具，每年必考） |
| **分值分布** | 约 4-10 分（选择/填空/解答中的极限计算步骤） |
| **题型** | 各种不定式的极限计算 |
| **难度** | 基础～中等 |

---

## 一、洛必达法则

### 1.1 $\dfrac{0}{0}$ 型

> 设：
> 1. $\lim\limits_{x \to a}f(x) = 0$，$\lim\limits_{x \to a}g(x) = 0$
> 2. 在 $a$ 的某去心邻域内，$f'(x)$ 和 $g'(x)$ 存在，且 $g'(x) \ne 0$
> 3. $\lim\limits_{x \to a}\dfrac{f'(x)}{g'(x)} = A$（$A$ 可以是有限数或 $\infty$）
>
> 则：
>
> $$\boxed{\lim_{x \to a}\frac{f(x)}{g(x)} = \lim_{x \to a}\frac{f'(x)}{g'(x)} = A}$$

### 1.2 $\dfrac{\infty}{\infty}$ 型

> 设：
> 1. $\lim\limits_{x \to a}f(x) = \infty$，$\lim\limits_{x \to a}g(x) = \infty$
> 2. 在 $a$ 的某去心邻域内，$f'(x)$ 和 $g'(x)$ 存在，且 $g'(x) \ne 0$
> 3. $\lim\limits_{x \to a}\dfrac{f'(x)}{g'(x)} = A$
>
> 则：
>
> $$\boxed{\lim_{x \to a}\frac{f(x)}{g(x)} = \lim_{x \to a}\frac{f'(x)}{g'(x)} = A}$$

**注**：以上 $x \to a$ 可替换为 $x \to a^+$、$x \to a^-$、$x \to +\infty$、$x \to -\infty$ 或 $x \to \infty$。

---

## 二、七种不定式

### 2.1 不定式分类


| 不定式 | 处理方法 |
|:---:|:---:|
| $\dfrac{0}{0}$ | **直接**用洛必达 |
| $\dfrac{\infty}{\infty}$ | **直接**用洛必达 |
| $0 \cdot \infty$ | 转化为 $\dfrac{0}{1/\infty} = \dfrac{0}{0}$ 或 $\dfrac{\infty}{1/0} = \dfrac{\infty}{\infty}$ |
| $\infty - \infty$ | **通分**或**有理化**转化为 $\dfrac{0}{0}$ 或 $\dfrac{\infty}{\infty}$ |
| $1^\infty$ | 取对数 $\to$ $0 \cdot \infty \to \dfrac{0}{0}$，或用重要极限 $e$ |
| $0^0$ | 取对数 $\to$ $0 \cdot \ln 0 = 0 \cdot (-\infty) \to \dfrac{0}{0}$ |
| $\infty^0$ | 取对数 $\to$ $0 \cdot \ln\infty = 0 \cdot \infty \to \dfrac{0}{0}$ |

### 2.2 转化技巧详解

**$0 \cdot \infty$ 型**：

$$\lim f(x)g(x) = \lim \frac{f(x)}{1/g(x)} \quad\left(\frac{0}{0}\text{型}\right) \quad \text{或} \quad \lim \frac{g(x)}{1/f(x)} \quad\left(\frac{\infty}{\infty}\text{型}\right)$$

> **选择标准**：哪个求导后更简单就放分母。

**$\infty - \infty$ 型**：

- 有分母的先**通分**
- 含根号的先**有理化**
- 利用等价无穷小化简

**$1^\infty$ 型**：

$$\lim f(x)^{g(x)} = e^{\lim g(x)\ln f(x)} = e^{\lim g(x)[f(x)-1]}$$

> $$\boxed{\lim [1 + \varphi(x)]^{g(x)} = e^{\lim \varphi(x) \cdot g(x)}}$$
>
> 其中 $\varphi(x) \to 0$，$g(x) \to \infty$。

---

## 三、使用洛必达的条件与注意事项

### 3.1 必须验证的条件

> 1. **是否为不定式**：只有 $\dfrac{0}{0}$ 和 $\dfrac{\infty}{\infty}$ 才能直接使用
> 2. **导数之比的极限是否存在**：若 $\lim\dfrac{f'}{g'}$ 不存在，**不能**用洛必达（但原极限可能存在）
> 3. **$g'(x) \ne 0$**：在去心邻域内分母的导数不能为零

### 3.2 常见错误

>
> **错误 1**：对非不定式使用洛必达
>
> $\lim\limits_{x \to 0}\dfrac{x}{\sin x + 1}$ **不是** $\dfrac{0}{0}$ 型（分母 $\to 1$），不能用洛必达，直接代入即可。
>
> **错误 2**：用洛必达后忘记化简
>
> 每次使用洛必达后，应先化简（约分、等价替换），再决定是否继续使用。
>
> **错误 3**：循环使用
>
> 有时使用洛必达后回到原式（如 $\dfrac{e^x + e^{-x}}{e^x + e^{-x}}$），此时应停止，用其他方法。
>
> **错误 4**：对离散变量 $n$ 直接使用洛必达
>
> $\lim\limits_{n \to \infty}\dfrac{f(n)}{g(n)}$ 不能直接对 $n$ 求导！需先化为 $\lim\limits_{x \to +\infty}\dfrac{f(x)}{g(x)}$，再用洛必达。

---

## 四、经典例题

### 【例1】$\dfrac{0}{0}$ 型

**题目**：求 $\lim\limits_{x \to 0}\dfrac{e^x - e^{-x} - 2x}{x - \sin x}$。

**解**：

$$\lim_{x \to 0}\frac{e^x - e^{-x} - 2x}{x - \sin x} \quad\left(\frac{0}{0}\right)$$

第一次洛必达：

$$= \lim_{x \to 0}\frac{e^x + e^{-x} - 2}{1 - \cos x} \quad\left(\frac{0}{0}\right)$$

等价替换 $1 - \cos x \sim \dfrac{x^2}{2}$：

$$= \lim_{x \to 0}\frac{e^x + e^{-x} - 2}{x^2/2} = 2\lim_{x \to 0}\frac{e^x + e^{-x} - 2}{x^2} \quad\left(\frac{0}{0}\right)$$

第二次洛必达：

$$= 2\lim_{x \to 0}\frac{e^x - e^{-x}}{2x} = \lim_{x \to 0}\frac{e^x - e^{-x}}{x} \quad\left(\frac{0}{0}\right)$$

第三次洛必达：

$$= \lim_{x \to 0}\frac{e^x + e^{-x}}{1} = 2$$

### 【例2】$1^\infty$ 型

**题目**：求 $\lim\limits_{x \to 0}\left(\dfrac{\sin x}{x}\right)^{\frac{1}{x^2}}$。

**解**：

$\lim\limits_{x \to 0}\left(\dfrac{\sin x}{x}\right) = 1$，指数 $\dfrac{1}{x^2} \to \infty$，是 $1^\infty$ 型。

$$L = \lim_{x \to 0}\frac{\ln(\sin x / x)}{x^2} = \lim_{x \to 0}\frac{\ln\sin x - \ln x}{x^2} \quad\left(\frac{0}{0}\right)$$

$$= \lim_{x \to 0}\frac{\frac{\cos x}{\sin x} - \frac{1}{x}}{2x} = \lim_{x \to 0}\frac{x\cos x - \sin x}{2x^2\sin x}$$

$$= \lim_{x \to 0}\frac{x\cos x - \sin x}{2x^3} \quad\left(\frac{0}{0}\right) = \lim_{x \to 0}\frac{-x\sin x}{6x^2} = \lim_{x \to 0}\frac{-\sin x}{6x} = -\frac{1}{6}$$

故原极限 $= e^{-1/6}$。

### 【例3】$\infty - \infty$ 型

**题目**：求 $\lim\limits_{x \to 0}\left(\dfrac{1}{\sin^2 x} - \dfrac{1}{x^2}\right)$。

**解**：

$$= \lim_{x \to 0}\frac{x^2 - \sin^2 x}{x^2\sin^2 x} = \lim_{x \to 0}\frac{(x - \sin x)(x + \sin x)}{x^4}$$

（用 $\sin^2 x \sim x^2$）

$$= \lim_{x \to 0}\frac{x - \sin x}{x^3} \cdot \lim_{x \to 0}\frac{x + \sin x}{x}$$

第二个极限 $= \lim\limits_{x \to 0}(1 + \dfrac{\sin x}{x}) = 2$

第一个极限（洛必达）：$\lim\limits_{x \to 0}\dfrac{1 - \cos x}{3x^2} = \lim\limits_{x \to 0}\dfrac{x^2/2}{3x^2} = \dfrac{1}{6}$

原式 $= \dfrac{1}{6} \times 2 = \dfrac{1}{3}$

### 【例4】洛必达失效的情况

**题目**：求 $\lim\limits_{x \to +\infty}\dfrac{x + \sin x}{x}$。

**解**：

这是 $\dfrac{\infty}{\infty}$ 型。尝试洛必达：

$$\lim_{x \to +\infty}\frac{1 + \cos x}{1} = \lim_{x \to +\infty}(1 + \cos x)$$

此极限**不存在**（$\cos x$ 振荡），洛必达**失效**。

正确做法：

$$\lim_{x \to +\infty}\frac{x + \sin x}{x} = \lim_{x \to +\infty}\left(1 + \frac{\sin x}{x}\right) = 1 + 0 = 1$$

> **教训**：洛必达法则只是充分条件，不是必要条件。当导数之比的极限不存在时，原极限仍可能存在，需用其他方法。

---

## 五、考研真题精选

### 【真题1】（2017年数一·选择）

**题目**：$\lim\limits_{x \to 0}\dfrac{\int_0^x t\ln(1+t\sin t)dt}{1 - \cos x^2} = $ ______。

**解**：

分母 $1 - \cos x^2 \sim \dfrac{(x^2)^2}{2} = \dfrac{x^4}{2}$

分子在 $x \to 0$ 时 $\sim \int_0^x t \cdot t\sin t \, dt = \int_0^x t^2\sin t \, dt$

（用洛必达 + 变上限积分求导）：

$$= \lim_{x \to 0}\frac{x\ln(1+x\sin x)}{2x\sin x \cdot \cos x \cdot 1} = \lim_{x \to 0}\frac{x \cdot x\sin x}{2x\sin x \cdot 2x} = \lim_{x \to 0}\frac{x^2\sin x}{4x^2\sin x} = \frac{1}{4}$$

（注：分母求导：$(1-\cos x^2)' = \sin(x^2) \cdot 2x \sim 2x^3$）

$$= \lim_{x \to 0}\frac{x\ln(1+x\sin x)}{2x \sin(x^2)} = \lim_{x \to 0}\frac{x \cdot x\sin x}{2x \cdot x^2} = \lim_{x \to 0}\frac{x^2\sin x}{2x^3} = \frac{1}{2}$$

**答案**：$\dfrac{1}{2}$

---

## 📝 本节要点总结

| 要点 | 内容 |
|------|------|
| 使用条件 | $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ 型 + 导数比极限存在 |
| $0 \cdot \infty$ | 放分母转化为 $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ |
| $\infty - \infty$ | 通分或有理化 |
| $1^\infty$ | $e^{\lim g(x)[f(x)-1]}$ |
| 不能用的情况 | 导数比极限不存在、非不定式、离散变量 |

> 洛必达不是万能的！使用前必须验证条件，使用后要化简。对于 $1^\infty$ 型，用 $e^{g(x)[f(x)-1]}$ 往往比取对数更快。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/03-微分中值定理与导数应用/Lecture 21：微分中值定理]] — 中值定理
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/03-微分中值定理与导数应用/Lecture 23：泰勒公式]] — 泰勒
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 10：求极限]] — 求极限
