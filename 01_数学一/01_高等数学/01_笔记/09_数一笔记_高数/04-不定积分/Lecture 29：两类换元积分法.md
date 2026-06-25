---
title: "Lecture 29：两类换元积分法"
chapter: "04-不定积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 换元积分法, 凑微分, 三角换元]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 29：两类换元积分法

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算题核心方法） |
| **分值分布** | 约 5-10 分（出现在不定积分、定积分计算中） |
| **题型** | 凑微分法求积分、三角换元去根号 |
| **难度** | 中等偏难（技巧性强，需要大量练习） |

---

## 一、第一类换元法（凑微分法）

> 若 $\displaystyle\int f(u)\,\mathrm{d}u = F(u) + C$，且 $u = \varphi(x)$ 可微，则：
>
> $$\boxed{\int f[\varphi(x)]\,\varphi'(x)\,\mathrm{d}x = \int f[\varphi(x)]\,\mathrm{d}\varphi(x) = F[\varphi(x)] + C}$$
>
> **核心思想**：把被积表达式中的一部分凑成某个函数的微分 $\mathrm{d}\varphi(x)$。

### 5 种常用凑微分形式


#### 形式 1：$\int f(ax + b)\,\mathrm{d}x$ 型

$$\int f(ax + b)\,\mathrm{d}x = \frac{1}{a}\int f(ax + b)\,\mathrm{d}(ax + b) = \frac{1}{a}F(ax + b) + C$$

**示例**：$\displaystyle\int e^{2x+3}\,\mathrm{d}x = \frac{1}{2}\int e^{2x+3}\,\mathrm{d}(2x+3) = \frac{1}{2}e^{2x+3} + C$

#### 形式 2：$\int x^{n-1}f(x^n)\,\mathrm{d}x$ 型

$$\int x^{n-1}f(x^n)\,\mathrm{d}x = \frac{1}{n}\int f(x^n)\,\mathrm{d}(x^n) = \frac{1}{n}F(x^n) + C$$

**示例**：$\displaystyle\int x\cos x^2\,\mathrm{d}x = \frac{1}{2}\int \cos x^2\,\mathrm{d}(x^2) = \frac{1}{2}\sin x^2 + C$

#### 形式 3：$\int f(\ln x)\cdot\frac{1}{x}\,\mathrm{d}x$ 型

$$\int f(\ln x)\cdot\frac{1}{x}\,\mathrm{d}x = \int f(\ln x)\,\mathrm{d}(\ln x) = F(\ln x) + C$$

**示例**：$\displaystyle\int \frac{1}{x\ln x}\,\mathrm{d}x = \int \frac{1}{\ln x}\,\mathrm{d}(\ln x) = \ln|\ln x| + C$

#### 形式 4：$\int f(e^x)\cdot e^x\,\mathrm{d}x$ 型

$$\int f(e^x)\cdot e^x\,\mathrm{d}x = \int f(e^x)\,\mathrm{d}(e^x) = F(e^x) + C$$

**示例**：$\displaystyle\int \frac{e^x}{1 + e^x}\,\mathrm{d}x = \int \frac{1}{1 + e^x}\,\mathrm{d}(e^x) = \ln(1 + e^x) + C$

#### 形式 5：$\int f(\sin x)\cos x\,\mathrm{d}x$ / $\int f(\cos x)\sin x\,\mathrm{d}x$ 型

$$\int f(\sin x)\cos x\,\mathrm{d}x = \int f(\sin x)\,\mathrm{d}(\sin x) = F(\sin x) + C$$

$$\int f(\cos x)\sin x\,\mathrm{d}x = -\int f(\cos x)\,\mathrm{d}(\cos x) = -F(\cos x) + C$$

**示例**：$\displaystyle\int \sin^2 x\cos x\,\mathrm{d}x = \int \sin^2 x\,\mathrm{d}(\sin x) = \frac{\sin^3 x}{3} + C$

---

> **记住常用微分关系**：
> - $\cos x\,\mathrm{d}x = \mathrm{d}(\sin x)$
> - $\sin x\,\mathrm{d}x = -\mathrm{d}(\cos x)$
> - $\sec^2 x\,\mathrm{d}x = \mathrm{d}(\tan x)$
> - $\csc^2 x\,\mathrm{d}x = -\mathrm{d}(\cot x)$
> - $\frac{1}{x}\,\mathrm{d}x = \mathrm{d}(\ln x)$
> - $e^x\,\mathrm{d}x = \mathrm{d}(e^x)$
> - $\frac{1}{\sqrt{1-x^2}}\,\mathrm{d}x = \mathrm{d}(\arcsin x)$
> - $\frac{1}{1+x^2}\,\mathrm{d}x = \mathrm{d}(\arctan x)$

---

## 二、第二类换元法（变量替换法）

> 设 $x = \varphi(t)$ 单调、可微，且 $\varphi'(t) \ne 0$，则：
>
> $$\boxed{\int f(x)\,\mathrm{d}x = \int f[\varphi(t)]\,\varphi'(t)\,\mathrm{d}t \bigg|_{t = \varphi^{-1}(x)}}$$
>
> **核心思想**：令 $x = \varphi(t)$，把复杂积分转化为简单积分，最后回代。

### 3 种常用三角换元形式


#### 形式 1：$\sqrt{a^2 - x^2}$ 型

> 令 $x = a\sin t$（$t \in [-\frac{\pi}{2}, \frac{\pi}{2}]$），则：
>
> $$\sqrt{a^2 - x^2} = \sqrt{a^2 - a^2\sin^2 t} = a\cos t$$
>
> $$\mathrm{d}x = a\cos t\,\mathrm{d}t$$

**适用场景**：被积函数含 $\sqrt{a^2 - x^2}$

**示例**：$\displaystyle\int \frac{\mathrm{d}x}{\sqrt{a^2 - x^2}}$

令 $x = a\sin t$，则：

$$\int \frac{a\cos t\,\mathrm{d}t}{a\cos t} = \int \mathrm{d}t = t + C = \arcsin\frac{x}{a} + C$$

#### 形式 2：$\sqrt{a^2 + x^2}$ 型

> 令 $x = a\tan t$（$t \in (-\frac{\pi}{2}, \frac{\pi}{2})$），则：
>
> $$\sqrt{a^2 + x^2} = \sqrt{a^2 + a^2\tan^2 t} = a\sec t$$
>
> $$\mathrm{d}x = a\sec^2 t\,\mathrm{d}t$$

**适用场景**：被积函数含 $\sqrt{a^2 + x^2}$

**示例**：$\displaystyle\int \frac{\mathrm{d}x}{\sqrt{a^2 + x^2}}$

令 $x = a\tan t$，则：

$$\int \frac{a\sec^2 t\,\mathrm{d}t}{a\sec t} = \int \sec t\,\mathrm{d}t = \ln|\sec t + \tan t| + C$$

回代：$\sec t = \dfrac{\sqrt{a^2 + x^2}}{a}$，$\tan t = \dfrac{x}{a}$

$$= \ln\left|\frac{x + \sqrt{a^2 + x^2}}{a}\right| + C = \ln|x + \sqrt{a^2 + x^2}| + C'$$

#### 形式 3：$\sqrt{x^2 - a^2}$ 型

> 令 $x = a\sec t$（$t \in [0, \frac{\pi}{2}) \cup (\frac{\pi}{2}, \pi]$），则：
>
> $$\sqrt{x^2 - a^2} = \sqrt{a^2\sec^2 t - a^2} = a\tan t$$
>
> $$\mathrm{d}x = a\sec t\tan t\,\mathrm{d}t$$

**适用场景**：被积函数含 $\sqrt{x^2 - a^2}$

---

### 其他常用第二类换元

**倒代换** $x = \frac{1}{t}$：

适用于被积函数分母次数高于分子次数较高的情况，如 $\displaystyle\int \frac{\mathrm{d}x}{x\sqrt{1+x^2}}$

**根号代换** $t = \sqrt[n]{g(x)}$：

适用于含根号的有理式，如 $\displaystyle\int \frac{\mathrm{d}x}{1 + \sqrt[3]{x}}$，令 $t = \sqrt[3]{x}$，即 $x = t^3$

---

## 三、三角换元总结表

| 被积函数含 | 换元 | 替换结果 | 适用公式 |
|------------|------|----------|----------|
| $\sqrt{a^2 - x^2}$ | $x = a\sin t$ | $a\cos t$ | 勾股定理 $\sin^2 + \cos^2 = 1$ |
| $\sqrt{a^2 + x^2}$ | $x = a\tan t$ | $a\sec t$ | $1 + \tan^2 = \sec^2$ |
| $\sqrt{x^2 - a^2}$ | $x = a\sec t$ | $a\tan t$ | $\sec^2 - 1 = \tan^2$ |

> 换元后画出对应的直角三角形，利用三角函数定义直接读出各边关系，避免记忆繁琐的反三角公式。

---

## 四、典型例题

### 例 1：凑微分法（指数型）

**题目**：求 $\displaystyle\int \frac{e^{3x}}{1 + e^{3x}}\,\mathrm{d}x$

**解**：

$$\int \frac{e^{3x}}{1 + e^{3x}}\,\mathrm{d}x = \frac{1}{3}\int \frac{1}{1 + e^{3x}}\,\mathrm{d}(e^{3x}) = \frac{1}{3}\ln(1 + e^{3x}) + C$$

$$\boxed{\int \frac{e^{3x}}{1 + e^{3x}}\,\mathrm{d}x = \frac{1}{3}\ln(1 + e^{3x}) + C}$$

---

### 例 2：凑微分法（三角型）

**题目**：求 $\displaystyle\int \frac{\sin x\cos x}{1 + \sin^4 x}\,\mathrm{d}x$

**解**：

注意到 $\sin x\cos x\,\mathrm{d}x = \sin x\,\mathrm{d}(\sin x) = \frac{1}{2}\mathrm{d}(\sin^2 x)$

$$\int \frac{\sin x\cos x}{1 + \sin^4 x}\,\mathrm{d}x = \frac{1}{2}\int \frac{\mathrm{d}(\sin^2 x)}{1 + (\sin^2 x)^2} = \frac{1}{2}\arctan(\sin^2 x) + C$$

$$\boxed{\int \frac{\sin x\cos x}{1 + \sin^4 x}\,\mathrm{d}x = \frac{1}{2}\arctan(\sin^2 x) + C}$$

---

### 例 3：三角换元（$\sqrt{1 - x^2}$ 型）

**题目**：求 $\displaystyle\int \sqrt{1 - x^2}\,\mathrm{d}x$

**解**：

令 $x = \sin t$（$t \in [-\frac{\pi}{2}, \frac{\pi}{2}]$），$\mathrm{d}x = \cos t\,\mathrm{d}t$

$$\int \sqrt{1 - x^2}\,\mathrm{d}x = \int \cos t \cdot \cos t\,\mathrm{d}t = \int \cos^2 t\,\mathrm{d}t$$

$$= \int \frac{1 + \cos 2t}{2}\,\mathrm{d}t = \frac{t}{2} + \frac{\sin 2t}{4} + C = \frac{t}{2} + \frac{\sin t\cos t}{2} + C$$

回代：$t = \arcsin x$，$\sin t = x$，$\cos t = \sqrt{1 - x^2}$

$$= \frac{\arcsin x}{2} + \frac{x\sqrt{1 - x^2}}{2} + C$$

$$\boxed{\int \sqrt{1 - x^2}\,\mathrm{d}x = \frac{\arcsin x}{2} + \frac{x\sqrt{1 - x^2}}{2} + C}$$

---

### 例 4：三角换元（$\sqrt{x^2 + 1}$ 型）

**题目**：求 $\displaystyle\int \frac{\mathrm{d}x}{x^2\sqrt{x^2 + 1}}$

**解**：

令 $x = \tan t$，$\mathrm{d}x = \sec^2 t\,\mathrm{d}t$，$\sqrt{x^2 + 1} = \sec t$

$$\int \frac{\sec^2 t\,\mathrm{d}t}{\tan^2 t \cdot \sec t} = \int \frac{\sec t}{\tan^2 t}\,\mathrm{d}t = \int \frac{\cos t}{\sin^2 t}\,\mathrm{d}t$$

$$= \int \frac{\mathrm{d}(\sin t)}{\sin^2 t} = -\frac{1}{\sin t} + C$$

回代：$\sin t = \dfrac{x}{\sqrt{x^2 + 1}}$

$$= -\frac{\sqrt{x^2 + 1}}{x} + C$$

$$\boxed{\int \frac{\mathrm{d}x}{x^2\sqrt{x^2 + 1}} = -\frac{\sqrt{x^2 + 1}}{x} + C}$$

---

### 例 5：根号代换

**题目**：求 $\displaystyle\int \frac{\mathrm{d}x}{1 + \sqrt{x}}$

**解**：

令 $t = \sqrt{x}$，$x = t^2$，$\mathrm{d}x = 2t\,\mathrm{d}t$

$$\int \frac{2t\,\mathrm{d}t}{1 + t} = 2\int \frac{t}{1 + t}\,\mathrm{d}t = 2\int \left(1 - \frac{1}{1 + t}\right)\mathrm{d}t$$

$$= 2t - 2\ln|1 + t| + C = 2\sqrt{x} - 2\ln(1 + \sqrt{x}) + C$$

$$\boxed{\int \frac{\mathrm{d}x}{1 + \sqrt{x}} = 2\sqrt{x} - 2\ln(1 + \sqrt{x}) + C}$$

---

## 📝 总结

| 方法 | 核心思想 | 关键步骤 |
|------|----------|----------|
| **第一类换元（凑微分）** | $f[\varphi(x)]\varphi'(x)\mathrm{d}x = f(u)\mathrm{d}u$ | 识别被积函数中的复合结构 |
| **第二类换元（变量替换）** | $x = \varphi(t)$，化繁为简 | 选择合适的替换函数 |
| **三角换元** | 利用三角恒等式去根号 | 根据根号形式选择 $\sin/\tan/\sec$ |

> 1. 凑微分时**别忘了系数调整**：$\mathrm{d}(2x) = 2\mathrm{d}x$，需要乘以 $\frac{1}{2}$ 补偿
> 2. 三角换元回代时**画直角三角形**，不要死记公式
> 3. 三角换元要注意 $t$ 的**取值范围**，确保函数单调
> 4. 定积分使用第二类换元时，**换上下限**（换元必换限）

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 28：不定积分]] — 不定积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/04-不定积分/Lecture 30：分部积分法]] — 分部积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/公式合集]] — 积分公式
