---
title: Lecture 03 - 一元函数积分学
subject: 高等数学
chapter: 第三章
lecture: 03
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 03: 一元函数积分学

## 一、不定积分的概念与性质

### 1.1 原函数的定义

<span style="background-color: #ccc1d9">**定义（原函数）**</span> 设 $f(x)$ 在区间 $I$ 上有定义，若存在函数 $F(x)$，使得对任意 $x \in I$，都有 $F'(x) = f(x)$，则称 $F(x)$ 为 $f(x)$ 在区间 $I$ 上的**原函数**。

<span style="background-color: #ccc1d9">**定义（不定积分）**</span> 若 $F(x)$ 是 $f(x)$ 的一个原函数，则 $f(x)$ 的全体原函数称为**不定积分**，记作

$$\int f(x) \, dx = F(x) + C$$

其中 $C$ 为任意常数。

### 1.2 原函数的存在性

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在区间 $I$ 上连续，则 $f(x)$ 在 $I$ 上必有原函数。

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在区间 $I$ 上有第一类间断点，则 $f(x)$ 在 $I$ 上没有原函数。

---

## 二、基本积分公式

| 函数 | 不定积分 |
|------|----------|
| $\int k \, dx$ | $kx + C$ |
| $\int x^\alpha \, dx$ | $\frac{x^{\alpha+1}}{\alpha+1} + C$（$\alpha \neq -1$） |
| $\int \frac{1}{x} \, dx$ | $\ln|x| + C$ |
| $\int e^x \, dx$ | $e^x + C$ |
| $\int a^x \, dx$ | $\frac{a^x}{\ln a} + C$ |
| $\int \sin x \, dx$ | $-\cos x + C$ |
| $\int \cos x \, dx$ | $\sin x + C$ |
| $\int \sec^2 x \, dx$ | $\tan x + C$ |
| $\int \csc^2 x \, dx$ | $-\cot x + C$ |
| $\int \sec x \tan x \, dx$ | $\sec x + C$ |
| $\int \csc x \cot x \, dx$ | $-\csc x + C$ |
| $\int \frac{1}{1+x^2} \, dx$ | $\arctan x + C$ |
| $\int \frac{1}{\sqrt{1-x^2}} \, dx$ | $\arcsin x + C$ |
| $\int \tan x \, dx$ | $-\ln|\cos x| + C$ |
| $\int \cot x \, dx$ | $\ln|\sin x| + C$ |
| $\int \sec x \, dx$ | $\ln|\sec x + \tan x| + C$ |
| $\int \csc x \, dx$ | $\ln|\csc x - \cot x| + C$ |
| $\int \frac{1}{\sqrt{x^2+a^2}} \, dx$ | $\ln|x + \sqrt{x^2+a^2}| + C$ |
| $\int \frac{1}{\sqrt{x^2-a^2}} \, dx$ | $\ln|x + \sqrt{x^2-a^2}| + C$（$|x|>a$） |

---

## 三、换元积分法

### 3.1 第一类换元法（凑微分法）

<span style="background-color: #8db3e2">**定理**</span> 若 $\int f(u) \, du = F(u) + C$，且 $u = \varphi(x)$ 可导，则

$$\int f(\varphi(x))\varphi'(x) \, dx = \int f(u) \, du = F(u) + C = F(\varphi(x)) + C$$

**常用凑微分形式**：
- $\sin x \, dx = -d(\cos x)$
- $\cos x \, dx = d(\sin x)$
- $\frac{1}{x} \, dx = d(\ln|x|)$
- $\frac{1}{x^2} \, dx = -d(\frac{1}{x})$
- $e^x \, dx = d(e^x)$
- $x^n \, dx = \frac{1}{n+1} d(x^{n+1})$

### 3.2 第二类换元法

<span style="background-color: #8db3e2">**定理**</span> 若 $x = \varphi(t)$ 单调可导，$\varphi'(t) \neq 0$，且 $\int f(\varphi(t))\varphi'(t) \, dt = F(t) + C$，则

$$\int f(x) \, dx = F(\varphi^{-1}(x)) + C$$

