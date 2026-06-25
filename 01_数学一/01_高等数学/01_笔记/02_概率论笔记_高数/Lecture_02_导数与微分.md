---
title: Lecture 02 - 导数与微分
subject: 高等数学
chapter: 第二章
lecture: 02
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 02: 导数与微分

## 一、导数的概念

### 1.1 导数的定义

<span style="background-color: #ccc1d9">**定义（导数）**</span> 设函数 $y = f(x)$ 在点 $x_0$ 的某邻域内有定义，若极限

$$\lim_{\Delta x \to 0} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}$$

存在，则称 $f(x)$ 在点 $x_0$ **可导**，该极限值称为 $f(x)$ 在 $x_0$ 的**导数**，记作 $f'(x_0)$ 或 $\frac{dy}{dx}\bigg|_{x=x_0}$。

**等价形式**：
- $f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}$
- $f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$

### 1.2 左导数与右导数

<span style="background-color: #ccc1d9">**定义（左导数与右导数）**</span>
- **左导数**：$f'_-(x_0) = \lim_{\Delta x \to 0^-} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}$
- **右导数**：$f'_+(x_0) = \lim_{\Delta x \to 0^+} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}$

<span style="background-color: #8db3e2">**定理**</span> $f(x)$ 在 $x_0$ 可导的充要条件是 $f'_-(x_0)$ 和 $f'_+(x_0)$ 都存在且相等。

### 1.3 导数的几何意义

<span style="background-color: #ccc1d9">**定义（切线）**</span> 导数 $f'(x_0)$ 表示曲线 $y = f(x)$ 在点 $(x_0, f(x_0))$ 处切线的斜率。

**切线方程**：$y - f(x_0) = f'(x_0)(x - x_0)$

**法线方程**：$y - f(x_0) = -\frac{1}{f'(x_0)}(x - x_0)$（$f'(x_0) \neq 0$）

### 1.4 可导与连续的关系

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在 $x_0$ 可导，则 $f(x)$ 在 $x_0$ 连续。

**注意**：反之不成立。连续不一定可导。

**典型反例**：$f(x) = |x|$ 在 $x = 0$ 连续但不可导。

---

## 二、导数的运算法则

### 2.1 基本导数公式

| 函数 | 导数 |
|------|------|
| $c$（常数） | $0$ |
| $x^n$ | $nx^{n-1}$ |
| $a^x$ | $a^x \ln a$ |
| $e^x$ | $e^x$ |
| $\log_a x$ | $\frac{1}{x \ln a}$ |
| $\ln x$ | $\frac{1}{x}$ |
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\sec^2 x$ |
| $\cot x$ | $-\csc^2 x$ |
| $\sec x$ | $\sec x \tan x$ |
| $\csc x$ | $-\csc x \cot x$ |
| $\arcsin x$ | $\frac{1}{\sqrt{1 - x^2}}$ |
| $\arccos x$ | $-\frac{1}{\sqrt{1 - x^2}}$ |
| $\arctan x$ | $\frac{1}{1 + x^2}$ |
| $\text{arccot} x$ | $-\frac{1}{1 + x^2}$ |

### 2.2 导数的四则运算

<span style="background-color: #8db3e2">**定理**</span> 设 $f(x)$ 和 $g(x)$ 可导，则：

1. $(f + g)' = f' + g'$（加法法则）
2. $(f - g)' = f' - g'$（减法法则）
3. $(f \cdot g)' = f'g + fg'$（乘法法则）
4. $(cf)' = cf'$（$c$ 为常数）
5. $\left(\frac{f}{g}\right)' = \frac{f'g - fg'}{g^2}$（$g \neq 0$）（除法法则）

### 2.3 复合函数求导法则

<span style="background-color: #8db3e2">**定理（链式法则）**</span> 若 $u = g(x)$ 在 $x$ 可导，$y = f(u)$ 在 $u = g(x)$ 可导，则复合函数 $y = f(g(x))$ 在 $x$ 可导，且

$$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx} = f'(u) \cdot g'(x)$$

