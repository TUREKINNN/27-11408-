---
title: Lecture 09 - 常微分方程
subject: 高等数学
chapter: 第八章
lecture: 09
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 09: 常微分方程

## 一、常微分方程的基本概念

### 1.1 微分方程的定义

<span style="background-color: #ccc1d9">**定义（微分方程）**</span> 含有未知函数的导数或微分的方程称为**微分方程**，简称**方程**。

### 1.2 微分方程的阶

<span style="background-color: #ccc1d9">**定义（微分方程的阶）**</span> 微分方程中所出现的未知函数最高阶导数的阶数，称为微分方程的**阶**。

### 1.3 微分方程的解

<span style="background-color: #ccc1d9">**定义（微分方程的解）**</span> 满足微分方程的函数，称为该方程的**解**。

### 1.4 微分方程的通解

<span style="background-color: #ccc1d9">**定义（通解）**</span> 如果微分方程的解中含有任意常数，且任意常数的个数与微分方程的阶数相同，则称之为微分方程的**通解**。

### 1.5 微分方程的特解

<span style="background-color: #ccc1d9">**定义（特解）**</span> 微分方程的不含任意常数的解，称之为**特解**。

### 1.6 初始条件

<span style="background-color: #ccc1d9">**定义（初始条件）**</span> 确定特解的一组常数条件称为**初始条件**。

### 1.7 积分曲线

<span style="background-color: #ccc1d9">**定义（积分曲线）**</span> 微分方程的一个解在平面上对应一条曲线，称为该微分方程的**积分曲线**。

---

## 二、一阶微分方程

### 2.1 可分离变量的方程

<span style="background-color: #ccc1d9">**定义（可分离变量方程）**</span> 能表示为 $g(y)dy = f(x)dx$ 的方程，称为**可分离变量的方程**。

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 两端积分：

$$\int g(y) dy = \int f(x) dx$$

**例题**：求微分方程 $y' = \frac{y(1-x)}{x}$ 的通解。

**解答**：

$$\frac{dy}{dx} = \frac{y(1-x)}{x}$$

分离变量：

$$\frac{dy}{y} = \frac{1-x}{x} dx$$

积分：

$$\ln|y| = \ln|x| - x + C_1$$

即

$$y = Cx e^{-x}$$

---

### 2.2 齐次微分方程

<span style="background-color: #ccc1d9">**定义（齐次微分方程）**</span> 能化为 $\frac{dy}{dx} = \varphi\left(\frac{y}{x}\right)$ 的微分方程称为**齐次微分方程**。

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 令 $u = \frac{y}{x}$，则 $y' = u + xu'$，从而将原方程化为 $xu' = \varphi(u) - u$，此方程为可分离变量的方程。

**例题**：求微分方程 $x^2y' + xy = y^2$ 满足初始条件 $y(1) = 1$ 的特解。

**解答**：

原方程化为 $y' = \left(\frac{y}{x}\right)^2 - \frac{y}{x}$

令 $u = \frac{y}{x}$，则 $xu' + u = u^2 - u$，即 $xu' = u^2 - 2u$

分离变量：$\frac{du}{u^2 - 2u} = \frac{dx}{x}$

积分得 $\frac{y - 2x}{y} = Cx^2$

由 $y(1) = 1$，得 $C = -1$，故 $y = \frac{2x}{1 + x^2}$

---

### 2.3 一阶线性微分方程

<span style="background-color: #ccc1d9">**定义（一阶线性微分方程）**</span> 形如 $y' + p(x)y = q(x)$ 的方程称为**一阶线性微分方程**。

<span style="background-color: #8db3e2">**定理（通解公式）**</span>

$$y = e^{-\int p(x) dx} \left[ \int q(x) e^{\int p(x) dx} dx + C \right]$$

**例题**：求微分方程 $(y + x^2 e^{-x})dx - xdy = 0$ 的通解。

**解答**：

$$\frac{dy}{dx} - \frac{1}{x}y = x e^{-x}$$

由通解公式：

$$y = e^{\int \frac{1}{x} dx} \left( \int x e^{-x} e^{-\int \frac{1}{x} dx} dx + C \right) = x \left( -e^{-x} + C \right) = x(C - e^{-x})$$

---

### 2.4 伯努利方程（仅数学一要求）

<span style="background-color: #ccc1d9">**定义（伯努利方程）**</span> 形如 $y' + p(x)y = Q(x)y^n$（$n \neq 0, 1$）的方程称为**伯努利方程**。

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 令 $u = y^{1-n}$，将原方程化为一阶线性微分方程。

---

### 2.5 全微分方程（仅数学一要求）

<span style="background-color: #ccc1d9">**定义（全微分方程）**</span> 若方程 $P(x,y)dx + Q(x,y)dy = 0$ 的左端是某个函数 $u(x,y)$ 的全微分，即

