---
title: "Lecture 19：隐函数与参数方程求导"
chapter: "02-导数与微分"
tags: [考研, 数学一, 高等数学, 考研数学一, 隐函数求导, 参数方程求导]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 19：隐函数与参数方程求导

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（几乎每年必考） |
| **分值分布** | 约 4-10 分（选择/填空/解答均涉及） |
| **题型** | 隐函数求导、参数方程求二阶导、极坐标下的导数 |
| **难度** | 中等 |

---

## 一、隐函数求导

### 1.1 隐函数的概念

> 由方程 $F(x, y) = 0$ 确定的函数关系 $y = y(x)$，称为**隐函数**。
>
> 隐函数可能无法显式地解出 $y = f(x)$，但仍可对其求导。

### 1.2 隐函数求导方法

> 1. 方程 $F(x, y) = 0$ **两边同时对 $x$ 求导**
> 2. 求导时注意 $y$ 是 $x$ 的函数，即 $y$ 视为中间变量，对含 $y$ 的项要使用**链式法则**
> 3. 求导后得到一个关于 $x, y, y'$ 的方程，**解出 $y'$**

### 1.3 示例

**例1**：$x^2 + y^2 = 1$，求 $y'$。

两边对 $x$ 求导：$2x + 2yy' = 0$

解出：$y' = -\dfrac{x}{y}$

**例2**：$e^y + xy = e$，求 $y'\big|_{x=0}$。

两边对 $x$ 求导：$e^y \cdot y' + y + xy' = 0$

$(e^y + x)y' = -y$

$y' = -\dfrac{y}{e^y + x}$

当 $x = 0$ 时，代入原方程 $e^y = e$，得 $y = 1$。

$$y'\bigg|_{x=0} = -\frac{1}{e^1 + 0} = -\frac{1}{e}$$

### 1.4 隐函数的二阶导数

> 方法一：对一阶导数的结果再对 $x$ 求导
>
> 方法二：对求导后的方程再对 $x$ 求导

**示例**：$x^2 + y^2 = 1$，求 $y''$。

由 $2x + 2yy' = 0$ 得 $y' = -\dfrac{x}{y}$