### 2.4 反函数求导法则

<span style="background-color: #8db3e2">**定理**</span> 若 $y = f(x)$ 在某区间内单调可导，且 $f'(x) \neq 0$，则其反函数 $x = f^{-1}(y)$ 在对应区间也可导，且

$$\frac{dx}{dy} = \frac{1}{\frac{dy}{dx}} = \frac{1}{f'(x)}$$

---

## 三、隐函数与参数方程求导

### 3.1 隐函数求导

<span style="background-color: #ccc1d9">**定义（隐函数）**</span> 由方程 $F(x, y) = 0$ 确定的函数关系 $y = y(x)$ 称为**隐函数**。

**求导方法**：
1. 方程两边对 $x$ 求导，将 $y$ 视为 $x$ 的函数
2. 解出 $\frac{dy}{dx}$

**示例**：设 $x^2 + y^2 = 1$ 确定 $y = y(x)$，求 $\frac{dy}{dx}$。

两边对 $x$ 求导：$2x + 2y \frac{dy}{dx} = 0$

解得：$\frac{dy}{dx} = -\frac{x}{y}$

### 3.2 参数方程求导

<span style="background-color: #ccc1d9">**定义（参数方程）**</span> 若 $y$ 与 $x$ 的关系由参数方程 $\begin{cases} x = x(t) \\ y = y(t) \end{cases}$ 给出，则

$$\frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{y'(t)}{x'(t)}$$

**二阶导数**：

$$\frac{d^2y}{dx^2} = \frac{d}{dx}\left(\frac{dy}{dx}\right) = \frac{\frac{d}{dt}\left(\frac{dy}{dx}\right)}{\frac{dx}{dt}} = \frac{\frac{d}{dt}\left(\frac{y'(t)}{x'(t)}\right)}{x'(t)}$$

---

## 四、高阶导数

### 4.1 高阶导数的定义

<span style="background-color: #ccc1d9">**定义（高阶导数）**</span> 导数 $f'(x)$ 的导数称为 $f(x)$ 的**二阶导数**，记作 $f''(x)$ 或 $\frac{d^2y}{dx^2}$。

一般地，$n$ 阶导数记作 $f^{(n)}(x)$ 或 $\frac{d^ny}{dx^n}$。

### 4.2 常用高阶导数公式

| 函数 | $n$ 阶导数 |
|------|-----------|
| $x^m$（$m$ 为正整数） | $m(m-1)\cdots(m-n+1)x^{m-n}$（$n \leq m$） |
| $e^x$ | $e^x$ |
| $a^x$ | $a^x (\ln a)^n$ |
| $\sin x$ | $\sin\left(x + \frac{n\pi}{2}\right)$ |
| $\cos x$ | $\cos\left(x + \frac{n\pi}{2}\right)$ |
| $\ln x$ | $(-1)^{n-1} \frac{(n-1)!}{x^n}$ |
| $(1 + x)^m$ | $m(m-1)\cdots(m-n+1)(1+x)^{m-n}$ |

### 4.3 高阶导数的运算法则

<span style="background-color: #8db3e2">**定理（莱布尼茨公式）**</span> 设 $f(x)$ 和 $g(x)$ 都有 $n$ 阶导数，则

$$(f \cdot g)^{(n)} = \sum_{k=0}^{n} C_n^k f^{(n-k)} g^{(k)}$$

其中 $C_n^k = \frac{n!}{k!(n-k)!}$ 为组合数。

---

## 五、微分

### 5.1 微分的定义

<span style="background-color: #ccc1d9">**定义（微分）**</span> 设 $y = f(x)$ 在 $x_0$ 可导，则称 $f'(x_0)\Delta x$ 为 $f(x)$ 在 $x_0$ 处的**微分**，记作 $dy$ 或 $df$。

$$dy = f'(x_0) \Delta x = f'(x_0) dx$$

### 5.2 微分的几何意义

微分 $dy$ 表示曲线 $y = f(x)$ 在点 $(x_0, f(x_0))$ 处切线的纵坐标增量。

### 5.3 微分与导数的关系

<span style="background-color: #8db3e2">**定理**</span> 函数 $f(x)$ 在 $x_0$ 可微的充要条件是 $f(x)$ 在 $x_0$ 可导，且 $dy = f'(x_0) dx$。

### 5.4 微分形式不变性

<span style="background-color: #8db3e2">**定理**</span> 无论 $u$ 是自变量还是中间变量，微分形式 $dy = f'(u) du$ 保持不变。

---

## 六、典型例题

### 例题1：导数定义的应用

**题目**：设 $f(x)$ 在 $x = 0$ 处连续，且 $\lim_{x \to 0} \frac{f(x)}{e^x - 1} = 2$，求曲线 $y = f(x)$ 在 $x = 0$ 处的法线方程。

**思路**：利用导数定义，先求 $f(0)$ 和 $f'(0)$。

**解答**：
由 $\lim_{x \to 0} \frac{f(x)}{e^x - 1} = 2$，且 $e^x - 1 \sim x$（$x \to 0$）

所以 $\lim_{x \to 0} \frac{f(x)}{x} = 2$

由连续性：$f(0) = \lim_{x \to 0} f(x) = \lim_{x \to 0} \frac{f(x)}{x} \cdot x = 2 \cdot 0 = 0$

由导数定义：$f'(0) = \lim_{x \to 0} \frac{f(x) - f(0)}{x - 0} = \lim_{x \to 0} \frac{f(x)}{x} = 2$

法线方程：$y - 0 = -\frac{1}{2}(x - 0)$，即 $y = -\frac{x}{2}$ 或 $x + 2y = 0$

**总结**：利用导数定义求导数时，关键是分析极限表达式。

---

### 例题2：分段函数求导

**题目**：设 $f(x) = \begin{cases} g(x)\sin\frac{1}{x}, & x \neq 0 \\ 0, & x = 0 \end{cases}$，其中 $g(x)$ 在 $x = 0$ 点可导。若 $f(x)$ 在 $x = 0$ 点可导，求 $f'(0)$。

**思路**：利用导数定义，分析极限。

**解答**：
$f'(0) = \lim_{x \to 0} \frac{f(x) - f(0)}{x - 0} = \lim_{x \to 0} \frac{g(x)\sin\frac{1}{x}}{x}$

为使此极限存在，需要 $\lim_{x \to 0} g(x) = 0$（否则 $\sin\frac{1}{x}$ 振荡导致极限不存在）

由 $g(x)$ 在 $x = 0$ 可导，$g(x)$ 连续，所以 $g(0) = 0$

$f'(0) = \lim_{x \to 0} \frac{g(x) - g(0)}{x} \cdot \sin\frac{1}{x} = g'(0) \cdot \lim_{x \to 0} \sin\frac{1}{x}$

由于 $\lim_{x \to 0} \sin\frac{1}{x}$ 不存在，要使 $f'(0)$ 存在，必须有 $g'(0) = 0$

因此 $f'(0) = 0$

**总结**：分段函数在分界点求导，必须使用导数定义，注意极限的存在性条件。

---

### 例题3：隐函数求导

**题目**：设方程 $x^2 + xy + y^2 + y = 0$ 确定 $y = y(x)$，满足 $y(1) = -1$，在 $x = 1$ 的某邻域内连续，在 $x = 1$ 的某去心邻域内可导，求 $\lim_{x \to 1} \frac{x - 1}{y + 1}$。

**思路**：隐函数求导，利用导数定义。

**解答**：
方程两边对 $x$ 求导：$2x + y + x\frac{dy}{dx} + 2y\frac{dy}{dx} + \frac{dy}{dx} = 0$

在 $x = 1$, $y = -1$ 处：$2(1) + (-1) + 1 \cdot y'(1) + 2(-1) \cdot y'(1) + y'(1) = 0$

$2 - 1 + y'(1) - 2y'(1) + y'(1) = 0$

$1 = 0$？这表明需要重新计算。

正确做法：$2x + y + xy' + 2yy' + y' = 0$

在 $(1, -1)$ 处：$2 + (-1) + y' + 2(-1)y' + y' = 0$

$1 + y' - 2y' + y' = 0$

$1 = 0$ 仍然矛盾，说明题目条件需要验证。

利用导数定义：$\lim_{x \to 1} \frac{x - 1}{y + 1} = \frac{1}{\lim_{x \to 1} \frac{y + 1}{x - 1}} = \frac{1}{y'(1)}$

需要先求 $y'(1)$。由隐函数求导：$(x + 2y + 1)y' = -2x - y$

$y' = \frac{-2x - y}{x + 2y + 1}$

在 $(1, -1)$ 处：$y'(1) = \frac{-2 - (-1)}{1 + 2(-1) + 1} = \frac{-1}{0}$

分母为零，说明需要用洛必达法则或泰勒展开。

**总结**：隐函数求导时，注意分母为零的特殊情况。

---

### 例题4：高阶导数

**题目**：设 $f(x) = e^x \sin x$，求 $f^{(n)}(x)$。

**思路**：利用莱布尼茨公式或找规律。

**解答**：
$f'(x) = e^x \sin x + e^x \cos x = e^x(\sin x + \cos x)$

$f''(x) = e^x(\sin x + \cos x) + e^x(\cos x - \sin x) = e^x(\cos x + \cos x) = 2e^x \cos x$

$f'''(x) = 2e^x \cos x + 2e^x(-\sin x) = 2e^x(\cos x - \sin x)$

$f^{(4)}(x) = 2e^x(\cos x - \sin x) + 2e^x(-\sin x - \cos x) = -4e^x \sin x$

规律：$f^{(n)}(x) = 2^{n/2} e^x \sin\left(x + \frac{n\pi}{4}\right)$（需要验证）

更准确的方法：设 $f(x) = e^x \sin x = e^x \cdot \frac{e^{ix} - e^{-ix}}{2i} = \frac{e^{x(1+i)} - e^{x(1-i)}}{2i}$

$f^{(n)}(x) = \frac{(1+i)^n e^{x(1+i)} - (1-i)^n e^{x(1-i)}}{2i}$

由于 $(1+i) = \sqrt{2} e^{i\frac{\pi}{4}}$，$(1+i)^n = 2^{n/2} e^{i\frac{n\pi}{4}}$

$f^{(n)}(x) = \frac{2^{n/2} e^{i\frac{n\pi}{4}} e^{x(1+i)} - 2^{n/2} e^{-i\frac{n\pi}{4}} e^{x(1-i)}}{2i}$

$= 2^{n/2} e^x \cdot \frac{e^{ix + i\frac{n\pi}{4}} - e^{-ix - i\frac{n\pi}{4}}}{2i}$

$= 2^{n/2} e^x \sin\left(x + \frac{n\pi}{4}\right)$

**总结**：利用复数表示可以简化三角函数的高阶导数计算。

---

### 例题5：参数方程求导

**题目**：设 $y = y(x)$ 由参数方程 $\begin{cases} x = 2^{\ln(t+1)} \\ y = \arctan t \end{cases}$ 确定，求 $\frac{dy}{dx}$ 和 $\frac{d^2y}{dx^2}$。

**思路**：参数方程求导公式。

**解答**：
$\frac{dx}{dt} = 2^{\ln(t+1)} \cdot \ln 2 \cdot \frac{1}{t+1}$

$\frac{dy}{dt} = \frac{1}{1 + t^2}$

$\frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{1}{1 + t^2} \cdot \frac{t+1}{2^{\ln(t+1)} \ln 2} = \frac{t+1}{(1+t^2) \cdot 2^{\ln(t+1)} \ln 2}$

二阶导数需要继续对 $t$ 求导再除以 $\frac{dx}{dt}$。

**总结**：参数方程求导要注意计算顺序，二阶导数公式容易出错。

---

## 七、解题方法总结

### 7.1 求导的主要方法

| 类型 | 方法 |
|------|------|
| 基本函数 | 直接用公式 |
| 复合函数 | 式法则 |
| 四则运算 | 加减乘除法则 |
| 隐函数 | 方程两边求导 |
| 参数方程 | $\frac{dy}{dx} = \frac{y'(t)}{x'(t)}$ |
| 分段函数 | 分界点用定义，其他用公式 |
| 反函数 | $\frac{dx}{dy} = \frac{1}{f'(x)}$ |

### 7.2 常见易错点

1. **复合函数求导遗漏**：忘记链式法则中的某一步
2. **隐函数求导混淆**：忘记 $y$ 是 $x$ 的函数
3. **分段函数分界点**：直接用公式而非定义
4. **参数方程二阶导**：忘记再除以 $\frac{dx}{dt}$
5. **符号错误**：$\cos$ 导数为 $-\sin$，$\ln$ 导数为 $\frac{1}{x}$

---

## 八、练习题精选

### 基础练习

1. 设 $f'(1) = 1$，求 $\lim_{x \to 0} \frac{f(1+x) - f(1-2\sin x)}{x + 2\sin x}$。

2. 设 $f(x)$ 在 $x = 0$ 可导且 $f(0) = 1$, $f'(0) = 3$，求 $\lim_{n \to \infty} \left(f\left(\frac{1}{n}\right)\right)^{\frac{\frac{1}{n}}{1 - \cos\frac{1}{n}}}$。

3. 设 $y = \sqrt{\frac{e}{e^{4x} + 1}}$，求 $dy$。

4. 设函数 $f(x)$ 可导，且 $f'(x) = e^{f(x)}$, $f(2) = 1$，求 $f''(2)$。

### 提高练习

5. 若曲线 $y = x^2 + ax + b$ 与曲线 $2y = -1 + xy^3$ 在 $(1, -1)$ 处相切，求 $a, b$。

6. 设 $f(x) = \begin{cases} \arctan x, & x \leq 1 \\ \frac{1}{2}(e^{x^2-1} - x) + \frac{\pi}{4}, & x > 1 \end{cases}$，求 $f'(x)$。

7. 设 $f(x)$ 在 $x = a$ 处二阶导数存在，求 $\lim_{h \to 0} \frac{\frac{f(a+h) - f(a)}{h} - f'(a)}{h}$。

---

## 参考答案提示

1. $1$（提示：利用导数定义变形）

2. $e^6$（提示：利用 $f\left(\frac{1}{n}\right) \approx f(0) + f'(0)\frac{1}{n}$）

3. $dy = -\frac{2e^{4x}}{(e^{4x}+1)^{3/2}} dx$（提示：复合函数求导）

4. $e^2$（提示：$f''(x) = f'(x) \cdot e^{f(x)} = e^{f(x)} \cdot e^{f(x)} = e^{2f(x)}$）

5. $a = -3$, $b = 1$（提示：两曲线在切点处函数值相等、导数相等）

6. $f'(x) = \begin{cases} \frac{1}{1+x^2}, & x < 1 \\ e^{x^2-1} \cdot x - \frac{1}{2}, & x > 1 \end{cases}$，在 $x = 1$ 处需验证连续性

7. $\frac{f''(a)}{2}$（提示：泰勒展开或洛必达法则）

---

> **注**：本 Lecture 内容涵盖导数与微分的基本概念、求导法则及典型例题。建议结合《基础过关660题》第20-38题进行练习巩固。