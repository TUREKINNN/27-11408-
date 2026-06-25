---
title: "Lecture 30：分部积分法"
chapter: "04-不定积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 分部积分法, 反三角函数积分, 对数函数积分]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 30：分部积分法

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，不定积分核心方法之一） |
| **分值分布** | 约 5-10 分（计算题中的重要步骤） |
| **题型** | 求不定积分、与递推公式结合、与微分方程结合 |
| **难度** | 中等偏难（关键是正确选择 $u$ 和 $v$） |

---

## 一、分部积分公式

> 设 $u = u(x)$，$v = v(x)$ 具有连续导数，则：
>
> $$\boxed{\int u\,\mathrm{d}v = uv - \int v\,\mathrm{d}u}$$
>
> 即：
> $$\int u(x)v'(x)\,\mathrm{d}x = u(x)v(x) - \int v(x)u'(x)\,\mathrm{d}x$$

**本质**：把求 $\int u\,\mathrm{d}v$ 转化为求 $\int v\,\mathrm{d}u$，如果后者更简单，则分部积分成功。

---

## 二、8 种使用场合


### 场合 1：多项式 × 指数函数

$$\int P_n(x)\,e^{ax}\,\mathrm{d}x$$

> **选择**：$u = P_n(x)$，$\mathrm{d}v = e^{ax}\,\mathrm{d}x$
> **原理**：多项式求导逐步降次，$e^{ax}$ 积分不变

### 场合 2：多项式 × 正弦/余弦函数

$$\int P_n(x)\sin(ax)\,\mathrm{d}x \quad \text{或} \quad \int P_n(x)\cos(ax)\,\mathrm{d}x$$

> **选择**：$u = P_n(x)$，$\mathrm{d}v = \sin(ax)\,\mathrm{d}x$（或 $\cos(ax)\,\mathrm{d}x$）
> **原理**：多项式求导逐步降次，三角函数积分保持同类型

### 场合 3：多项式 × 对数函数

$$\int P_n(x)\ln x\,\mathrm{d}x$$

> **选择**：$u = \ln x$，$\mathrm{d}v = P_n(x)\,\mathrm{d}x$
> **原理**：对数函数求导变为有理函数 $\frac{1}{x}$，比原来简单

### 场合 4：多项式 × 反三角函数

$$\int P_n(x)\arcsin x\,\mathrm{d}x \quad \text{或} \quad \int P_n(x)\arctan x\,\mathrm{d}x$$

> **选择**：$u = \arcsin x$（或 $\arctan x$），$\mathrm{d}v = P_n(x)\,\mathrm{d}x$
> **原理**：反三角函数求导变为代数函数，比原来简单

### 场合 5：指数函数 × 三角函数

$$\int e^{ax}\sin(bx)\,\mathrm{d}x \quad \text{或} \quad \int e^{ax}\cos(bx)\,\mathrm{d}x$$

> **选择**：$u$ 和 $v$ 任意选择均可（两种选法等价）
> **原理**：分部两次后出现循环，解方程即可得到结果
> **口诀**："指数三角，谁当 $u$ 都行，分部两次解方程"

### 场合 6：指数函数 × 对数函数

$$\int e^{ax}\ln x\,\mathrm{d}x$$

> **选择**：$u = \ln x$，$\mathrm{d}v = e^{ax}\,\mathrm{d}x$

### 场合 7：三角函数 × 对数函数

$$\int \sin(ax)\ln x\,\mathrm{d}x$$

> **选择**：$u = \ln x$，$\mathrm{d}v = \sin(ax)\,\mathrm{d}x$

### 场合 8：单独的对数/反三角函数

$$\int \ln x\,\mathrm{d}x \quad \int \arcsin x\,\mathrm{d}x \quad \int \arctan x\,\mathrm{d}x$$

> **选择**：$u = \ln x$（或 $\arcsin x$，$\arctan x$），$\mathrm{d}v = \mathrm{d}x$
> **原理**：利用 $\int 1\,\mathrm{d}x = x$ 作为 $v$

---

## 三、选择 $u$ 的优先级

> 按优先级从高到低选择 $u$：
>
> | 优先级 | 类型 | 英文缩写 | 例子 |
> |--------|------|----------|------|
> | ① 最优先 | **对**数函数 | **L**ogarithmic | $\ln x$，$\log_a x$ |
> | ② | **反**三角函数 | **I**nverse trig | $\arcsin x$，$\arctan x$ |
> | ③ | **幂**函数（多项式） | **A**lgebraic | $x^n$，$P_n(x)$ |
> | ④ | **三**角函数 | **T**rigonometric | $\sin x$，$\cos x$ |
> | ⑤ 最低优先 | **指**数函数 | **E**xponential | $e^x$，$a^x$ |

