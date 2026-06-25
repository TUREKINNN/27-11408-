---
title: Lecture 59：第一类曲面积分
tags: [考研, 数学一, 高等数学, 数学, 曲面积分, 对面积的曲面积分, 第一类曲面积分]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 59：第一类曲面积分

## 一、对面积的曲面积分（第一类曲面积分）定义

> [!important|purple] 定义：第一类曲面积分
> 设 $\Sigma$ 为光滑曲面，$f(x,y,z)$ 为定义在 $\Sigma$ 上的有界函数。将 $\Sigma$ 任意分成 $n$ 小块 $\Delta S_i$（面积），在每小块上任取一点 $(\xi_i, \eta_i, \zeta_i)$，作和
> $$\sum_{i=1}^n f(\xi_i, \eta_i, \zeta_i) \Delta S_i$$
> 若当 $\lambda = \max\{\Delta S_i$ 的直径$\} \to 0$ 时极限存在，则记为：
> $$\iint_\Sigma f(x,y,z)\,dS = \lim_{\lambda \to 0} \sum_{i=1}^n f(\xi_i, \eta_i, \zeta_i) \Delta S_i$$
>
> 其中 $dS$ 为面积微元。
>
> **物理意义：** 当 $f \equiv 1$ 时，$\iint_\Sigma dS = S$（曲面面积）。当 $f$ 为面密度时，积分为曲面质量。

> [!important|blue] 定理：第一类曲面积分的性质
> 1. **与曲面的侧无关**：$\displaystyle\iint_\Sigma f\,dS$ 不因改变法向量方向而变化（这是与第二类的关键区别！）
> 2. **线性性**、**曲面可加性**同前。
> 3. 若 $\Sigma = \Sigma_1 + \Sigma_2$，则 $\displaystyle\iint_\Sigma f\,dS = \iint_{\Sigma_1} f\,dS + \iint_{\Sigma_2} f\,dS$

---

## 二、计算方法：投影法

> [!important|blue] 定理：投影法计算公式
> 若曲面 $\Sigma$ 的方程为 $z = z(x,y)$，$(x,y) \in D_{xy}$（$D_{xy}$ 为 $\Sigma$ 在 $xOy$ 面上的投影区域），则
> $$\iint_\Sigma f(x,y,z)\,dS = \iint_{D_{xy}} f(x, y, z(x,y)) \sqrt{1 + z_x^2 + z_y^2}\,dxdy$$
>
> 其中面积微元 $dS = \sqrt{1 + z_x^2 + z_y^2}\,dxdy$。
>
> **同理：** 若 $\Sigma$ 表示为 $x = x(y,z)$，投影到 $yOz$ 面：
> $$\iint_\Sigma f\,dS = \iint_{D_{yz}} f(x(y,z), y, z) \sqrt{1 + x_y^2 + x_z^2}\,dydz$$
>
> 若 $\Sigma$ 表示为 $y = y(x,z)$，投影到 $xOz$ 面：
> $$\iint_\Sigma f\,dS = \iint_{D_{xz}} f(x, y(x,z), z) \sqrt{1 + y_x^2 + y_z^2}\,dxdz$$

#### 例题 1

计算 $\iint_\Sigma z\,dS$，其中 $\Sigma$ 是锥面 $z = \sqrt{x^2 + y^2}$ 在 $0 \le z \le 1$ 的部分。

**解：** $z_x = \dfrac{x}{\sqrt{x^2+y^2}}$，$z_y = \dfrac{y}{\sqrt{x^2+y^2}}$。

$$\sqrt{1 + z_x^2 + z_y^2} = \sqrt{1 + \frac{x^2}{x^2+y^2} + \frac{y^2}{x^2+y^2}} = \sqrt{2}$$

投影区域 $D_{xy}$：$x^2 + y^2 \le 1$（$z \le 1$ 时）。

$$\iint_\Sigma z\,dS = \iint_{D_{xy}} \sqrt{x^2+y^2} \cdot \sqrt{2}\,dxdy = \sqrt{2}\int_0^{2\pi}\int_0^1 r \cdot r\,drd\theta = \sqrt{2} \cdot 2\pi \cdot \frac{1}{3} = \frac{2\sqrt{2}\pi}{3}$$

---

#### 例题 2

计算 $\iint_\Sigma (x^2 + y^2)\,dS$，其中 $\Sigma$ 是球面 $x^2 + y^2 + z^2 = a^2$。

**解：** 利用球面的对称性。球面关于 $x, y, z$ 轮换对称，故

$$\iint_\Sigma x^2\,dS = \iint_\Sigma y^2\,dS = \iint_\Sigma z^2\,dS$$

