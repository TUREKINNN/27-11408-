---
title: Lecture 37：可降阶方程与高阶线性微分方程
tags: [考研, 数学一, 高等数学, 数学, 微分方程, 可降阶, 高阶线性]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 37：可降阶方程与高阶线性微分方程

## 一、可降阶的高阶微分方程

### 1.1 $y'' = f(x)$ 型

> [!important|purple] 类型一：$y^{(n)} = f(x)$ 型
> 方程右端仅含自变量 $x$，直接**逐次积分**即可。
>
> $$y'' = f(x) \implies y' = \int f(x) \, dx + C_1 \implies y = \iint f(x) \, dx \, dx + C_1 x + C_2$$

#### 例题 1

求 $y'' = xe^x$ 的通解。

**解：**
$$y' = \int xe^x \, dx = xe^x - e^x + C_1 = (x-1)e^x + C_1$$

$$y = \int [(x-1)e^x + C_1] \, dx = (x-1)e^x - e^x + C_1 x + C_2 = (x-2)e^x + C_1 x + C_2$$

#### 例题 2

求 $y''' = \sin x$ 的通解。

**解：**
$$y'' = -\cos x + C_1$$
$$y' = -\sin x + C_1 x + C_2$$
$$y = \cos x + \frac{C_1}{2}x^2 + C_2 x + C_3$$

---

### 1.2 $y'' = f(x, y')$ 型（不显含 $y$）

> [!important|purple] 类型二：$y'' = f(x, y')$ 型
> 方程中不显含因变量 $y$。令 $p = y'$，则 $y'' = p'$，方程降为关于 $p$ 的**一阶方程**：
> $$p' = f(x, p)$$
> 解出 $p = p(x, C_1)$ 后，再积分得 $y$。

#### 例题 3

求 $y'' = \dfrac{y'}{x} + x$ 的通解。

**解：** 令 $p = y'$，$y'' = p'$，方程变为：
$$p' = \frac{p}{x} + x \implies p' - \frac{p}{x} = x$$

这是一阶线性方程。积分因子 $\mu = e^{-\int \frac{1}{x}dx} = e^{-\ln|x|} = \dfrac{1}{|x|}$。

用公式法：$p = e^{\int \frac{1}{x}dx}\left[\int x \cdot e^{-\int \frac{1}{x}dx}dx + C_1\right] = |x|\left[\int \frac{x}{|x|}dx + C_1\right]$

取 $x > 0$：$p = x\left[\int 1 \, dx + C_1\right] = x(x + C_1) = x^2 + C_1 x$。

$$y' = x^2 + C_1 x \implies y = \frac{x^3}{3} + \frac{C_1}{2}x^2 + C_2$$

#### 例题 4

求 $(1 + x^2)y'' = 2xy'$ 满足 $y(0) = 1$，$y'(0) = 3$ 的特解。

**解：** 令 $p = y'$：
$$(1 + x^2)p' = 2xp \implies \frac{dp}{p} = \frac{2x}{1+x^2}dx$$

$$\ln|p| = \ln(1+x^2) + C \implies p = C_1(1+x^2)$$

由 $y'(0) = p(0) = C_1 = 3$，得 $p = 3(1+x^2)$。

$$y = \int 3(1+x^2) \, dx = 3x + x^3 + C_2$$

由 $y(0) = 1$：$C_2 = 1$。

特解：$y = x^3 + 3x + 1$。

---

### 1.3 $y'' = f(y, y')$ 型（不显含 $x$）

> [!important|purple] 类型三：$y'' = f(y, y')$ 型
> 方程中不显含自变量 $x$。令 $p = y'$，将 $y$ 视为自变量：
> $$y'' = \frac{dp}{dx} = \frac{dp}{dy} \cdot \frac{dy}{dx} = p \frac{dp}{dy}$$
>
> 方程降为关于 $p$ 和 $y$ 的一阶方程：
> $$p \frac{dp}{dy} = f(y, p)$$

**注意：** 这里关键是利用链式法则 $y'' = p\dfrac{dp}{dy}$，而不是 $y'' = p'$。

#### 例题 5

求 $yy'' = (y')^2$ 的通解。

**解：** 令 $p = y'$，$y'' = p\dfrac{dp}{dy}$：
$$y \cdot p\frac{dp}{dy} = p^2$$

若 $p \neq 0$：
$$y\frac{dp}{dy} = p \implies \frac{dp}{p} = \frac{dy}{y} \implies \ln|p| = \ln|y| + C \implies p = C_1 y$$

$$y' = C_1 y \implies \frac{dy}{y} = C_1 dx \implies \ln|y| = C_1 x + C_2 \implies y = C_2 e^{C_1 x}$$

若 $p = 0$，则 $y' = 0$，$y = C$（常数解），这也是上面解中 $C_1 = 0$ 的情形。

#### 例题 6

求 $y'' + y = 0$ 的通解。（提示：这是常系数方程，但也可以用可降阶法）

**解：** 令 $p = y'$，$y'' = p\dfrac{dp}{dy}$：
$$p\frac{dp}{dy} + y = 0 \implies p \, dp = -y \, dy \implies \frac{p^2}{2} = -\frac{y^2}{2} + C_1$$

$$p^2 = 2C_1 - y^2 \implies y' = \pm\sqrt{2C_1 - y^2}$$

$$\frac{dy}{\sqrt{2C_1 - y^2}} = \pm dx \implies \arcsin\frac{y}{\sqrt{2C_1}} = \pm x + C_2$$

$$y = \sqrt{2C_1}\sin(\pm x + C_2) = A\sin(x + \varphi)$$

其中 $A = \sqrt{2C_1}$，与 $y = C_1\cos x + C_2\sin x$ 一致。

---

## 二、高阶线性微分方程的一般理论

### 2.1 $n$ 阶线性微分方程

> [!important|purple] 定义：$n$ 阶线性微分方程
> $$y^{(n)} + p_1(x)y^{(n-1)} + \cdots + p_{n-1}(x)y' + p_n(x)y = f(x)$$
> 其中 $p_i(x)$ 和 $f(x)$ 是已知函数。
> - 若 $f(x) \equiv 0$，称为**齐次线性方程**；
> - 若 $f(x) \not\equiv 0$，称为**非齐次线性方程**。

### 2.2 齐次线性方程解的结构

> [!important|blue] 定理：齐次线性方程解的叠加原理
> 设 $y_1(x), y_2(x), \ldots, y_k(x)$ 是齐次方程
> $$y^{(n)} + p_1(x)y^{(n-1)} + \cdots + p_n(x)y = 0$$
> 的解，则它们的**任意线性组合**
> $$y = C_1 y_1(x) + C_2 y_2(x) + \cdots + C_k y_k(x)$$
> 也是该方程的解。

> [!important|blue] 定理：齐次方程通解的结构
> 若 $y_1, y_2, \ldots, y_n$ 是 $n$ 阶齐次线性方程的 $n$ 个**线性无关**的解，则通解为：
> $$y = C_1 y_1 + C_2 y_2 + \cdots + C_n y_n$$

**线性无关的判定：** $y_1, y_2, \ldots, y_n$ 线性无关 $\iff$ Wronsky 行列式
$$W(x) = \begin{vmatrix} y_1 & y_2 & \cdots & y_n \\ y_1' & y_2' & \cdots & y_n' \\ \vdots & \vdots & \ddots & \vdots \\ y_1^{(n-1)} & y_2^{(n-1)} & \cdots & y_n^{(n-1)} \end{vmatrix} \neq 0$$

对于二阶方程：$y_1, y_2$ 线性无关 $\iff \dfrac{y_1}{y_2} \neq$ 常数。

### 2.3 非齐次线性方程解的结构

> [!important|blue] 定理：非齐次方程通解的结构
> 非齐次线性方程的**通解** $=$ 对应齐次方程的**通解** $+$ 非齐次方程的一个**特解**。
>
> 即：若 $Y$ 是对应齐次方程的通解，$y^*$ 是非齐次方程的一个特解，则非齐次方程的通解为：
> $$y = Y + y^*$$

> [!important|blue] 定理：非齐次方程解的差
> 非齐次方程的两个特解之差是对应齐次方程的解。
>
> 即：若 $y_1^*, y_2^*$ 都是非齐次方程的特解，则 $y_1^* - y_2^*$ 是齐次方程的解。

#### 例题 7

已知 $y_1 = e^x$，$y_2 = e^{-x}$，$y_3 = e^{2x}$ 是某三阶齐次线性方程的三个解，验证它们线性无关并写出通解。

**解：** Wronsky 行列式：
$$W = \begin{vmatrix} e^x & e^{-x} & e^{2x} \\ e^x & -e^{-x} & 2e^{2x} \\ e^x & e^{-x} & 4e^{2x} \end{vmatrix} = e^x \cdot e^{-x} \cdot e^{2x} \begin{vmatrix} 1 & 1 & 1 \\ 1 & -1 & 2 \\ 1 & 1 & 4 \end{vmatrix}$$

$$= e^{2x}[1(-4-2) - 1(4-2) + 1(1+1)] = e^{2x}(-6 - 2 + 2) = -6e^{2x} \neq 0$$

线性无关，通解 $y = C_1 e^x + C_2 e^{-x} + C_3 e^{2x}$。

#### 例题 8

已知 $y_1 = x$ 是 $y'' - \dfrac{1}{x}y' + \dfrac{1}{x^2}y = 0$ 的一个解，求通解。

**解：** 设 $y_2 = v(x) \cdot x$（常数变易法/降阶法），代入方程求 $v(x)$。

$y_2' = v'x + v$，$y_2'' = v''x + 2v'$。

代入：
$$v''x + 2v' - \frac{1}{x}(v'x + v) + \frac{1}{x^2}vx = 0$$
$$v''x + 2v' - v' - \frac{v}{x} + \frac{v}{x} = 0$$
$$v''x + v' = 0$$

令 $w = v'$：$w'x + w = 0$ → $\dfrac{dw}{w} = -\dfrac{dx}{x}$ → $w = \dfrac{C}{x}$ → $v = C\ln|x| + D$。

取 $v = \ln|x|$，则 $y_2 = x\ln|x|$。

$\dfrac{y_1}{y_2} = \dfrac{1}{\ln|x|} \neq$ 常数，线性无关。

通解 $y = C_1 x + C_2 x\ln|x|$。

---

## 三、易错点总结

> 1. **$y'' = f(y, y')$ 型中 $y'' = p\dfrac{dp}{dy}$**，不是 $y'' = p'$。这是最常见的错误。
> 2. **可降阶法中注意丢失的解**：如令 $p = 0$ 时可能丢掉常数解。
> 3. **线性无关是通解的必要条件**：$n$ 阶齐次方程需要 $n$ 个线性无关解才能构成通解。
> 4. **非齐次方程的通解 = 齐次通解 + 非齐次特解**：不要遗漏齐次部分。
> 5. **叠加原理仅适用于线性方程**：非线性方程的解不能叠加。
> 6. **常数变易法中 $v(x)$ 的选择**：取最简形式即可，不必包含所有常数。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 36：一阶线性微分方程]] — 一阶
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 38：常系数齐次线性微分方程]] — 齐次
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 39：常系数非齐次线性微分方程]] — 非齐次
