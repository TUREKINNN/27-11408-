---
title: "Lecture 20：函数的微分"
chapter: "02-导数与微分"
tags: [考研, 数学一, 高等数学, 考研数学一, 微分, 一阶微分形式不变性]
difficulty: ★★★
exam_weight: ★★★
created: 2026-06-16
---

# Lecture 20：函数的微分

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★（不是高频考点，但概念重要） |
| **分值分布** | 约 2-4 分（偶尔出现于选择/填空） |
| **题型** | 微分的定义、一阶微分形式不变性、近似计算 |
| **难度** | 基础～中等 |

---

## 一、微分的定义

### 1.1 微分的概念

> 设函数 $y = f(x)$ 在某区间内有定义，$x_0$ 和 $x_0 + \Delta x$ 都在此区间内。若函数的增量
>
> $$\Delta y = f(x_0 + \Delta x) - f(x_0)$$
>
> 可以表示为
>
> $$\boxed{\Delta y = A \cdot \Delta x + o(\Delta x) \quad (\Delta x \to 0)}$$
>
> 其中 $A$ 是与 $\Delta x$ 无关的常数，则称 $f(x)$ 在 $x_0$ 处**可微**，$A \cdot \Delta x$ 为函数在 $x_0$ 处的**微分**，记为
>
> $$dy = A \cdot \Delta x = A \cdot dx$$
>
> 其中 $dx = \Delta x$ 称为**自变量的微分**。

### 1.2 可微与可导的关系