$$\iint_\Sigma (x^2+y^2+z^2)\,dS = a^2 \iint_\Sigma dS = a^2 \cdot 4\pi a^2 = 4\pi a^4$$

$$\iint_\Sigma x^2\,dS = \frac{4\pi a^4}{3}$$

$$\iint_\Sigma (x^2+y^2)\,dS = \frac{8\pi a^4}{3}$$

---

#### 例题 3

计算 $\iint_\Sigma \dfrac{1}{z}\,dS$，其中 $\Sigma$ 是球面 $x^2 + y^2 + z^2 = a^2$ 在 $z \ge \dfrac{a}{2}$ 的部分。

**解：** 上半球面 $z = \sqrt{a^2 - x^2 - y^2}$，$z_x = \dfrac{-x}{z}$，$z_y = \dfrac{-y}{z}$。

$$\sqrt{1 + z_x^2 + z_y^2} = \sqrt{1 + \frac{x^2+y^2}{z^2}} = \frac{\sqrt{x^2+y^2+z^2}}{z} = \frac{a}{z}$$

投影区域 $D_{xy}$：$x^2 + y^2 \le a^2 - \dfrac{a^2}{4} = \dfrac{3a^2}{4}$。

$$\iint_\Sigma \frac{1}{z}\,dS = \iint_{D_{xy}} \frac{1}{z} \cdot \frac{a}{z}\,dxdy = a\iint_{D_{xy}} \frac{1}{z^2}\,dxdy = a\iint_{D_{xy}} \frac{1}{a^2 - x^2 - y^2}\,dxdy$$

极坐标：$= a\int_0^{2\pi}\int_0^{\frac{\sqrt{3}a}{2}} \frac{r}{a^2-r^2}\,drd\theta = 2\pi a \left[-\frac{1}{2}\ln(a^2-r^2)\right]_0^{\frac{\sqrt{3}a}{2}}$

$= -\pi a \left[\ln\left(a^2 - \frac{3a^2}{4}\right) - \ln a^2\right] = -\pi a \left[\ln\frac{a^2}{4} - \ln a^2\right] = -\pi a \ln\frac{1}{4} = 2\pi a\ln 2$

---

## 三、奇偶性与对称性

> [!important|blue] 定理：第一类曲面积分的对称性
>
> **关于坐标面的对称性：**
>
> 设 $\Sigma$ 关于 $xOy$ 平面对称（即上下对称），$\Sigma_1$ 为上半部分：
> - 若 $f(x,y,z)$ 关于 $z$ 为**偶函数**（$f(x,y,-z) = f(x,y,z)$），则 $\displaystyle\iint_\Sigma f\,dS = 2\iint_{\Sigma_1} f\,dS$
> - 若 $f(x,y,z)$ 关于 $z$ 为**奇函数**（$f(x,y,-z) = -f(x,y,z)$），则 $\displaystyle\iint_\Sigma f\,dS = 0$
>
> 类似地，关于 $yOz$、$xOz$ 平面对称时分别判断 $f$ 关于 $x$、$y$ 的奇偶性。
>
> **轮换对称性：** 若曲面 $\Sigma$ 关于 $x, y, z$ 轮换对称（如球面 $x^2+y^2+z^2 = a^2$），则
> $$\iint_\Sigma f(x,y,z)\,dS = \iint_\Sigma f(y,z,x)\,dS = \iint_\Sigma f(z,x,y)\,dS$$
>
> 特别地：$\displaystyle\iint_\Sigma x\,dS = \iint_\Sigma y\,dS = \iint_\Sigma z\,dS$，$\displaystyle\iint_\Sigma x^2\,dS = \iint_\Sigma y^2\,dS = \iint_\Sigma z^2\,dS$。

#### 例题 4

计算 $\iint_\Sigma xyz\,dS$，其中 $\Sigma$ 是平面 $x + y + z = 1$ 在第一卦限的部分。

**解：** $z = 1 - x - y$，$z_x = -1$，$z_y = -1$，$\sqrt{1+1+1} = \sqrt{3}$。

$D_{xy}$：$x \ge 0$，$y \ge 0$，$x + y \le 1$。

$$\iint_\Sigma xyz\,dS = \iint_{D_{xy}} xy(1-x-y)\sqrt{3}\,dxdy = \sqrt{3}\int_0^1\int_0^{1-x} xy(1-x-y)\,dydx$$

$$= \sqrt{3}\int_0^1 x\left[\frac{(1-x)y^2}{2} - \frac{y^3}{3}\right]_0^{1-x} dx = \sqrt{3}\int_0^1 x \cdot \frac{(1-x)^3}{6}\,dx$$

$$= \frac{\sqrt{3}}{6}\int_0^1 x(1-x)^3\,dx = \frac{\sqrt{3}}{6} \cdot \frac{1}{20} = \frac{\sqrt{3}}{120}$$

