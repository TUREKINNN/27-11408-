---
title: "Lecture 36：一阶线性微分方程"
chapter: "06-微分方程"
tags: [考研, 数学一, 高等数学, 考研数学一, 可分离变量, 齐次方程, 一阶线性方程, 伯努利方程]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 36：一阶线性微分方程

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，解答题高频） |
| **分值分布** | 约 10-12 分（解答题 1 题） |
| **题型** | 求解一阶微分方程、与几何/物理问题结合 |
| **难度** | 中等（公式要熟，判断类型是关键） |

---

## 一、可分离变量的微分方程

> 形如：
>
> $$\frac{\mathrm{d}y}{\mathrm{d}x} = f(x)g(y) \quad \text{或} \quad M_1(x)M_2(y)\mathrm{d}x = N_1(x)N_2(y)\mathrm{d}y$$
>
> 的方程称为**可分离变量的微分方程**。

**解法**：

$$\frac{\mathrm{d}y}{g(y)} = f(x)\,\mathrm{d}x$$

两边积分：

$$\int\frac{\mathrm{d}y}{g(y)} = \int f(x)\,\mathrm{d}x + C$$


**示例**：$y' = 2xy$

$$\frac{\mathrm{d}y}{y} = 2x\,\mathrm{d}x$$

$$\ln|y| = x^2 + C_1$$

$$y = Ce^{x^2} \quad (C = \pm e^{C_1}，\text{包含 } C = 0 \text{ 即 } y = 0)$$

---

## 二、齐次微分方程

> 形如：
>
> $$\frac{\mathrm{d}y}{\mathrm{d}x} = \varphi\left(\frac{y}{x}\right)$$
>
> 的方程称为**齐次微分方程**。

**解法**：令 $u = \dfrac{y}{x}$，即 $y = ux$，则：

$$\frac{\mathrm{d}y}{\mathrm{d}x} = u + x\frac{\mathrm{d}u}{\mathrm{d}x}$$

代入原方程：

$$u + x\frac{\mathrm{d}u}{\mathrm{d}x} = \varphi(u)$$

$$x\frac{\mathrm{d}u}{\mathrm{d}x} = \varphi(u) - u$$

分离变量：

$$\frac{\mathrm{d}u}{\varphi(u) - u} = \frac{\mathrm{d}x}{x}$$

积分后回代 $u = \dfrac{y}{x}$。

**示例**：$xy' = y + x\sin\dfrac{y}{x}$

令 $u = \frac{y}{x}$：$u + xu' = u + \sin u$

$xu' = \sin u$，分离：$\frac{\mathrm{d}u}{\sin u} = \frac{\mathrm{d}x}{x}$

$\ln|\csc u - \cot u| = \ln|x| + C_1$

回代 $u = \frac{y}{x}$ 即得解。

---

## 三、一阶线性微分方程