$$du(x,y) = P(x,y)dx + Q(x,y)dy$$

则称该方程为**全微分方程**，其通解为 $u(x,y) = C$。

<span style="background-color: #8db3e2">**定理（判别条件）**</span> 当 $P(x,y), Q(x,y)$ 在单连通域 $G$ 内具有一阶连续偏导数时，方程 $Pdx + Qdy = 0$ 是全微分方程的充要条件是：

$$\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$$

---

## 三、可降阶的高阶微分方程

### 3.1 $y^{(n)} = f(x)$ 型

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 连续积分 $n$ 次即可。

**例题**：求微分方程 $xy'' + 3y' = 0$ 的通解。

**解答**：

令 $y' = p$，则 $y'' = \frac{dp}{dx}$

$$x\frac{dp}{dx} + 3p = 0$$

分离变量：$\frac{dp}{p} = -\frac{3}{x}dx$

积分：$p x^3 = C_1$

即 $y' = \frac{C_1}{x^3}$

积分得 $y = C_1 + \frac{C_2}{x^2}$

---

### 3.2 $y'' = f(x, y')$ 型

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 令 $y' = p$，则 $y'' = p'$，方程化为 $p' = f(x, p)$。

---

### 3.3 $y'' = f(y, y')$ 型

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 令 $y' = p$，则 $y'' = p\frac{dp}{dy}$，方程化为 $p\frac{dp}{dy} = f(y, p)$。

**例题**：求微分方程 $yy'' + y'^2 = 0$ 满足初始条件 $y(0) = 1, y'(0) = \frac{1}{2}$ 的特解。

**解答**：

令 $y' = p$，则 $y'' = p\frac{dp}{dy}$

$$yp\frac{dp}{dy} + p^2 = 0$$

即 $y\frac{dp}{dy} = -p$

分离变量：$\frac{dp}{p} = -\frac{dy}{y}$

积分：$yp = C_1$

由 $y(0) = 1, y'(0) = \frac{1}{2}$，得 $C_1 = \frac{1}{2}$

故 $y\frac{dy}{dx} = \frac{1}{2}$，即 $y^2 = x + C_2$

由 $y(0) = 1$，得 $C_2 = 1$，故 $y = \sqrt{x + 1}$

---

## 四、高阶线性微分方程解的结构

### 4.1 二阶线性微分方程的一般形式

<span style="background-color: #ccc1d9">**定义（二阶线性微分方程）**</span>

$$y'' + p(x)y' + q(x)y = f(x)$$

当 $f(x) \equiv 0$ 时，称为**齐次方程**；当 $f(x) \neq 0$ 时，称为**非齐次方程**。

### 4.2 齐次方程解的结构

<span style="background-color: #8db3e2">**定理（齐次方程通解结构）**</span> 若 $y_1(x)$ 和 $y_2(x)$ 是齐次方程的两个线性无关的特解，则

$$y = C_1 y_1(x) + C_2 y_2(x)$$

是齐次方程的通解。

<span style="background-color: #8db3e2">**定理（线性无关的判定）**</span> 两个解线性无关的充要条件是它们之比不为常数。

### 4.3 非齐次方程解的结构

<span style="background-color: #8db3e2">**定理（非齐次方程通解结构）**</span> 若 $y^*$ 是非齐次方程的一个特解，$y_1(x)$ 和 $y_2(x)$ 是齐次方程的两个线性无关的特解，则

$$y = C_1 y_1(x) + C_2 y_2(x) + y^*(x)$$

是非齐次方程的通解。

<span style="background-color: #8db3e2">**定理（特解的性质）**</span> 若 $y_1^*(x), y_2^*(x)$ 是非齐次方程的两个特解，则 $y_2^*(x) - y_1^*(x)$ 是齐次方程的解。

---

## 五、二阶常系数齐次线性微分方程

### 5.1 标准形式

<span style="background-color: #ccc1d9">**定义（二阶常系数齐次线性微分方程）**</span>

$$y'' + py' + qy = 0$$

其中 $p, q$ 为常数。

### 5.2 特征方程

<span style="background-color: #ccc1d9">**定义（特征方程）**</span> 将 $y'' + py' + qy = 0$ 中的 $y''$ 换成 $r^2$，$y'$ 换成 $r$，$y$ 换成 $1$，得到

$$r^2 + pr + q = 0$$

称为**特征方程**。

### 5.3 特征根与通解的关系

<span style="background-color: #8db3e2">**定理（特征根与通解）**</span>

设特征方程的两个根为 $r_1, r_2$：

1. **若 $r_1 \neq r_2$ 为两个不相等的实特征根**，则通解为：

$$y = C_1 e^{r_1 x} + C_2 e^{r_2 x}$$