**核心原则**：选 $u$ 使得 $u'$ 比 $u$ 更简单，$\int v\,\mathrm{d}u$ 比 $\int u\,\mathrm{d}v$ 更容易求。

---

## 四、特殊技巧

### 技巧 1：循环型分部积分

对 $\int e^{ax}\sin bx\,\mathrm{d}x$ 这类问题：

设 $I = \int e^{ax}\sin bx\,\mathrm{d}x$，分部两次后得到：

$$I = \frac{e^{ax}(a\sin bx - b\cos bx)}{a^2 + b^2} + C$$

**推导过程**：

取 $u = \sin bx$，$\mathrm{d}v = e^{ax}\mathrm{d}x$：

$$I = \frac{e^{ax}\sin bx}{a} - \frac{b}{a}\int e^{ax}\cos bx\,\mathrm{d}x$$

再对 $\int e^{ax}\cos bx\,\mathrm{d}x$ 分部（$u = \cos bx$）：

$$\int e^{ax}\cos bx\,\mathrm{d}x = \frac{e^{ax}\cos bx}{a} + \frac{b}{a}\int e^{ax}\sin bx\,\mathrm{d}x = \frac{e^{ax}\cos bx}{a} + \frac{b}{a}I$$

代入得：$I = \dfrac{e^{ax}\sin bx}{a} - \dfrac{b}{a}\left(\dfrac{e^{ax}\cos bx}{a} + \dfrac{b}{a}I\right)$

解方程：$\left(1 + \dfrac{b^2}{a^2}\right)I = \dfrac{e^{ax}(a\sin bx - b\cos bx)}{a^2}$

$$\boxed{I = \frac{e^{ax}(a\sin bx - b\cos bx)}{a^2 + b^2} + C}$$

### 技巧 2：递推公式

利用分部积分建立递推关系，如 $I_n = \int \sin^n x\,\mathrm{d}x$：

$$I_n = -\frac{1}{n}\sin^{n-1}x\cos x + \frac{n-1}{n}I_{n-2}$$

### 技巧 3：先变形再分部

有些题目需要先做三角恒等变换或其他变形，再使用分部积分。

---

## 五、典型例题

### 例 1：多项式 × 指数函数

**题目**：求 $\displaystyle\int (x^2 + 1)e^x\,\mathrm{d}x$

**解**：

$$\int (x^2 + 1)e^x\,\mathrm{d}x = \int x^2 e^x\,\mathrm{d}x + \int e^x\,\mathrm{d}x$$

对 $\int x^2 e^x\,\mathrm{d}x$ 分部（$u = x^2$，$\mathrm{d}v = e^x\mathrm{d}x$）：

$$\int x^2 e^x\,\mathrm{d}x = x^2 e^x - 2\int x e^x\,\mathrm{d}x$$

再分部（$u = x$）：

$$\int x e^x\,\mathrm{d}x = xe^x - e^x + C$$

合并：

$$\int (x^2 + 1)e^x\,\mathrm{d}x = x^2 e^x - 2(xe^x - e^x) + e^x + C = x^2 e^x - 2xe^x + 3e^x + C$$

$$\boxed{\int (x^2 + 1)e^x\,\mathrm{d}x = e^x(x^2 - 2x + 3) + C}$$

---

### 例 2：对数函数型

**题目**：求 $\displaystyle\int x^2\ln x\,\mathrm{d}x$

**解**：

令 $u = \ln x$，$\mathrm{d}v = x^2\mathrm{d}x$，则 $\mathrm{d}u = \frac{1}{x}\mathrm{d}x$，$v = \frac{x^3}{3}$

$$\int x^2\ln x\,\mathrm{d}x = \frac{x^3}{3}\ln x - \int \frac{x^3}{3}\cdot\frac{1}{x}\,\mathrm{d}x = \frac{x^3}{3}\ln x - \frac{1}{3}\int x^2\,\mathrm{d}x$$

$$= \frac{x^3}{3}\ln x - \frac{x^3}{9} + C$$

$$\boxed{\int x^2\ln x\,\mathrm{d}x = \frac{x^3}{3}\ln x - \frac{x^3}{9} + C}$$

---

### 例 3：反三角函数型

**题目**：求 $\displaystyle\int x\arctan x\,\mathrm{d}x$

**解**：

令 $u = \arctan x$，$\mathrm{d}v = x\mathrm{d}x$，则 $\mathrm{d}u = \frac{1}{1+x^2}\mathrm{d}x$，$v = \frac{x^2}{2}$