> 形如：
>
> $$\boxed{y' + P(x)y = Q(x)}$$
>
> 的方程称为**一阶线性微分方程**。
>
> - 当 $Q(x) \equiv 0$ 时，称为**齐次**的：$y' + P(x)y = 0$
> - 当 $Q(x) \not\equiv 0$ 时，称为**非齐次**的

### 齐次方程的解

$$y' + P(x)y = 0$$

分离变量：$\frac{\mathrm{d}y}{y} = -P(x)\mathrm{d}x$

$$\boxed{y = Ce^{-\int P(x)\mathrm{d}x}}$$

### 非齐次方程的通解（常数变易法）

>
> $$\boxed{y = e^{-\int P(x)\mathrm{d}x}\left[\int Q(x)e^{\int P(x)\mathrm{d}x}\,\mathrm{d}x + C\right]}$$
>
> **记忆口诀**："齐次解 × $\left[\int \frac{Q}{y_0}\mathrm{d}x + C\right]$"

**推导（常数变易法）**：

设齐次方程的解为 $y = Ce^{-\int P\mathrm{d}x}$，将常数 $C$ 替换为待定函数 $C(x)$：

$$y = C(x)e^{-\int P\mathrm{d}x}$$

代入原方程：$C'(x)e^{-\int P\mathrm{d}x} = Q(x)$

$$C'(x) = Q(x)e^{\int P\mathrm{d}x}$$

$$C(x) = \int Q(x)e^{\int P\mathrm{d}x}\,\mathrm{d}x + C$$

代回即得通解公式。

---

## 四、伯努利方程

> 形如：
>
> $$y' + P(x)y = Q(x)y^n \quad (n \ne 0, 1)$$
>
> 的方程称为**伯努利方程**。

**解法**：两边除以 $y^n$：

$$y^{-n}y' + P(x)y^{1-n} = Q(x)$$

令 $z = y^{1-n}$，则 $z' = (1-n)y^{-n}y'$，代入得：

$$\frac{z'}{1-n} + P(x)z = Q(x)$$

$$z' + (1-n)P(x)z = (1-n)Q(x)$$

这是关于 $z$ 的一阶线性方程，用通解公式求解后回代 $z = y^{1-n}$。

---

## 五、一阶方程求解流程

>
> ```
> 1. 能否分离变量？ → 可分离变量方程
> 2. 是否形如 y' = φ(y/x)？ → 齐次方程，令 u = y/x
> 3. 是否形如 y' + P(x)y = Q(x)？ → 一阶线性方程，用通解公式
> 4. 是否形如 y' + P(x)y = Q(x)y^n？ → 伯努利方程，令 z = y^(1-n)
> 5. 以上都不是？ → 检查是否为全微分方程或其他方法
> ```

---

## 六、典型例题

### 例 1：可分离变量

**题目**：求 $y' = \dfrac{1 + y^2}{xy(1 + x^2)}$

**解**：

$$\frac{y\,\mathrm{d}y}{1 + y^2} = \frac{\mathrm{d}x}{x(1 + x^2)} = \left(\frac{1}{x} - \frac{x}{1 + x^2}\right)\mathrm{d}x$$

$$\frac{1}{2}\ln(1 + y^2) = \ln|x| - \frac{1}{2}\ln(1 + x^2) + C_1$$

$$\ln(1 + y^2) = 2\ln|x| - \ln(1 + x^2) + C_2$$

$$(1 + y^2)(1 + x^2) = Cx^2$$

$$\boxed{(1 + y^2)(1 + x^2) = Cx^2}$$

---

### 例 2：齐次方程

**题目**：求 $y' = \dfrac{y}{x} + \tan\dfrac{y}{x}$，$y(1) = \dfrac{\pi}{2}$

**解**：

令 $u = \frac{y}{x}$：$u + xu' = u + \tan u$

$$xu' = \tan u$$

$$\frac{\cos u}{\sin u}\mathrm{d}u = \frac{\mathrm{d}x}{x}$$

$$\ln|\sin u| = \ln|x| + C_1$$

$$\sin u = Cx$$

回代：$\sin\dfrac{y}{x} = Cx$

由 $y(1) = \frac{\pi}{2}$：$\sin\frac{\pi}{2} = C$，$C = 1$

$$\boxed{\sin\frac{y}{x} = x}$$

---

### 例 3：一阶线性方程

**题目**：求 $y' + \dfrac{y}{x} = x^2$

**解**：

$P(x) = \frac{1}{x}$，$Q(x) = x^2$

$\int P(x)\mathrm{d}x = \ln|x|$

通解公式：

$$y = e^{-\ln|x|}\left[\int x^2 e^{\ln|x|}\,\mathrm{d}x + C\right] = \frac{1}{x}\left[\int x^3\,\mathrm{d}x + C\right]$$

$$= \frac{1}{x}\left(\frac{x^4}{4} + C\right) = \frac{x^3}{4} + \frac{C}{x}$$

$$\boxed{y = \frac{x^3}{4} + \frac{C}{x}}$$

---

### 例 4：伯努利方程

**题目**：求 $y' + \dfrac{y}{x} = y^2\ln x$

**解**：

这是伯努利方程（$n = 2$），两边除以 $y^2$：

$$y^{-2}y' + \frac{1}{x}y^{-1} = \ln x$$

令 $z = y^{-1}$，$z' = -y^{-2}y'$：

$$-z' + \frac{z}{x} = \ln x \quad \Rightarrow \quad z' - \frac{z}{x} = -\ln x$$

这是一阶线性方程，$P(x) = -\frac{1}{x}$，$Q(x) = -\ln x$

$$z = e^{\ln|x|}\left[\int(-\ln x)e^{-\ln|x|}\,\mathrm{d}x + C\right] = x\left[-\int\frac{\ln x}{x}\,\mathrm{d}x + C\right]$$

$$= x\left[-\frac{(\ln x)^2}{2} + C\right] = Cx - \frac{x(\ln x)^2}{2}$$

回代 $z = \frac{1}{y}$：

$$\frac{1}{y} = Cx - \frac{x(\ln x)^2}{2}$$

$$\boxed{y = \frac{1}{Cx - \frac{x(\ln x)^2}{2}}}$$

---

### 例 5：综合应用

**题目**：设曲线过点 $(1, 1)$，且曲线上任一点处的切线在 $y$ 轴上的截距等于该点横坐标的立方，求曲线方程。

**解**：

设曲线 $y = f(x)$，点 $(x_0, y_0)$ 处切线方程：

$$Y - y_0 = y'(X - x_0)$$

$y$ 轴截距（$X = 0$）：$Y = y_0 - x_0 y'$

由题意：$y_0 - x_0 y' = x_0^3$

$$y' - \frac{y}{x} = -x^2$$

$P(x) = -\frac{1}{x}$，$Q(x) = -x^2$

$$y = e^{\ln|x|}\left[\int(-x^2)e^{-\ln|x|}\,\mathrm{d}x + C\right] = x\left[-\int x\,\mathrm{d}x + C\right] = x\left(-\frac{x^2}{2} + C\right)$$

$$y = Cx - \frac{x^3}{2}$$

由 $y(1) = 1$：$C - \frac{1}{2} = 1$，$C = \frac{3}{2}$

$$\boxed{y = \frac{3x}{2} - \frac{x^3}{2}}$$

---

## 📝 总结

| 方程类型 | 标准形式 | 解法 |
|----------|----------|------|
| **可分离变量** | $y' = f(x)g(y)$ | 分离两边积分 |
| **齐次方程** | $y' = \varphi(y/x)$ | 令 $u = y/x$ |
| **一阶线性** | $y' + P(x)y = Q(x)$ | 通解公式（常数变易法） |
| **伯努利方程** | $y' + P(x)y = Q(x)y^n$ | 令 $z = y^{1-n}$ 化为线性 |

> 1. 分离变量时**检查常数解**（$g(y) = 0$ 的根）
> 2. 齐次方程令 $u = y/x$ 后别忘 $y' = u + xu'$
> 3. 一阶线性通解公式中**指数的符号**容易搞反
> 4. 伯努利方程中 $n = 0, 1$ 时不是伯努利方程
> 5. 通解公式中的积分是**不定积分**（不带上下限），加 $C$

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 35：微分方程的基本概念]] — 基本概念
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 37：可降阶方程与高阶线性微分方程]] — 高阶
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/06-微分方程/Lecture 38：常系数齐次线性微分方程]] — 齐次