2. **若 $r_1 = r_2$ 为二重实特征根**，则通解为：

$$y = (C_1 + C_2 x) e^{r_1 x}$$

3. **若 $r_1 = \alpha + i\beta, r_2 = \alpha - i\beta$ 为共轭复根**，则通解为：

$$y = e^{\alpha x}(C_1 \cos\beta x + C_2 \sin\beta x)$$

**例题**：求微分方程 $y'' - y' + \frac{1}{4}y = 0$ 的通解。

**解答**：

特征方程 $r^2 - r + \frac{1}{4} = 0$，解得 $r_{1,2} = \frac{1}{2}$（重根）

故通解为 $y = e^{\frac{1}{2}x}(C_1 + C_2 x)$

---

## 六、二阶常系数非齐次线性微分方程

### 6.1 标准形式

<span style="background-color: #ccc1d9">**定义（二阶常系数非齐次线性微分方程）**</span>

$$y'' + py' + qy = f(x)$$

其中 $p, q$ 为常数，$f(x)$ 为自由项。

### 6.2 特解的设法

#### （1）$f(x) = P_m(x)e^{\lambda x}$ 型

<span style="background-color: #8db3e2">**定理（特解设法）**</span> 设特解为

$$y^* = x^k Q_m(x) e^{\lambda x}$$

其中 $Q_m(x)$ 是与 $P_m(x)$ 同次的一般多项式，$k$ 是特征方程含根 $\lambda$ 的重复次数：
- 若 $\lambda$ 不是特征根，则 $k = 0$
- 若 $\lambda$ 是单特征根，则 $k = 1$
- 若 $\lambda$ 是二重特征根，则 $k = 2$

#### （2）$f(x) = e^{\alpha x}[P_l^{(1)}(x)\cos\beta x + P_n^{(2)}(x)\sin\beta x]$ 型

<span style="background-color: #8db3e2">**定理（特解设法）**</span> 设特解为

$$y^* = x^k e^{\alpha x}[R_m^{(1)}(x)\cos\beta x + R_m^{(2)}(x)\sin\beta x]$$

其中 $m = \max\{l, n\}$，$k$ 的取值：
- 若 $\alpha \pm i\beta$ 不是特征根，则 $k = 0$
- 若 $\alpha \pm i\beta$ 是特征根，则 $k = 1$

**例题**：求微分方程 $y'' - 4y' + 3y = 2e^{2x}$ 的通解。

**解答**：

齐次方程 $y'' - 4y' + 3y = 0$ 的特征方程 $r^2 - 4r + 3 = 0$，解得 $r_1 = 1, r_2 = 3$

齐次通解：$y = C_1 e^x + C_2 e^{3x}$

设特解 $y^* = Ae^{2x}$，代入原方程：

$4Ae^{2x} - 8Ae^{2x} + 3Ae^{2x} = 2e^{2x}$，即 $-Ae^{2x} = 2e^{2x}$

故 $A = -2$，$y^* = -2e^{2x}$

通解：$y = C_1 e^x + C_2 e^{3x} - 2e^{2x}$

---

## 七、欧拉方程（仅数学一要求）

### 7.1 欧拉方程的定义

<span style="background-color: #ccc1d9">**定义（欧拉方程）**</span> 形如

$$x^n y^{(n)} + p_1 x^{n-1} y^{(n-1)} + \cdots + p_{n-1} x y' + p_n y = f(x)$$

的方程称为**欧拉方程**。

### 7.2 二阶欧拉方程的解法

<span style="background-color: #8db3e2">**定理（求解方法）**</span> 令 $x = e^t$ 或 $t = \ln x$，可将欧拉方程化为线性常系数微分方程。

对于二阶欧拉方程 $x^2 y'' + pxy' + qy = f(x)$：

令 $x = e^t$，则 $t = \ln x$，设 $Y(t) = y(e^t)$，有：

$$\frac{dy}{dx} = \frac{1}{x}\frac{dY}{dt}, \quad \frac{d^2y}{dx^2} = \frac{1}{x^2}\left(\frac{d^2Y}{dt^2} - \frac{dY}{dt}\right)$$

代入原方程即可化为常系数微分方程。

---

## 八、微分方程的应用

### 8.1 微分方程在物理中的应用

**常见物理问题**：
- 冷却定律：$\frac{dT}{dt} = -k(T - T_0)$
- 放射性衰变：$\frac{dN}{dt} = -\lambda N$
- 弹簧振动：$m\frac{d^2x}{dt^2} + c\frac{dx}{dt} + kx = 0$

### 8.2 微分方程在几何中的应用

**常见几何问题**：
- 曲线在某点的切线斜率等于某函数
- 曲线在某点的曲率等于某函数
- 曲线围成的面积与曲线方程有关

