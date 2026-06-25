---
title: Lecture 57：第一类曲线积分
tags: [考研, 数学一, 高等数学, 数学, 曲线积分, 对弧长的曲线积分, 第一类曲线积分]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 57：第一类曲线积分

## 一、对弧长的曲线积分（第一类曲线积分）定义

> [!important|purple] 定义：第一类曲线积分
> 设 $L$ 为 $xOy$ 面上的光滑曲线弧，$f(x,y)$ 为定义在 $L$ 上的有界函数。将 $L$ 任意分成 $n$ 小段 $\Delta s_i$（弧长），在每小段上任取一点 $(\xi_i, \eta_i)$，作和
> $$\sum_{i=1}^n f(\xi_i, \eta_i) \Delta s_i$$
> 若当 $\lambda = \max\{\Delta s_i\} \to 0$ 时，极限存在且与分割和取点方式无关，则称此极限为 $f(x,y)$ 在曲线 $L$ 上对弧长的曲线积分，记为：
> $$\int_L f(x,y)\,ds = \lim_{\lambda \to 0} \sum_{i=1}^n f(\xi_i, \eta_i) \Delta s_i$$
>
> 其中 $L$ 为积分路径，$ds$ 为弧长微元。
>
> **物理意义：** 当 $f(x,y) = 1$ 时，$\int_L ds = s$（曲线弧长）。当 $f(x,y)$ 为线密度时，积分结果为曲线的质量。

> [!important|blue] 定理：第一类曲线积分的性质
> 1. **与路径方向无关**：$\displaystyle\int_{L(A \to B)} f\,ds = \int_{L(B \to A)} f\,ds$（这是与第二类曲线积分的关键区别！）
> 2. **线性性**：$\displaystyle\int_L (\alpha f + \beta g)\,ds = \alpha\int_L f\,ds + \beta\int_L g\,ds$
> 3. **路径可加性**：若 $L = L_1 + L_2$，则 $\displaystyle\int_L f\,ds = \int_{L_1} f\,ds + \int_{L_2} f\,ds$
> 4. **保号性**：若 $f(x,y) \ge 0$，则 $\displaystyle\int_L f\,ds \ge 0$

---

## 二、计算方法

### 方法一：参数方程法

