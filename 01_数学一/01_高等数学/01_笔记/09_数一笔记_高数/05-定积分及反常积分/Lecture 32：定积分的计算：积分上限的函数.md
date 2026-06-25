---
title: "Lecture 32：定积分的计算：积分上限的函数"
chapter: "05-定积分及反常积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 变上限积分, 微积分基本定理, 牛顿-莱布尼茨公式]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 32：定积分的计算：积分上限的函数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，是连接微分与积分的桥梁） |
| **分值分布** | 约 10-15 分（解答题中高频出现，常与极限、导数结合） |
| **题型** | 变上限积分求导、牛顿-莱布尼茨公式应用、含参积分求导 |
| **难度** | 中等偏难（综合题较难，需要灵活运用） |

---

## 一、积分上限的函数（变上限积分）

> 设 $f(x)$ 在 $[a, b]$ 上连续，则对任意 $x \in [a, b]$，函数：
>
> $$\Phi(x) = \int_a^x f(t)\,\mathrm{d}t$$
>
> 称为 $f(x)$ 在 $[a, b]$ 上的**积分上限函数**（或**变上限积分**）。

**注意**：积分变量用 $t$ 表示（与上限 $x$ 区分），$x$ 是自变量。

---

## 二、微积分基本定理

> 设 $f(x)$ 在 $[a, b]$ 上连续，则 $\Phi(x) = \displaystyle\int_a^x f(t)\,\mathrm{d}t$ 在 $[a, b]$ 上可导，且：
>
> $$\boxed{\Phi'(x) = \frac{\mathrm{d}}{\mathrm{d}x}\int_a^x f(t)\,\mathrm{d}t = f(x)}$$
>
> 即**变上限积分对上限求导等于被积函数在上限处的值**。

**证明**：

$$\Phi'(x) = \lim_{\Delta x \to 0}\frac{\Phi(x + \Delta x) - \Phi(x)}{\Delta x} = \lim_{\Delta x \to 0}\frac{\int_x^{x+\Delta x}f(t)\,\mathrm{d}t}{\Delta x}$$

由积分中值定理，$\int_x^{x+\Delta x}f(t)\,\mathrm{d}t = f(\xi)\Delta x$（$\xi$ 在 $x$ 与 $x + \Delta x$ 之间）

当 $\Delta x \to 0$ 时，$\xi \to x$，由 $f(x)$ 的连续性：

$$\Phi'(x) = \lim_{\xi \to x}f(\xi) = f(x) \quad \blacksquare$$

> 这个定理说明：**连续函数一定有原函数**，且变上限积分就是它的一个原函数。
> 这是不定积分中"原函数存在定理"的严格证明。

---

## 三、变上限积分求导的推广形式

>
> **形式 1**：$\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\int_a^{\varphi(x)}f(t)\,\mathrm{d}t = f[\varphi(x)]\cdot\varphi'(x)$
>
> **形式 2**：$\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\int_{\psi(x)}^{\varphi(x)}f(t)\,\mathrm{d}t = f[\varphi(x)]\cdot\varphi'(x) - f[\psi(x)]\cdot\psi'(x)$
>
> **形式 3**：$\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\int_a^x f(x, t)\,\mathrm{d}t = \int_a^x \frac{\partial f(x, t)}{\partial x}\,\mathrm{d}t + f(x, x)$

**记忆口诀**："代上限乘上限导，减代下限乘下限导"

---

## 四、牛顿-莱布尼茨公式

> 设 $f(x)$ 在 $[a, b]$ 上连续，$F(x)$ 是 $f(x)$ 的一个原函数，则：
>
> $$\boxed{\int_a^b f(x)\,\mathrm{d}x = F(x)\Big|_a^b = F(b) - F(a)}$$
>
> **意义**：定积分的计算归结为求原函数在端点的差值，把积分问题转化为求不定积分。

**证明**：

设 $\Phi(x) = \int_a^x f(t)\,\mathrm{d}t$，$F(x)$ 是 $f(x)$ 的任一原函数。

则 $\Phi(x) = F(x) + C$，令 $x = a$：$\Phi(a) = 0 = F(a) + C$，故 $C = -F(a)$。

令 $x = b$：$\Phi(b) = \int_a^b f(t)\,\mathrm{d}t = F(b) - F(a)$。$\blacksquare$

---

## 五、定积分的换元法与分部积分法

### 定积分的换元法

> 设 $f(x)$ 在 $[a, b]$ 上连续，$x = \varphi(t)$ 在 $[\alpha, \beta]$（或 $[\beta, \alpha]$）上单调且有连续导数，$\varphi(\alpha) = a$，$\varphi(\beta) = b$，则：
>
> $$\boxed{\int_a^b f(x)\,\mathrm{d}x = \int_\alpha^\beta f[\varphi(t)]\,\varphi'(t)\,\mathrm{d}t}$$

> 定积分换元时**必须换上下限**！即换元后 $t$ 的范围 $[\alpha, \beta]$ 要相应改变。

### 定积分的分部积分法

>
> $$\boxed{\int_a^b u\,\mathrm{d}v = uv\Big|_a^b - \int_a^b v\,\mathrm{d}u}$$

---

## 六、华里士公式（点火公式）

>
> $$\boxed{\int_0^{\frac{\pi}{2}}\sin^n x\,\mathrm{d}x = \int_0^{\frac{\pi}{2}}\cos^n x\,\mathrm{d}x = \begin{cases} \frac{(n-1)!!}{n!!}\cdot\frac{\pi}{2}, & n \text{ 为偶数} \\ \frac{(n-1)!!}{n!!}, & n \text{ 为奇数} \end{cases}}$$
>
> 其中 $n!!$ 为双阶乘：$n!! = n(n-2)(n-4)\cdots$

**常用值**：
- $\int_0^{\pi/2}\sin^2 x\,\mathrm{d}x = \frac{1}{2}\cdot\frac{\pi}{2} = \frac{\pi}{4}$
- $\int_0^{\pi/2}\sin^3 x\,\mathrm{d}x = \frac{2}{3}$
- $\int_0^{\pi/2}\sin^4 x\,\mathrm{d}x = \frac{3}{4}\cdot\frac{1}{2}\cdot\frac{\pi}{2} = \frac{3\pi}{16}$

---

## 七、典型例题

### 例 1：变上限积分求导

**题目**：设 $\Phi(x) = \displaystyle\int_0^{x^2}\sin t^2\,\mathrm{d}t$，求 $\Phi'(x)$。

**解**：

由链式法则：

$$\Phi'(x) = \sin(x^2)^2 \cdot (x^2)' = 2x\sin x^4$$

$$\boxed{\Phi'(x) = 2x\sin x^4}$$

---

### 例 2：含变上限积分的极限

**题目**：求 $\displaystyle\lim_{x\to 0}\frac{\int_0^x \arctan t\,\mathrm{d}t}{x^2}$

**解**：

这是 $\frac{0}{0}$ 型，用洛必达法则：

$$\lim_{x\to 0}\frac{\int_0^x \arctan t\,\mathrm{d}t}{x^2} = \lim_{x\to 0}\frac{\arctan x}{2x} = \frac{1}{2}\lim_{x\to 0}\frac{\arctan x}{x}$$

由 $\lim\limits_{x\to 0}\frac{\arctan x}{x} = 1$：

$$= \frac{1}{2}$$

$$\boxed{\lim_{x\to 0}\frac{\int_0^x \arctan t\,\mathrm{d}t}{x^2} = \frac{1}{2}}$$

---

### 例 3：变上限积分与微分方程

**题目**：设 $f(x)$ 连续，$F(x) = \displaystyle\int_0^x (x - t)f(t)\,\mathrm{d}t$，求 $F''(x)$。

**解**：

先展开：$F(x) = x\int_0^x f(t)\,\mathrm{d}t - \int_0^x tf(t)\,\mathrm{d}t$

一阶导数：

$$F'(x) = \int_0^x f(t)\,\mathrm{d}t + xf(x) - xf(x) = \int_0^x f(t)\,\mathrm{d}t$$

二阶导数：

$$F''(x) = f(x)$$

$$\boxed{F''(x) = f(x)}$$

---

### 例 4：N-L 公式应用

**题目**：求 $\displaystyle\int_0^{\pi}\sqrt{1 + \sin x}\,\mathrm{d}x$

**解**：

利用 $1 + \sin x = \left(\sin\frac{x}{2} + \cos\frac{x}{2}\right)^2$：

$$\sqrt{1 + \sin x} = \left|\sin\frac{x}{2} + \cos\frac{x}{2}\right|$$

在 $[0, \pi]$ 上，$\frac{x}{2} \in [0, \frac{\pi}{2}]$，$\sin\frac{x}{2} + \cos\frac{x}{2} > 0$

$$\int_0^{\pi}\sqrt{1 + \sin x}\,\mathrm{d}x = \int_0^{\pi}\left(\sin\frac{x}{2} + \cos\frac{x}{2}\right)\mathrm{d}x$$

$$= \left[-2\cos\frac{x}{2} + 2\sin\frac{x}{2}\right]_0^{\pi} = (-2\cos\frac{\pi}{2} + 2\sin\frac{\pi}{2}) - (-2 + 0) = 2 + 2 = 4$$

$$\boxed{\int_0^{\pi}\sqrt{1 + \sin x}\,\mathrm{d}x = 4}$$

---

### 例 5：华里士公式

**题目**：求 $\displaystyle\int_0^{\pi}\sin^4 x\,\mathrm{d}x$

**解**：

由 $\sin^4 x$ 的周期性和对称性：

$$\int_0^{\pi}\sin^4 x\,\mathrm{d}x = 2\int_0^{\pi/2}\sin^4 x\,\mathrm{d}x = 2 \cdot \frac{3!!}{4!!}\cdot\frac{\pi}{2} = 2\cdot\frac{3\cdot 1}{4\cdot 2}\cdot\frac{\pi}{2} = \frac{3\pi}{8}$$

$$\boxed{\int_0^{\pi}\sin^4 x\,\mathrm{d}x = \frac{3\pi}{8}}$$

---

### 例 6：利用对称性简化计算

**题目**：求 $\displaystyle\int_0^{\pi}\frac{x\sin x}{1 + \cos^2 x}\,\mathrm{d}x$

**解**：

利用公式 $\int_0^a f(x)\,\mathrm{d}x = \int_0^a f(a-x)\,\mathrm{d}x$：

$$I = \int_0^{\pi}\frac{(\pi - x)\sin(\pi - x)}{1 + \cos^2(\pi - x)}\,\mathrm{d}x = \int_0^{\pi}\frac{(\pi - x)\sin x}{1 + \cos^2 x}\,\mathrm{d}x$$

两式相加：

$$2I = \pi\int_0^{\pi}\frac{\sin x}{1 + \cos^2 x}\,\mathrm{d}x$$

令 $t = \cos x$：$2I = -\pi\int_1^{-1}\frac{\mathrm{d}t}{1+t^2} = \pi\int_{-1}^{1}\frac{\mathrm{d}t}{1+t^2} = \pi\cdot 2\arctan 1 = \frac{\pi^2}{2}$

$$I = \frac{\pi^2}{4}$$

$$\boxed{\int_0^{\pi}\frac{x\sin x}{1 + \cos^2 x}\,\mathrm{d}x = \frac{\pi^2}{4}}$$

---

## 📝 总结

| 知识点 | 要点 |
|--------|------|
| **变上限积分求导** | $\frac{\mathrm{d}}{\mathrm{d}x}\int_a^x f(t)\mathrm{d}t = f(x)$ |
| **链式法则** | $\frac{\mathrm{d}}{\mathrm{d}x}\int_a^{\varphi(x)}f(t)\mathrm{d}t = f[\varphi(x)]\varphi'(x)$ |
| **N-L 公式** | $\int_a^b f(x)\mathrm{d}x = F(b) - F(a)$ |
| **华里士公式** | $\int_0^{\pi/2}\sin^n x\,\mathrm{d}x$ 的分奇偶计算公式 |
| **对称性** | $\int_0^a f(x)\mathrm{d}x = \int_0^a f(a-x)\mathrm{d}x$ |

> 1. 变上限积分求导时，若被积函数含上限变量，需要**先分离再求导**
> 2. 洛必达法则配合变上限积分求导是高频考点
> 3. 华里士公式**只适用于** $[0, \frac{\pi}{2}]$ 上的 $\sin^n x$ 或 $\cos^n x$
> 4. 定积分换元**必须换限**，这是与不定积分换元的重要区别

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 31：定积分的基本概念]] — 概念
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 33：反常积分]] — 反常积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 34：定积分的应用]] — 应用