$$\int x\arctan x\,\mathrm{d}x = \frac{x^2}{2}\arctan x - \frac{1}{2}\int \frac{x^2}{1+x^2}\,\mathrm{d}x$$

$$= \frac{x^2}{2}\arctan x - \frac{1}{2}\int \left(1 - \frac{1}{1+x^2}\right)\mathrm{d}x$$

$$= \frac{x^2}{2}\arctan x - \frac{x}{2} + \frac{1}{2}\arctan x + C$$

$$\boxed{\int x\arctan x\,\mathrm{d}x = \frac{x^2 + 1}{2}\arctan x - \frac{x}{2} + C}$$

---

### 例 4：指数 × 三角函数（循环型）

**题目**：求 $\displaystyle\int e^x\sin x\,\mathrm{d}x$

**解**：

设 $I = \int e^x\sin x\,\mathrm{d}x$

令 $u = \sin x$，$\mathrm{d}v = e^x\mathrm{d}x$：

$$I = e^x\sin x - \int e^x\cos x\,\mathrm{d}x$$

对 $\int e^x\cos x\,\mathrm{d}x$ 分部（$u = \cos x$）：

$$\int e^x\cos x\,\mathrm{d}x = e^x\cos x + \int e^x\sin x\,\mathrm{d}x = e^x\cos x + I$$

代入：$I = e^x\sin x - e^x\cos x - I$

$$2I = e^x(\sin x - \cos x)$$

$$\boxed{\int e^x\sin x\,\mathrm{d}x = \frac{e^x(\sin x - \cos x)}{2} + C}$$

---

### 例 5：单独的反正切函数

**题目**：求 $\displaystyle\int \arctan x\,\mathrm{d}x$

**解**：

令 $u = \arctan x$，$\mathrm{d}v = \mathrm{d}x$，则 $\mathrm{d}u = \frac{1}{1+x^2}\mathrm{d}x$，$v = x$

$$\int \arctan x\,\mathrm{d}x = x\arctan x - \int \frac{x}{1+x^2}\,\mathrm{d}x = x\arctan x - \frac{1}{2}\ln(1+x^2) + C$$

$$\boxed{\int \arctan x\,\mathrm{d}x = x\arctan x - \frac{1}{2}\ln(1+x^2) + C}$$

---

### 例 6：递推公式

**题目**：建立 $I_n = \displaystyle\int \sec^n x\,\mathrm{d}x$ 的递推公式，并求 $I_2$。

**解**：

$$I_n = \int \sec^{n-2}x\cdot\sec^2 x\,\mathrm{d}x$$

令 $u = \sec^{n-2}x$，$\mathrm{d}v = \sec^2 x\,\mathrm{d}x$：

$$I_n = \sec^{n-2}x\tan x - (n-2)\int \sec^{n-2}x\tan^2 x\,\mathrm{d}x$$

$$= \sec^{n-2}x\tan x - (n-2)\int \sec^{n-2}x(\sec^2 x - 1)\,\mathrm{d}x$$

$$= \sec^{n-2}x\tan x - (n-2)I_n + (n-2)I_{n-2}$$

解出：

$$\boxed{I_n = \frac{\sec^{n-2}x\tan x}{n-1} + \frac{n-2}{n-1}I_{n-2}}$$

$I_2 = \int \sec^2 x\,\mathrm{d}x = \tan x + C$（基本公式）

---

## 📝 总结

| 场景 | $u$ 的选择 | 说明 |
|------|-----------|------|
| 多项式 × 指数 | $u = P_n(x)$ | 求导降次 |
| 多项式 × 三角 | $u = P_n(x)$ | 求导降次 |
| 多项式 × 对数 | $u = \ln x$ | 求导简化 |
| 多项式 × 反三角 | $u = \arcsin x$ 等 | 求导简化 |
| 指数 × 三角 | 任选均可 | 分部两次解方程 |
| 单独 $\ln x$ / $\arctan x$ | $u = \ln x$，$\mathrm{d}v = \mathrm{d}x$ | 配 $\mathrm{d}x$ |

> 1. 分部积分后**积分号内的 $\mathrm{d}u$ 别忘计算**：$\mathrm{d}u = u'(x)\mathrm{d}x$
> 2. 循环型必须**两次分部用同一种选法**，否则可能死循环
> 3. 负号容易丢：$\int \sin x\,\mathrm{d}x = -\cos x + C$
> 4. 递推公式要注意**初值条件**的确定

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 28：不定积分]] — 不定积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 29：两类换元积分法]] — 换元法
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 32：定积分的计算：积分上限的函数]] — 定积分