---

## 九、典型例题

### 例题1：可分离变量方程

**题目**：求微分方程 $\frac{dy}{dx} = xy$ 的通解。

**思路**：分离变量后两边积分。

**解答**：

分离变量：$\frac{dy}{y} = x dx$

积分：$\ln|y| = \frac{x^2}{2} + C_1$

故 $y = Ce^{\frac{x^2}{2}}$

**总结**：可分离变量方程是基础类型。

---

### 例题2：一阶线性方程

**题目**：求微分方程 $y' + 2xy = 2xe^{-x^2}$ 的通解。

**思路**：直接套用一阶线性微分方程的通解公式。

**解答**：

$p(x) = 2x$，$q(x) = 2xe^{-x^2}$

$y = e^{-\int 2x dx} \left( \int 2xe^{-x^2} e^{\int 2x dx} dx + C \right) = e^{-x^2} \left( \int 2xe^{-x^2} e^{x^2} dx + C \right) = e^{-x^2} \left( x^2 + C \right)$

**总结**：一阶线性方程通解公式是解题利器。

---

### 例题3：二阶常系数齐次方程

**题目**：求微分方程 $y'' + 2y' + 5y = 0$ 的通解。

**思路**：求特征方程的根，根据根的情况写通解。

**解答**：

特征方程 $r^2 + 2r + 5 = 0$，解得 $r_{1,2} = -1 \pm 2i$

通解：$y = e^{-x}(C_1 \cos 2x + C_2 \sin 2x)$

**总结**：共轭复根对应指数函数乘三角函数。

---

### 例题4：二阶常系数非齐次方程

**题目**：求微分方程 $y'' + y = -2x$ 的通解。

**思路**：先求齐次通解，再求特解。

**解答**：

齐次方程 $y'' + y = 0$ 的通解：$y = C_1 \cos x + C_2 \sin x$

设特解 $y^* = ax + b$，代入得 $-ax - b + ax + b = -2x$，故 $a = -2, b = 0$

通解：$y = C_1 \cos x + C_2 \sin x - 2x$

**总结**：多项式乘指数型自由项，用待定系数法求特解。

---

### 例题5：微分方程的几何应用

**题目**：求曲线的方程，使得该曲线在点 $(x,y)$ 处的切线斜率等于该点横坐标的平方，且曲线过点 $(0, 1)$。

**思路**：根据题意建立微分方程并求解。

**解答**：

由题意：$\frac{dy}{dx} = x^2$

积分：$y = \frac{x^3}{3} + C$

由 $y(0) = 1$，得 $C = 1$

故曲线方程为 $y = \frac{x^3}{3} + 1$

**总结**：几何应用问题关键在于正确建立微分方程。

---

## 十、解题方法总结

### 10.1 一阶微分方程类型判别与解法

| 类型 | 方程形式 | 解法 |
|------|---------|------|
| 可分离变量 | $g(y)dy = f(x)dx$ | 分离变量积分 |
| 齐次方程 | $y' = \varphi(y/x)$ | 令 $u = y/x$ |
| 一阶线性 | $y' + p(x)y = q(x)$ | 通解公式 |
| 伯努利方程 | $y' + p(x)y = Q(x)y^n$ | 令 $u = y^{1-n}$ |
| 全微分方程 | $Pdx + Qdy = 0$ | 积分或偏积分 |

### 10.2 高阶微分方程解法

1. **可降阶方程**：直接积分或换元降阶
2. **常系数齐次方程**：求特征根，写通解
3. **常系数非齐次方程**：齐次通解 + 特解（待定系数法）

### 10.3 二阶常系数齐次方程特征根与通解对照表

| 特征根情况 | 通解形式 |
|------------|---------|
| $r_1 \neq r_2$（实根） | $C_1 e^{r_1 x} + C_2 e^{r_2 x}$ |
| $r_1 = r_2$（重根） | $(C_1 + C_2 x) e^{r_1 x}$ |
| $r_{1,2} = \alpha \pm i\beta$（共轭复根） | $e^{\alpha x}(C_1 \cos\beta x + C_2 \sin\beta x)$ |

---

## 参考答案提示

1. $y = Ce^{\frac{x^2}{2}}$

2. $y = e^{-x^2}(x^2 + C)$

3. $y = e^{-x}(C_1 \cos 2x + C_2 \sin 2x)$

4. $y = C_1 \cos x + C_2 \sin x - 2x$

5. $y = \frac{x^3}{3} + 1$

---

> **注**：本 Lecture 内容涵盖常微分方程的基本概念、各类一阶和高阶微分方程的解法及典型例题。重点掌握可分离变量方程、一阶线性方程、二阶常系数线性微分方程的解法。建议结合《基础过关660题》高数篇第81-93题进行练习巩固。