> $$\boxed{f(x) \text{ 在 } x_0 \text{ 处可微} \iff f(x) \text{ 在 } x_0 \text{ 处可导}}$$
>
> 且 $A = f'(x_0)$，即：
>
> $$\boxed{dy = f'(x_0) \, dx}$$

**证明**（可微 $\Rightarrow$ 可导）：

设 $\Delta y = A \cdot \Delta x + o(\Delta x)$，则

$$\frac{\Delta y}{\Delta x} = A + \frac{o(\Delta x)}{\Delta x} \to A \quad (\Delta x \to 0)$$

故 $f'(x_0) = A$ 存在。$\blacksquare$

**证明**（可导 $\Rightarrow$ 可微）：

设 $f'(x_0)$ 存在，令 $\alpha(\Delta x) = \dfrac{\Delta y}{\Delta x} - f'(x_0)$，则 $\alpha(\Delta x) \to 0$（当 $\Delta x \to 0$）。

$$\Delta y = f'(x_0) \cdot \Delta x + \alpha(\Delta x) \cdot \Delta x = f'(x_0) \cdot \Delta x + o(\Delta x)$$

故 $f(x)$ 在 $x_0$ 处可微。$\blacksquare$

### 1.3 微分的几何意义

> 微分 $dy = f'(x_0)dx$ 表示曲线 $y = f(x)$ 在点 $(x_0, f(x_0))$ 处**切线上纵坐标的增量**。
>
> 当 $|\Delta x|$ 很小时，$dy \approx \Delta y$，即用切线段代替曲线段（**以直代曲**）。

---

## 二、一阶微分形式不变性

### 2.1 核心定理

> 无论 $u$ 是**自变量**还是**中间变量**，函数 $y = f(u)$ 的微分总可以写成：
>
> $$\boxed{dy = f'(u) \, du}$$
>
> - 当 $u$ 是自变量时，$dy = f'(u) \, du$（微分定义）
> - 当 $u = g(x)$ 是中间变量时，$dy = f'(u) \cdot g'(x) \, dx = f'(u) \, du$（因为 $du = g'(x)dx$）

**意义**：一阶微分的形式与 $u$ 是自变量还是中间变量**无关**，这就是"形式不变性"。

### 2.2 微分运算法则


| 函数 $y$ | 微分 $dy$ | 函数 $y$ | 微分 $dy$ |
|:---:|:---:|:---:|:---:|
| $C$ | $0$ | $a^x$ | $a^x \ln a \, dx$ |
| $x^n$ | $nx^{n-1}dx$ | $e^x$ | $e^x dx$ |
| $\sin x$ | $\cos x \, dx$ | $\ln x$ | $\dfrac{dx}{x}$ |
| $\cos x$ | $-\sin x \, dx$ | $\log_a x$ | $\dfrac{dx}{x\ln a}$ |
| $\tan x$ | $\sec^2 x \, dx$ | $\arcsin x$ | $\dfrac{dx}{\sqrt{1-x^2}}$ |
| $\cot x$ | $-\csc^2 x \, dx$ | $\arctan x$ | $\dfrac{dx}{1+x^2}$ |

>
> $$d(u \pm v) = du \pm dv$$
>
> $$d(uv) = v \, du + u \, dv$$
>
> $$d\left(\frac{u}{v}\right) = \frac{v \, du - u \, dv}{v^2}$$

---

## 三、微分的应用

### 3.1 近似计算

> 当 $|\Delta x|$ 很小时：
>
> $$\boxed{\Delta y \approx dy = f'(x_0)\Delta x}$$
>
> 即：
>
> $$\boxed{f(x_0 + \Delta x) \approx f(x_0) + f'(x_0)\Delta x}$$

**常用近似公式**（当 $|x|$ 很小时）：

| 近似公式 | 条件 |
|:---:|:---:|
| $\sin x \approx x$ | $|x| \ll 1$ |
| $\tan x \approx x$ | $|x| \ll 1$ |
| $e^x \approx 1 + x$ | $|x| \ll 1$ |
| $\ln(1+x) \approx x$ | $|x| \ll 1$ |
| $(1+x)^\alpha \approx 1 + \alpha x$ | $|x| \ll 1$ |
| $\dfrac{1}{1+x} \approx 1 - x$ | $|x| \ll 1$ |

### 3.2 误差估计

设 $y = f(x)$，若 $x$ 的绝对误差为 $|\Delta x| \le \delta_x$，则：

- $y$ 的绝对误差：$|\Delta y| \approx |dy| = |f'(x)||\Delta x| \le |f'(x)|\delta_x$
- $y$ 的相对误差：$\dfrac{|\Delta y|}{|y|} \approx \dfrac{|f'(x)|}{|f(x)|}\delta_x$

---

## 四、经典例题

### 【例1】求微分

**题目**：设 $y = e^{-x}\sin(2x)$，求 $dy$。

**解**：

$$dy = d(e^{-x}\sin 2x) = \sin 2x \cdot d(e^{-x}) + e^{-x} \cdot d(\sin 2x)$$

$$= \sin 2x \cdot (-e^{-x})dx + e^{-x} \cdot 2\cos 2x \, dx$$

$$= e^{-x}(2\cos 2x - \sin 2x)dx$$

### 【例2】利用微分形式不变性求导

**题目**：设 $y = \ln\sin\sqrt{x}$，求 $dy$ 和 $y'$。

**解**：

利用一阶微分形式不变性，逐层使用微分公式：

$$dy = \frac{d(\sin\sqrt{x})}{\sin\sqrt{x}} = \frac{\cos\sqrt{x} \cdot d(\sqrt{x})}{\sin\sqrt{x}} = \frac{\cos\sqrt{x}}{\sin\sqrt{x}} \cdot \frac{dx}{2\sqrt{x}}$$

$$= \frac{\cot\sqrt{x}}{2\sqrt{x}}dx$$

故 $y' = \dfrac{\cot\sqrt{x}}{2\sqrt{x}}$

> **技巧**：利用微分形式不变性，像"剥洋葱"一样逐层求微分，比用链式法则更直观。

### 【例3】近似计算

**题目**：利用微分近似计算 $\sqrt[3]{998}$ 的近似值。

**解**：

设 $f(x) = \sqrt[3]{x} = x^{1/3}$，取 $x_0 = 1000$，$\Delta x = -2$

$$f'(x) = \frac{1}{3}x^{-2/3}$$

$$f(998) \approx f(1000) + f'(1000) \times (-2) = 10 + \frac{1}{3 \times 100} \times (-2) = 10 - \frac{1}{150} \approx 9.9933$$

（精确值 $\sqrt[3]{998} \approx 9.99333...$，近似效果很好）

### 【例4】微分形式不变性的应用

**题目**：设 $y = f(e^x)e^{f(x)}$，其中 $f$ 可微，求 $dy$。

**解**：

$$dy = d[f(e^x)] \cdot e^{f(x)} + f(e^x) \cdot d[e^{f(x)}]$$

$$= f'(e^x) \cdot e^x \cdot e^{f(x)} \, dx + f(e^x) \cdot e^{f(x)} \cdot f'(x) \, dx$$

$$= e^{f(x)}\left[e^x f'(e^x) + f(e^x)f'(x)\right]dx$$

### 【例5】由微分方程求函数

**题目**：设 $y = f(x)$ 满足 $dy = 2x \, dx + x \, dy$，且 $f(0) = 1$，求 $f(x)$。

**解**：

$dy - x \, dy = 2x \, dx$

$(1-x)dy = 2x \, dx$

$dy = \dfrac{2x}{1-x}dx$

积分：$y = \int\dfrac{2x}{1-x}dx = \int\left(-2 + \dfrac{2}{1-x}\right)dx = -2x - 2\ln|1-x| + C$

由 $f(0) = 1$ 得 $C = 1$。

$$\boxed{f(x) = 1 - 2x - 2\ln|1-x|}$$

---

## 五、考研真题精选

### 【真题1】（2013年数一·选择）

**题目**：设函数 $y = f(x)$ 由方程 $\cos(xy) + lny - x = 1$ 确定，则 $\lim\limits_{n \to \infty}n\left[f\left(\dfrac{2}{n}\right) - 1\right] = $ ______。

**解**：

当 $x = 0$ 时，$\cos 0 + \ln y - 0 = 1$，$\ln y = 0$，$y = 1$，即 $f(0) = 1$。

$$\lim_{n \to \infty}n\left[f\left(\frac{2}{n}\right) - 1\right] = \lim_{n \to \infty}\frac{f\left(\frac{2}{n}\right) - f(0)}{\frac{1}{n}} = 2\lim_{n \to \infty}\frac{f\left(\frac{2}{n}\right) - f(0)}{\frac{2}{n}} = 2f'(0)$$

对原方程两边对 $x$ 求导：

$-\sin(xy) \cdot (y + xy') + \frac{y'}{y} - 1 = 0$

在 $x = 0, y = 1$ 处：$0 + y'(0) - 1 = 0$，$f'(0) = 1$。

故 $\lim\limits_{n \to \infty}n\left[f\left(\dfrac{2}{n}\right) - 1\right] = 2$

**答案**：$2$

---

## 📝 本节要点总结

| 要点 | 内容 |
|------|------|
| 微分定义 | $\Delta y = A\Delta x + o(\Delta x)$，$A = f'(x_0)$ |
| 可微与可导 | 可微 $\iff$ 可导（一元函数中等价） |
| 微分公式 | $dy = f'(x)dx$ |
| 形式不变性 | $dy = f'(u)du$，无论 $u$ 是自变量还是中间变量 |
| 近似计算 | $f(x_0+\Delta x) \approx f(x_0) + f'(x_0)\Delta x$ |

> 一阶微分形式不变性在后续的**不定积分换元法**中有重要应用，务必熟练掌握。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 16：导数基本概念]] — 导数概念
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 17：导数求导法则]] — 求导法则
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/03-微分中值定理与导数应用/Lecture 22：洛必达法则]] — 洛必达