> [!important|blue] 定理：参数方程下的计算公式
> 设曲线 $L$ 的参数方程为 $\begin{cases} x = x(t) \\ y = y(t) \end{cases}$，$t \in [\alpha, \beta]$，则
> $$\int_L f(x,y)\,ds = \int_\alpha^\beta f(x(t), y(t)) \sqrt{[x'(t)]^2 + [y'(t)]^2}\,dt$$
>
> 其中 $ds = \sqrt{[x'(t)]^2 + [y'(t)]^2}\,dt$。
>
> **三维情形：** 设 $L$ 的参数方程为 $\begin{cases} x = x(t) \\ y = y(t) \\ z = z(t) \end{cases}$，则
> $$\int_L f(x,y,z)\,ds = \int_\alpha^\beta f(x(t), y(t), z(t)) \sqrt{[x'(t)]^2 + [y'(t)]^2 + [z'(t)]^2}\,dt$$

#### 例题 1

计算 $\int_L (x^2 + y^2)\,ds$，其中 $L$ 是圆 $x^2 + y^2 = a^2$ 的上半圆（$y \ge 0$）。

**解：** 参数方程：$x = a\cos t$，$y = a\sin t$，$t \in [0, \pi]$。

$$ds = \sqrt{(-a\sin t)^2 + (a\cos t)^2}\,dt = \sqrt{a^2}\,dt = a\,dt$$

$$\int_L (x^2+y^2)\,ds = \int_0^\pi a^2 \cdot a\,dt = a^3 \int_0^\pi dt = \pi a^3$$

---

### 方法二：直角坐标法

> [!important|blue] 定理：直角坐标下的计算公式
> 若曲线 $L$ 可表示为 $y = y(x)$，$x \in [a, b]$，则
> $$\int_L f(x,y)\,ds = \int_a^b f(x, y(x)) \sqrt{1 + [y'(x)]^2}\,dx$$
>
> 其中 $ds = \sqrt{1 + [y'(x)]^2}\,dx$。
>
> 若 $L$ 表示为 $x = x(y)$，$y \in [c, d]$，则
> $$\int_L f(x,y)\,ds = \int_c^d f(x(y), y) \sqrt{1 + [x'(y)]^2}\,dy$$

#### 例题 2

计算 $\int_L \sqrt{y}\,ds$，其中 $L$ 是抛物线 $y = x^2$ 从 $(0,0)$ 到 $(1,1)$ 的一段。

**解：** $y' = 2x$，$ds = \sqrt{1 + 4x^2}\,dx$。

$$\int_L \sqrt{y}\,ds = \int_0^1 \sqrt{x^2} \cdot \sqrt{1+4x^2}\,dx = \int_0^1 x\sqrt{1+4x^2}\,dx$$

令 $u = 1 + 4x^2$，$du = 8x\,dx$：

$$= \int_1^5 \frac{1}{8}\sqrt{u}\,du = \frac{1}{8} \cdot \frac{2}{3} u^{3/2} \Big|_1^5 = \frac{1}{12}(5\sqrt{5} - 1)$$

---

### 方法三：极坐标法

> [!important|blue] 定理：极坐标下的计算公式
> 若曲线 $L$ 的极坐标方程为 $r = r(\theta)$，$\theta \in [\alpha, \beta]$，则
> $$\int_L f(x,y)\,ds = \int_\alpha^\beta f(r\cos\theta, r\sin\theta) \sqrt{r^2 + [r'(\theta)]^2}\,d\theta$$
>
> 其中 $ds = \sqrt{r^2 + [r'(\theta)]^2}\,d\theta$。

#### 例题 3

计算 $\int_L x\,ds$，其中 $L$ 是心脏线 $r = a(1 + \cos\theta)$ 的上半部分（$0 \le \theta \le \pi$）。

**解：** $r'(\theta) = -a\sin\theta$，$x = r\cos\theta = a(1+\cos\theta)\cos\theta$。

$$ds = \sqrt{r^2 + (r')^2}\,d\theta = \sqrt{a^2(1+\cos\theta)^2 + a^2\sin^2\theta}\,d\theta = a\sqrt{2(1+\cos\theta)}\,d\theta = 2a\cos\frac{\theta}{2}\,d\theta$$

$$\int_L x\,ds = \int_0^\pi a(1+\cos\theta)\cos\theta \cdot 2a\cos\frac{\theta}{2}\,d\theta$$

利用 $1 + \cos\theta = 2\cos^2\frac{\theta}{2}$：

$$= \int_0^\pi 2a\cos^2\frac{\theta}{2} \cdot \cos\theta \cdot 2a\cos\frac{\theta}{2}\,d\theta = 4a^2 \int_0^\pi \cos^3\frac{\theta}{2}\cos\theta\,d\theta$$

令 $t = \frac{\theta}{2}$：$= 8a^2 \int_0^{\pi/2} \cos^3 t \cos 2t\,dt = 8a^2 \int_0^{\pi/2} \cos^3 t (2\cos^2 t - 1)\,dt$

$= 8a^2 \left[2\int_0^{\pi/2}\cos^5 t\,dt - \int_0^{\pi/2}\cos^3 t\,dt\right]$

利用 Wallis 公式：$\int_0^{\pi/2}\cos^5 t\,dt = \frac{8}{15}$，$\int_0^{\pi/2}\cos^3 t\,dt = \frac{2}{3}$。

$= 8a^2\left[\frac{16}{15} - \frac{2}{3}\right] = 8a^2 \cdot \frac{6}{15} = \frac{16a^2}{5}$

---

## 三、奇偶性与对称性

> [!important|blue] 定理：第一类曲线积分的对称性
>
> **关于坐标轴的对称性：**
>
> 设曲线 $L$ 关于 $y$ 轴对称（左右对称），$L_1$ 为 $L$ 在 $x \ge 0$ 的部分：
> - 若 $f(x,y)$ 关于 $x$ 为**偶函数**（$f(-x,y) = f(x,y)$），则 $\displaystyle\int_L f\,ds = 2\int_{L_1} f\,ds$
> - 若 $f(x,y)$ 关于 $x$ 为**奇函数**（$f(-x,y) = -f(x,y)$），则 $\displaystyle\int_L f\,ds = 0$
>
> 设曲线 $L$ 关于 $x$ 轴对称（上下对称），$L_1$ 为 $L$ 在 $y \ge 0$ 的部分：
> - 若 $f(x,y)$ 关于 $y$ 为偶函数，则 $\displaystyle\int_L f\,ds = 2\int_{L_1} f\,ds$
> - 若 $f(x,y)$ 关于 $y$ 为奇函数，则 $\displaystyle\int_L f\,ds = 0$
>
> **轮换对称性：** 若曲线 $L$ 关于 $x, y$ 具有轮换对称性（即交换 $x, y$ 后曲线不变），则
> $$\int_L f(x,y)\,ds = \int_L f(y,x)\,ds$$
>
> 特别地，$\displaystyle\int_L x\,ds = \int_L y\,ds$，$\displaystyle\int_L x^2\,ds = \int_L y^2\,ds$。
>
> **三维轮换对称性：** 若 $L$ 关于 $x, y, z$ 轮换对称，则
> $$\int_L f(x,y,z)\,ds = \int_L f(y,z,x)\,ds = \int_L f(z,x,y)\,ds$$

#### 例题 4

计算 $\int_L (x^2 + y^2)\,ds$，其中 $L$ 是圆 $x^2 + y^2 = a^2$。

**解（利用对称性）：** 圆关于 $x, y$ 轮换对称，$\int_L x^2\,ds = \int_L y^2\,ds$。

$$\int_L (x^2+y^2)\,ds = 2\int_L x^2\,ds$$

又 $x^2 + y^2 = a^2$ 在 $L$ 上为常数，故

$$\int_L (x^2+y^2)\,ds = a^2 \int_L ds = a^2 \cdot 2\pi a = 2\pi a^3$$

#### 例题 5

计算 $\int_L x\,ds$，其中 $L$ 为椭圆 $\dfrac{x^2}{4} + y^2 = 1$。

**解：** 椭圆关于 $y$ 轴对称，$f(x,y) = x$ 关于 $x$ 是奇函数，故

$$\int_L x\,ds = 0$$

---

## 四、第一类曲线积分的应用

### 1. 曲线弧长

$$s = \int_L ds$$

### 2. 曲线的质量

设线密度为 $\rho(x,y)$，则质量 $M = \int_L \rho(x,y)\,ds$。

### 3. 曲线的质心

$$\bar{x} = \frac{\int_L x\rho\,ds}{\int_L \rho\,ds}, \quad \bar{y} = \frac{\int_L y\rho\,ds}{\int_L \rho\,ds}$$

---

## 五、典型例题汇总

#### 例题 6

计算 $\int_L xy\,ds$，其中 $L$ 是连接 $(0,0)$ 和 $(1,1)$ 的直线段。

**解：** $L$ 的方程为 $y = x$，$x \in [0,1]$。$ds = \sqrt{1+1}\,dx = \sqrt{2}\,dx$。

$$\int_L xy\,ds = \int_0^1 x \cdot x \cdot \sqrt{2}\,dx = \sqrt{2} \cdot \frac{x^3}{3}\Big|_0^1 = \frac{\sqrt{2}}{3}$$

#### 例题 7

计算 $\oint_L e^{\sqrt{x^2+y^2}}\,ds$，其中 $L$ 是圆 $x^2 + y^2 = a^2$（$\oint$ 表示闭曲线积分）。

**解：** 在 $L$ 上，$\sqrt{x^2+y^2} = a$，故 $e^{\sqrt{x^2+y^2}} = e^a$（常数）。

$$\oint_L e^{\sqrt{x^2+y^2}}\,ds = e^a \oint_L ds = e^a \cdot 2\pi a = 2\pi a e^a$$

#### 例题 8

计算 $\int_L (x + y)\,ds$，其中 $L$ 为从 $A(1,0)$ 沿 $x^2 + y^2 = 1$ 到 $B(0,1)$ 的四分之一圆弧。

**解：** 参数方程 $x = \cos t$，$y = \sin t$，$t \in [0, \frac{\pi}{2}]$，$ds = dt$。

$$\int_L (x+y)\,ds = \int_0^{\pi/2} (\cos t + \sin t)\,dt = [\sin t - \cos t]_0^{\pi/2} = (1-0) - (0-1) = 2$$

---

## 六、易错点总结

> 1. **第一类曲线积分与方向无关**：$\int_L f\,ds$ 的值不因改变积分方向而改变。这与第二类曲线积分不同。
> 2. **$ds$ 永远为正**：$ds = \sqrt{(x')^2 + (y')^2}\,dt$，根号恒取正值。即使参数 $t$ 减小，$ds$ 仍为正。
> 3. **利用对称性时注意判断奇偶性的变量**：关于 $y$ 轴对称时，看 $f$ 关于 $x$ 是否为奇/偶函数。
> 4. **参数化时的取值范围**：要保证参数恰好遍历整条曲线（不遗漏、不重复）。
> 5. **圆上的简化**：在圆 $x^2 + y^2 = a^2$ 上，$x^2 + y^2 = a^2$ 是常数，可以直接提出。类似地，在给定曲线上，利用曲线方程简化被积函数。
> 6. **计算 $ds$ 不要忘记开根号**：$ds = \sqrt{(x')^2 + (y')^2}\,dt$，不是 $(x')^2 + (y')^2$。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 58：第二类曲线积分]] — 第二类
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/10-向量代数与空间解析几何/Lecture 53：向量代数]] — 向量
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 31：定积分的基本概念]] — 定积分