再求导：$2 + 2(y')^2 + 2yy'' = 0$

$$y'' = -\frac{1 + (y')^2}{y} = -\frac{1 + \frac{x^2}{y^2}}{y} = -\frac{y^2 + x^2}{y^3} = -\frac{1}{y^3}$$

> **注意**：最后一步利用了 $x^2 + y^2 = 1$ 的条件。

---

## 二、参数方程求导

### 2.1 参数方程的一阶导数

> 设参数方程 $\begin{cases} x = \varphi(t) \\ y = \psi(t) \end{cases}$，其中 $\varphi(t)$、$\psi(t)$ 可导且 $\varphi'(t) \ne 0$，则：
>
> $$\boxed{\frac{dy}{dx} = \frac{\dfrac{dy}{dt}}{\dfrac{dx}{dt}} = \frac{\psi'(t)}{\varphi'(t)}}$$

**记忆**：参数方程求导 = $y$ 对参数的导数 ÷ $x$ 对参数的导数

### 2.2 参数方程的二阶导数

> $$\frac{d^2y}{dx^2} = \frac{\dfrac{d}{dt}\left(\dfrac{dy}{dx}\right)}{\dfrac{dx}{dt}} = \frac{\dfrac{d}{dt}\left(\dfrac{\psi'(t)}{\varphi'(t)}\right)}{\varphi'(t)}$$
>
> $$= \boxed{\frac{\psi''(t)\varphi'(t) - \psi'(t)\varphi''(t)}{[\varphi'(t)]^3}}$$

> 参数方程的二阶导数 **不是** $\dfrac{\psi''(t)}{\varphi''(t)}$！
>
> 必须对 $\dfrac{dy}{dx}$ 关于 $t$ 求导后，再除以 $\dfrac{dx}{dt}$。

### 2.3 参数方程求导的步骤

1. 求 $\dfrac{dx}{dt} = \varphi'(t)$，$\dfrac{dy}{dt} = \psi'(t)$
2. 一阶导：$\dfrac{dy}{dx} = \dfrac{\psi'(t)}{\varphi'(t)}$
3. 二阶导：对 $\dfrac{dy}{dx}$ 关于 $t$ 求商，再除以 $\varphi'(t)$
4. 代入具体 $t$ 值计算

---

## 三、极坐标下的导数

### 3.1 极坐标转化为参数方程

> 极坐标方程 $r = r(\theta)$ 可化为参数方程：
>
> $$\begin{cases} x = r(\theta)\cos\theta \\ y = r(\theta)\sin\theta \end{cases}$$
>
> 则：
>
> $$\frac{dy}{dx} = \frac{y'(\theta)}{x'(\theta)} = \frac{r'(\theta)\sin\theta + r(\theta)\cos\theta}{r'(\theta)\cos\theta - r(\theta)\sin\theta}$$

---

## 四、经典例题

### 【例1】隐函数求导

**题目**：设 $e^y + xy - e = 0$，求 $y'$ 和 $y''$。

**解**：

两边对 $x$ 求导：$e^y y' + y + xy' = 0$

$$y' = -\frac{y}{e^y + x} \tag{1}$$

再对 $x$ 求导（对 $(e^y + x)y' = -y$ 两边求导）：

$e^y(y')^2 + (e^y + x)y'' + 2y' = -y'$（注：实际上从 $(e^y+x)y'=-y$ 两边求导）

$(e^y y' + 1)y' + (e^y + x)y'' = -y'$

$e^y(y')^2 + y' + (e^y + x)y'' = -y'$

$y'' = \frac{-2y' - e^y(y')^2}{e^y + x}$

代入 $(1)$ 式中的 $y'$：

$$y'' = -\frac{2y' + e^y(y')^2}{e^y + x}$$

### 【例2】参数方程二阶导数

**题目**：设 $\begin{cases} x = a\cos^3 t \\ y = a\sin^3 t \end{cases}$（$a > 0$），求 $\dfrac{d^2y}{dx^2}$。

**解**：

$$\frac{dx}{dt} = -3a\cos^2 t \sin t, \quad \frac{dy}{dt} = 3a\sin^2 t \cos t$$

$$\frac{dy}{dx} = \frac{3a\sin^2 t \cos t}{-3a\cos^2 t \sin t} = -\frac{\sin t}{\cos t} = -\tan t$$

$$\frac{d^2y}{dx^2} = \frac{\frac{d}{dt}(-\tan t)}{\frac{dx}{dt}} = \frac{-\sec^2 t}{-3a\cos^2 t \sin t} = \frac{1}{3a\cos^4 t \sin t}$$

$$\boxed{\frac{d^2y}{dx^2} = \frac{1}{3a\cos^4 t \sin t} = \frac{\sec^4 t \csc t}{3a}}$$

### 【例3】由方程确定的参数方程

**题目**：设 $y = y(x)$ 由 $\begin{cases} x = \arctan t \\ 2y - ty^2 + e^t = 5 \end{cases}$ 确定，求 $\dfrac{dy}{dx}$。

**解**：

$\dfrac{dx}{dt} = \dfrac{1}{1+t^2}$

对第二式关于 $t$ 求导（$y$ 是 $t$ 的函数）：

$2\dfrac{dy}{dt} - y^2 - 2ty\dfrac{dy}{dt} + e^t = 0$

$(2 - 2ty)\dfrac{dy}{dt} = y^2 - e^t$

$$\frac{dy}{dt} = \frac{y^2 - e^t}{2 - 2ty}$$

$$\frac{dy}{dx} = \frac{dy/dt}{dx/dt} = \frac{(y^2 - e^t)(1 + t^2)}{2 - 2ty}$$

### 【例4】隐函数在某点的切线

**题目**：求曲线 $x^3 + y^3 - 3xy = 0$ 在点 $\left(\dfrac{3}{2}, \dfrac{3}{2}\right)$ 处的切线方程。

**解**：

两边对 $x$ 求导：$3x^2 + 3y^2 y' - 3y - 3xy' = 0$

$(3y^2 - 3x)y' = 3y - 3x^2$

$y' = \dfrac{y - x^2}{y^2 - x}$

在 $\left(\dfrac{3}{2}, \dfrac{3}{2}\right)$ 处：

$$y' = \frac{\frac{3}{2} - \frac{9}{4}}{\frac{9}{4} - \frac{3}{2}} = \frac{\frac{6-9}{4}}{\frac{9-6}{4}} = \frac{-3}{3} = -1$$

切线方程：$y - \dfrac{3}{2} = -1 \cdot \left(x - \dfrac{3}{2}\right)$，即 $y = -x + 3$

### 【例5】极坐标下的切线斜率

**题目**：求心形线 $r = a(1 - \cos\theta)$ 在 $\theta = \dfrac{\pi}{2}$ 处的切线斜率。

**解**：

$r'(\theta) = a\sin\theta$

$$\frac{dy}{dx} = \frac{r'\sin\theta + r\cos\theta}{r'\cos\theta - r\sin\theta} = \frac{a\sin^2\theta + a(1-\cos\theta)\cos\theta}{a\sin\theta\cos\theta - a(1-\cos\theta)\sin\theta}$$

$$= \frac{\sin^2\theta + \cos\theta - \cos^2\theta}{\sin\theta\cos\theta - \sin\theta + \sin\theta\cos\theta} = \frac{\sin^2\theta + \cos\theta - \cos^2\theta}{2\sin\theta\cos\theta - \sin\theta}$$

在 $\theta = \dfrac{\pi}{2}$ 处：

$$\frac{dy}{dx} = \frac{1 + 0 - 0}{0 - 1} = -1$$

---

## 五、考研真题精选

### 【真题1】（2014年数一·解答）

**题目**：设函数 $y = f(x)$ 由方程 $y^3 + xy^2 + x^2y + 6 = 0$ 确定，求 $f(x)$ 的极值。

**解**：

两边对 $x$ 求导：$3y^2 y' + y^2 + 2xyy' + 2xy + x^2 y' = 0$

$(3y^2 + 2xy + x^2)y' = -(y^2 + 2xy)$

$$y' = -\frac{y^2 + 2xy}{3y^2 + 2xy + x^2}$$

令 $y' = 0$，得 $y^2 + 2xy = 0$，即 $y(y + 2x) = 0$。

**情形 1**：$y = 0$，代入原方程 $0 + 0 + 0 + 6 = 6 \ne 0$，矛盾。

**情形 2**：$y = -2x$，代入原方程：

$-8x^3 + x \cdot 4x^2 + x^2 \cdot (-2x) + 6 = -8x^3 + 4x^3 - 2x^3 + 6 = -6x^3 + 6 = 0$

$x^3 = 1$，$x = 1$，$y = -2$。

判断极值类型（代入 $y''$ 的符号），可得 $x = 1$ 处取得极小值 $y = -2$。

### 【真题2】（2020年数一·填空）

**题目**：设 $\begin{cases} x = t - \sin t \\ y = 1 - \cos t \end{cases}$，则 $\dfrac{d^2y}{dx^2}\bigg|_{t=\pi} = $ ______。

**解**：

$$\frac{dx}{dt} = 1 - \cos t, \quad \frac{dy}{dt} = \sin t$$

$$\frac{dy}{dx} = \frac{\sin t}{1 - \cos t} = \frac{2\sin\frac{t}{2}\cos\frac{t}{2}}{2\sin^2\frac{t}{2}} = \cot\frac{t}{2}$$

$$\frac{d^2y}{dx^2} = \frac{-\frac{1}{2}\csc^2\frac{t}{2}}{1 - \cos t} = \frac{-\frac{1}{2}\csc^2\frac{t}{2}}{2\sin^2\frac{t}{2}} = -\frac{1}{4\sin^4\frac{t}{2}}$$

在 $t = \pi$ 处，$\sin\dfrac{\pi}{2} = 1$：

$$\frac{d^2y}{dx^2}\bigg|_{t=\pi} = -\frac{1}{4}$$

**答案**：$-\dfrac{1}{4}$

---

## 📝 本节要点总结

| 方法 | 步骤 | 注意事项 |
|------|------|----------|
| 隐函数求导 | 方程两边对 $x$ 求导，$y$ 用链式法则 | $y$ 是 $x$ 的函数 |
| 参数方程一阶 | $y'_x = \psi'/\varphi'$ | 分子分母都是对参数求导 |
| 参数方程二阶 | $\frac{d}{dt}(\frac{dy}{dx}) \div \varphi'$ | 不是 $\psi''/\varphi''$ |
| 极坐标 | 转化为参数方程 | $x = r\cos\theta, y = r\sin\theta$ |

> 参数方程二阶导数是最容易出错的考点，务必记住公式 $\dfrac{d^2y}{dx^2} = \dfrac{(\frac{dy}{dx})'}{\frac{dx}{dt}}$，不能想当然地"分子分母分别求二阶导"。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 17：导数求导法则]] — 求导法则
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 18：高阶导数]] — 高阶导数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 20：函数的微分]] — 微分