**常用代换**：
- **三角代换**：$\sqrt{a^2-x^2}$ → $x = a\sin t$ 或 $x = a\cos t$
- **根号代换**：$\sqrt{x^2-a^2}$ → $x = a\sec t$
- **倒代换**：$x = \frac{1}{t}$

---

## 四、分部积分法

<span style="background-color: #8db3e2">**定理（分部积分公式）**</span> 若 $u(x)$ 和 $v(x)$ 可导，则

$$\int u \, dv = uv - \int v \, du$$

**选取 $u$ 的原则**（LIPTE 法则）：
1. **L** - 对数函数：$\ln x$，$\log_a x$
2. **I** - 反三角函数：$\arctan x$，$\arcsin x$
3. **P** - 幂函数：$x^n$
4. **T** - 三角函数：$\sin x$，$\cos x$
5. **E** - 指数函数：$e^x$，$a^x$

**优先选取顺序**：L > I > P > T > E

**常见类型**：
- $\int x^n e^x \, dx$：选 $u = x^n$，$dv = e^x dx$
- $\int x^n \ln x \, dx$：选 $u = \ln x$，$dv = x^n dx$
- $\int x^n \sin x \, dx$：选 $u = x^n$，$dv = \sin x dx$
- $\int e^x \sin x \, dx$：需要两次分部积分后移项

---

## 五、有理函数积分

### 5.1 有理函数的概念

<span style="background-color: #ccc1d9">**定义（有理函数）**</span> 两个多项式的商 $P(x)/Q(x)$ 称为**有理函数**，其中 $Q(x) \neq 0$。

### 5.2 部分分式分解

**分解步骤**：
1. 分子次数小于分母次数（真分式），否则做多项式除法
2. 将分母分解为一次因式和二次质因式的乘积
3. 根据分母因式写出部分分式的一般形式
4. 求出待定系数

**基本形式**：
- $\frac{A}{x-a}$ → 积分结果为 $A\ln|x-a|$
- $\frac{A}{(x-a)^n}$ → 积分结果为 $-\frac{A}{n-1}\frac{1}{(x-a)^{n-1}}$
- $\frac{Ax+B}{x^2+px+q}$ → 配方后分解

---

## 六、三角函数有理式积分

### 6.1 基本思路

利用三角恒等变形和万能公式，将三角函数有理式转化为有理函数积分。

### 6.2 常用技巧

**降幂公式**：
- $\sin^2 x = \frac{1-\cos 2x}{2}$
- $\cos^2 x = \frac{1+\cos 2x}{2}$

**积化和差与和差化积**

**万能公式**：设 $t = \tan\frac{x}{2}$，则
$$\sin x = \frac{2t}{1+t^2}, \quad \cos x = \frac{1-t^2}{1+t^2}, \quad dx = \frac{2}{1+t^2}dt$$

---

## 七、定积分的概念与性质

### 7.1 定积分的定义

<span style="background-color: #ccc1d9">**定义（定积分）**</span> 设 $f(x)$ 在 $[a,b]$ 上有界，将区间 $[a,b]$ 分成 $n$ 份，取近似求和，取极限得

$$\int_a^b f(x) \, dx = \lim_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i)\Delta x_i$$

其中 $\lambda = \max\{\Delta x_i\}$。

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，则 $f(x)$ 在 $[a,b]$ 上可积。

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在 $[a,b]$ 上有界且只有有限个间断点，则 $f(x)$ 在 $[a,b]$ 上可积。

### 7.2 定积分的性质

<span style="background-color: #8db3e2">**定理（线性运算）**</span>
$$\int_a^b [kf(x) + mg(x)] \, dx = k\int_a^b f(x) \, dx + m\int_a^b g(x) \, dx$$

<span style="background-color: #8db3e2">**定理（区间可加）**</span>
$$\int_a^b f(x) \, dx = \int_a^c f(x) \, dx + \int_c^b f(x) \, dx$$

<span style="background-color: #8db3e2">**定理（保号性）**</span> 若 $f(x) \geq 0$，则 $\int_a^b f(x) \, dx \geq 0$。

<span style="background-color: #8db3e2">**定理（估值定理）**</span> 若 $m \leq f(x) \leq M$，则
$$m(b-a) \leq \int_a^b f(x) \, dx \leq M(b-a)$$

---

## 八、定积分中值定理