---

#### 例题 5

计算 $\iint_\Sigma (x + y + z)\,dS$，其中 $\Sigma$ 为球面 $x^2 + y^2 + z^2 = a^2$。

**解：** 球面关于 $x, y, z$ 轮换对称，故 $\iint_\Sigma x\,dS = \iint_\Sigma y\,dS = \iint_\Sigma z\,dS$。

又球面关于 $xOy$ 平面对称，$z$ 关于 $z$ 是奇函数，故 $\iint_\Sigma z\,dS = 0$。

因此 $\iint_\Sigma x\,dS = \iint_\Sigma y\,dS = \iint_\Sigma z\,dS = 0$。

$$\iint_\Sigma (x+y+z)\,dS = 0$$

---

## 四、第一类曲面积分的应用

### 曲面的面积

$$S = \iint_\Sigma dS = \iint_{D_{xy}} \sqrt{1 + z_x^2 + z_y^2}\,dxdy$$

### 曲面的质量

设面密度 $\rho(x,y,z)$，则 $M = \iint_\Sigma \rho\,dS$。

### 曲面的质心

$$\bar{x} = \frac{\iint_\Sigma x\rho\,dS}{\iint_\Sigma \rho\,dS}, \quad \bar{y} = \frac{\iint_\Sigma y\rho\,dS}{\iint_\Sigma \rho\,dS}, \quad \bar{z} = \frac{\iint_\Sigma z\rho\,dS}{\iint_\Sigma \rho\,dS}$$

---

## 五、典型例题汇总

#### 例题 6

计算 $\iint_\Sigma (x^2 + y^2)\,dS$，其中 $\Sigma$ 为锥面 $z = \sqrt{x^2+y^2}$ 被 $z = 1$ 截下的部分。

**解：** $z_x = \dfrac{x}{\sqrt{x^2+y^2}}$，$z_y = \dfrac{y}{\sqrt{x^2+y^2}}$，$\sqrt{1+z_x^2+z_y^2} = \sqrt{2}$。

$D_{xy}$：$x^2+y^2 \le 1$。

$$\iint_\Sigma (x^2+y^2)\,dS = \iint_{D_{xy}} (x^2+y^2)\sqrt{2}\,dxdy = \sqrt{2}\int_0^{2\pi}\int_0^1 r^2 \cdot r\,drd\theta = \sqrt{2} \cdot 2\pi \cdot \frac{1}{4} = \frac{\sqrt{2}\pi}{2}$$

#### 例题 7

计算 $\iint_\Sigma z^2\,dS$，其中 $\Sigma$ 为柱面 $x^2 + y^2 = a^2$ 介于 $z = 0$ 和 $z = h$ 之间的部分。

**解：** 柱面不能直接表示为 $z = f(x,y)$。用参数方程：$x = a\cos\theta$，$y = a\sin\theta$，$z = z$，$\theta \in [0, 2\pi]$，$z \in [0, h]$。

$$dS = a\,d\theta\,dz$$

$$\iint_\Sigma z^2\,dS = \int_0^{2\pi}\int_0^h z^2 \cdot a\,dzd\theta = a \cdot 2\pi \cdot \frac{h^3}{3} = \frac{2\pi ah^3}{3}$$

---

## 六、易错点总结

> 1. **第一类曲面积分与曲面的侧无关**：无论法向量取哪个方向，$\iint_\Sigma f\,dS$ 的值不变。
> 2. **面积微元 $dS$ 恒为正**：$dS = \sqrt{1+z_x^2+z_y^2}\,dxdy > 0$，这与第二类曲面积分中 $dxdy$ 可正可负不同。
> 3. **投影法选择合适的投影面**：应选择使投影区域简单、$\sqrt{1+z_x^2+z_y^2}$ 易算的投影面。柱面通常投影到坐标面上不方便，用参数方程更简洁。
> 4. **利用对称性时**：关于 $xOy$ 平面对称，看 $f$ 关于 $z$ 的奇偶性；轮换对称性适用于球面、正四面体面等高度对称的曲面。
> 5. **$dS$ 与 $dxdy$ 的关系**：$dS = \sqrt{1+z_x^2+z_y^2}\,dxdy$，不能漏掉根号因子。
> 6. **球面上的简化**：在球面 $x^2+y^2+z^2 = a^2$ 上，$x^2+y^2+z^2 = a^2$ 是常数，可直接用。类似地利用曲面方程简化被积函数。
> 7. **投影区域的确定**：要根据曲面的范围（如 $z \ge 0$）确定投影区域，不是简单地取整个截面。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 60：第二类曲面积分]] — 第二类
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 57：第一类曲线积分]] — 曲线积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 44：二重积分]] — 二重积分