<span style="background-color: #8db3e2">**定理（积分中值定理）**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，则存在 $\xi \in [a,b]$，使得

$$\int_a^b f(x) \, dx = f(\xi)(b-a)$$

<span style="background-color: #8db3e2">**定理（积分第一中值定理）**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，$g(x)$ 在 $[a,b]$ 上可积且不变号，则存在 $\xi \in [a,b]$，使得

$$\int_a^b f(x)g(x) \, dx = f(\xi)\int_a^b g(x) \, dx$$

---

## 九、积分上限的函数及其导数

### 9.1 变上限积分

<span style="background-color: #ccc1d9">**定义（变上限积分）**</span> 若 $f(x)$ 在 $[a,b]$ 上可积，则称

$$\Phi(x) = \int_a^x f(t) \, dt \quad (a \leq x \leq b)$$

为**变上限积分函数**。

### 9.2 变上限积分的导数

<span style="background-color: #8db3e2">**定理（变上限积分求导）**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，则 $\Phi(x)$ 在 $[a,b]$ 上可导，且

$$\Phi'(x) = \frac{d}{dx}\int_a^x f(t) \, dt = f(x)$$

**推广公式**：
- $\frac{d}{dx}\int_a^{\varphi(x)} f(t) \, dt = f(\varphi(x))\varphi'(x)$
- $\frac{d}{dx}\int_{\psi(x)}^{\varphi(x)} f(t) \, dt = f(\varphi(x))\varphi'(x) - f(\psi(x))\psi'(x)$

---

## 十、牛顿-莱布尼茨公式

<span style="background-color: #8db3e2">**定理（牛顿-莱布尼茨公式）**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，$F(x)$ 是 $f(x)$ 的一个原函数，则

$$\int_a^b f(x) \, dx = F(b) - F(a)$$

**注意**：使用牛顿-莱布尼茨公式时，原函数必须存在且连续。

---

## 十一、定积分的换元法和分部积分法

### 11.1 换元法

<span style="background-color: #8db3e2">**定理**</span> 若 $f(x)$ 在 $[a,b]$ 上连续，$x = \varphi(t)$ 满足：
1. $\varphi(\alpha) = a$，$\varphi(\beta) = b$
2. $\varphi(t)$ 在 $[\alpha,\beta]$（或 $[\beta,\alpha]$）上有连续导数
3. $f(\varphi(t))\varphi'(t)$ 连续

则
$$\int_a^b f(x) \, dx = \int_\alpha^\beta f(\varphi(t))\varphi'(t) \, dt$$

### 11.2 分部积分法

<span style="background-color: #8db3e2">**定理**</span> 若 $u(x)$ 和 $v(x)$ 在 $[a,b]$ 上有连续导数，则

$$\int_a^b u \, dv = uv\bigg|_a^b - \int_a^b v \, du$$

---

## 十二、反常积分

### 12.1 无穷区间上的反常积分

<span style="background-color: #ccc1d9">**定义（无穷限反常积分）**</span>
- $\int_a^{+\infty} f(x) \, dx = \lim_{b \to +\infty}\int_a^b f(x) \, dx$
- $\int_{-\infty}^{b} f(x) \, dx = \lim_{a \to -\infty}\int_a^b f(x) \, dx$
- $\int_{-\infty}^{+\infty} f(x) \, dx = \int_{-\infty}^{c} f(x) \, dx + \int_c^{+\infty} f(x) \, dx$

**敛散性判别**：
- $\int_1^{+\infty} \frac{1}{x^p} \, dx$：$p>1$ 时收敛，$p \leq 1$ 时发散
- $\int_a^{+\infty} e^{kx} \, dx$：$k<0$ 时收敛，$k \geq 0$ 时发散

### 12.2 无界函数的反常积分

<span style="background-color: #ccc1d9">**定义（无界函数反常积分）**</span> 若 $f(x)$ 在 $x=b$ 的邻域内无界，则

$$\int_a^b f(x) \, dx = \lim_{\varepsilon \to 0^+}\int_a^{b-\varepsilon} f(x) \, dx$$

**敛散性判别**：
- $\int_a^b \frac{1}{(x-a)^p} \, dx$：$p<1$ 时收敛，$p \geq 1$ 时发散
- $\int_a^b \frac{1}{(b-x)^p} \, dx$：$p<1$ 时收敛，$p \geq 1$ 时发散

---

## 十三、定积分的应用

### 13.1 平面图形的面积

**直角坐标系**：
- 由 $y = f(x)$，$x=a$，$x=b$ 围成：$A = \int_a^b |f(x)| \, dx$
- 由 $x = g(y)$，$y=c$，$y=d$ 围成：$A = \int_c^d |g(y)| \, dy$
- 由两曲线围成：$A = \int_a^b |f(x) - g(x)| \, dx$

**极坐标系**：
$$A = \frac{1}{2}\int_\alpha^\beta r^2(\theta) \, d\theta$$

### 13.2 体积

**旋转体体积**：
- 绕 $x$ 轴旋转：$V_x = \pi\int_a^b f^2(x) \, dx$
- 绕 $y$ 轴旋转：$V_y = 2\pi\int_a^b x|f(x)| \, dx$

**平行截面面积为已知的立体体积**：
$$V = \int_a^b S(x) \, dx$$

### 13.3 弧长

**直角坐标系**：$s = \int_a^b \sqrt{1 + [f'(x)]^2} \, dx$

**参数方程**：$s = \int_\alpha^\beta \sqrt{[x'(t)]^2 + [y'(t)]^2} \, dt$

**极坐标系**：$s = \int_\alpha^\beta \sqrt{r^2(\theta) + [r'(\theta)]^2} \, d\theta$

---

## 十四、典型例题

### 例题1：换元积分法

**题目**（660题43）：$I = \int \frac{\sqrt{x+1} + 2}{(x+1)^2 - \sqrt{x+1}} \, dx$

**思路**：先换元令 $t = \sqrt{x+1}$，将根式积分转化为有理函数积分。

**解答**：
令 $t = \sqrt{x+1}$，则 $x = t^2 - 1$，$dx = 2t \, dt$

$$I = \int \frac{t + 2}{(t^2 - 1)^2 - t} \cdot 2t \, dt = \int \frac{2t(t+2)}{(t^2-1)^2 - t} \, dt$$

分母展开后化简，利用部分分式分解求解。

**总结**：换元积分法关键在于选择合适的代换，将复杂积分转化为基本积分形式。

---

### 例题2：分部积分法

**题目**（660题47）：$\int e^{-2x}\arctan e^x \, dx$

**思路**：选取 $u = \arctan e^x$，$dv = e^{-2x}dx$。

**解答**：
$$I = \int e^{-2x}\arctan e^x \, dx = -\frac{1}{2}e^{-2x}\arctan e^x + \frac{1}{2}\int e^{-2x} \cdot \frac{e^x}{1+e^{2x}} \, dx$$

$$= -\frac{1}{2}e^{-2x}\arctan e^x + \frac{1}{2}\int \frac{e^{-x}}{1+e^{2x}} \, dx$$

令 $t = e^x$，继续计算可得最终结果。

**总结**：分部积分中，正确选取 $u$ 和 $dv$ 是解题关键。

---

### 例题3：定积分计算

**题目**（660题70）：$\int_0^{2\pi} |\sin^2 x - \cos^2 x| \, dx$

**思路**：利用周期性化简被积函数。

**解答**：
$$\sin^2 x - \cos^2 x = -\cos 2x$$

$$|\sin^2 x - \cos^2 x| = |\cos 2x|$$

在 $[0,2\pi]$ 上，$|\cos 2x|$ 的周期为 $\pi$，所以

$$\int_0^{2\pi} |\cos 2x| \, dx = 2\int_0^{\pi} |\cos 2x| \, dx = 4\int_0^{\pi/2} \cos 2x \, dx = 4 \cdot \frac{1}{2} = 2$$

**总结**：利用函数周期性和对称性可简化定积分计算。

---

### 例题4：变上限积分求导

**题目**（660题64）：$\frac{d}{dx}\left(\int_0^x \frac{\sin(x+t)}{\sqrt{x+t}} \, dt\right)$

**思路**：先换元将积分上限变成参数，再求导。

**解答**：
令 $u = x + t$，则 $t = 0 \Rightarrow u = x$，$t = x \Rightarrow u = 2x$，$dt = du$

$$I = \frac{d}{dx}\left(\int_x^{2x} \frac{\sin u}{\sqrt{u}} \, du\right) = \frac{\sin(2x)}{\sqrt{2x}} \cdot 2 - \frac{\sin x}{\sqrt{x}} \cdot 1$$

$$= \frac{2\sin(2x)}{\sqrt{2x}} - \frac{\sin x}{\sqrt{x}}$$

**总结**：变上限积分求导需注意被积函数中也含有上限变量。

---

### 例题5：反常积分敛散性

**题目**（660题62）：$\int_1^{+\infty} \frac{dx}{x\sqrt{2x^2-1}}$

**思路**：先换元化为标准形式，再判断敛散性。

**解答**：
令 $x = \frac{1}{\sqrt{2}}\sec t$，则 $dx = \frac{1}{\sqrt{2}}\sec t \tan t \, dt$

$$\int_1^{+\infty} \frac{dx}{x\sqrt{2x^2-1}} = \int_0^{\pi/2} \frac{\frac{1}{\sqrt{2}}\sec t \tan t}{\frac{1}{\sqrt{2}}\sec t \cdot \tan t} \, dt = \int_0^{\pi/2} 1 \, dt = \frac{\pi}{2}$$

**总结**：反常积分计算需先化为标准形式。

---

### 例题6：定积分应用-面积

**题目**（660题75）：星形线 $\begin{cases} x = a\cos^3 t \\ y = a\sin^3 t \end{cases}$ 所围成的面积。

**思路**：利用参数方程求面积公式。

**解答**：
$$A = 4\int_0^a y \, dx = 4\int_{\pi/2}^{0} a\sin^3 t \cdot (-3a\cos^2 t\sin t) \, dt = 12a^2\int_0^{\pi/2} \sin^4 t \cos^2 t \, dt$$

$$= 12a^2 \cdot \frac{\pi}{24} = \frac{\pi a^2}{2}$$

**总结**：参数方程求面积需注意积分上下限的确定。

---

## 十五、解题方法总结

### 15.1 不定积分计算

| 类型 | 方法 |
|------|------|
| 有理函数 | 部分分式分解 |
| 三角函数有理式 | 三角恒等变换、万能公式 |
| 根式函数 | 换元法 |
| 复合函数 | 链式法则（凑微分） |

### 15.2 定积分计算

1. **利用对称性和周期性**
2. **换元法注意积分限变化**
3. **分部积分**
4. **处理绝对值**（分段去绝对值）

### 15.3 反常积分

1. **先判断类型**：无穷限还是无界函数
2. **计算原函数**
3. **取极限判断敛散性**

---

## 十六、练习题精选

### 基础练习

1. 求 $\int \frac{x^2}{1+x^2} \, dx$。

2. 求 $\int \sin 3x \cos 2x \, dx$。

3. 计算 $\int_0^1 x e^x \, dx$。

4. 判断 $\int_0^{+\infty} \frac{\sin x}{x} \, dx$ 的敛散性。

### 提高练习

5. 求 $\int \frac{\ln x}{x\sqrt{1+\ln x}} \, dx$。

6. 计算 $\int_0^{\pi/2} \frac{\cos x}{\sin x + \cos x} \, dx$。

7. 求 $\int_1^{+\infty} \frac{dx}{x(x^2+1)}$。

8. 设 $f(x) = \int_1^{x^2} e^{-t^2} \, dt$，求 $f'(x)$。

---

## 参考答案提示

1. $x - \arctan x + C$

2. $-\frac{1}{2}\cos 5x + \frac{1}{10}\cos x + C$

3. $1$（提示：分部积分）

4. 收敛（ Dirichlet 积分）

5. $\frac{2}{3}(1+\ln x)^{3/2} - 2\sqrt{1+\ln x} + C$

6. $\frac{\pi}{4}$（提示：利用对称性）

7. $\frac{1}{2}\ln 2$（提示：部分分式分解）

8. $2xe^{-x^4}$

---

> **注**：本 Lecture 内容涵盖一元函数积分学的基本概念、计算方法和典型例题。建议结合《基础过关660题》第39-74题进行练习巩固。
