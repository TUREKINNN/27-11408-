---
title: "Lecture 46：三重积分"
chapter: "08-重积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 三重积分, 柱坐标, 球坐标]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 46：三重积分

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（数一必考，解答题常考） |
| **分值分布** | 约 10-12 分 |
| **题型** | 三重积分的计算（直角坐标、柱坐标、球坐标） |
| **难度** | 中等偏难 |

---

## 一、三重积分的定义

> 设 $f(x, y, z)$ 在空间有界闭区域 $\Omega$ 上有界，将 $\Omega$ 任意分割为 $n$ 个小区域 $\Delta v_i$，在每个小区域内任取一点 $(\xi_i, \eta_i, \zeta_i)$，若极限：
>
> $$\lim_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i, \eta_i, \zeta_i) \Delta v_i$$
>
> 存在（$\lambda$ 为各小区域直径的最大值），则称此极限为 $f$ 在 $\Omega$ 上的三重积分：
>
> $$\boxed{\iiint_\Omega f(x, y, z)\,dv}$$

**物理意义**：当 $f(x, y, z) = 1$ 时，$\displaystyle\iiint_\Omega dv = V$（$\Omega$ 的体积）。

---

## 二、直角坐标下的计算

### 2.1 先一后二法（投影法）

> 将 $\Omega$ 投影到 $xOy$ 面得投影区域 $D_{xy}$，对 $(x, y) \in D_{xy}$，$z$ 的范围为 $z_1(x, y) \le z \le z_2(x, y)$：
>
> $$\boxed{\iiint_\Omega f\,dv = \iint_{D_{xy}} \left[\int_{z_1(x,y)}^{z_2(x,y)} f(x,y,z)\,dz\right] d\sigma}$$
>
> 先算内层的单积分（$x, y$ 固定），再算外层的二重积分。

### 2.2 先二后一法（截面法）

> 用平面 $z = z_0$ 截 $\Omega$ 得截面 $D(z)$，若 $z$ 的范围为 $c_1 \le z \le c_2$：
>
> $$\boxed{\iiint_\Omega f\,dv = \int_{c_1}^{c_2} \left[\iint_{D(z)} f(x,y,z)\,d\sigma\right] dz}$$
>
> 先算截面上的二重积分，再对 $z$ 积分。

> 1. 被积函数只含 $z$（不含 $x, y$），如 $f(z)$
> 2. 截面 $D(z)$ 的面积容易求出（如圆形截面）
> 3. 用投影法时内层积分困难

### 2.3 经典例题

**【例1】** 计算 $\displaystyle\iiint_\Omega z\,dv$，其中 $\Omega$ 由 $z = x^2 + y^2$ 和 $z = 1$ 围成。

**解（投影法）**：$\Omega$ 在 $xOy$ 面的投影为 $D: x^2 + y^2 \le 1$。

$$\iiint_\Omega z\,dv = \iint_D \left[\int_{x^2+y^2}^1 z\,dz\right] d\sigma = \iint_D \frac{1 - (x^2+y^2)^2}{2}\,d\sigma$$

用极坐标：

$$= \int_0^{2\pi} d\theta \int_0^1 \frac{1-r^4}{2} \cdot r\,dr = 2\pi \cdot \frac{1}{2}\int_0^1 (r - r^5)\,dr$$

$$= \pi\left(\frac{1}{2} - \frac{1}{6}\right) = \frac{\pi}{3} \quad \square$$

**解（截面法）**：用 $z = c$（$0 \le c \le 1$）截 $\Omega$，截面 $D(z): x^2 + y^2 \le z$（圆面积 $\pi z$）。

$$\iiint_\Omega z\,dv = \int_0^1 z \cdot \pi z\,dz = \pi\int_0^1 z^2\,dz = \frac{\pi}{3} \quad \square$$

---

## 三、柱坐标

### 3.1 柱坐标变换

> $$x = r\cos\theta, \quad y = r\sin\theta, \quad z = z$$
>
> 体积元素：$\boxed{dv = r\,dr\,d\theta\,dz}$
>
> $$\iiint_\Omega f(x,y,z)\,dv = \iiint_{\Omega'} f(r\cos\theta, r\sin\theta, z) \cdot r\,dr\,d\theta\,dz$$

> 1. 积分区域 $\Omega$ 是**柱体**、**锥体**或由旋转曲面围成
> 2. 被积函数含 $x^2 + y^2$、$\dfrac{y}{x}$ 等形式
> 3. $\Omega$ 在 $xOy$ 面的投影为圆域

### 3.2 柱坐标下积分限的确定

> 1. 确定 $\theta$ 的范围（通常是 $[0, 2\pi]$ 或其子区间）
> 2. 确定 $r$ 的范围（投影区域在极坐标下的表示）
> 3. 确定 $z$ 的范围（下曲面 $z_1(r, \theta) \le z \le$ 上曲面 $z_2(r, \theta)$）

### 3.3 经典例题

**【例2】** 计算 $\displaystyle\iiint_\Omega (x^2 + y^2)\,dv$，其中 $\Omega: x^2 + y^2 \le z \le 2$。

**解**：用柱坐标，$\Omega$ 的投影为 $D: x^2 + y^2 \le 2$，即 $0 \le r \le \sqrt{2}$，$0 \le \theta \le 2\pi$。

$z$ 的范围：$r^2 \le z \le 2$。

$$\iiint_\Omega (x^2+y^2)\,dv = \int_0^{2\pi} d\theta \int_0^{\sqrt{2}} r\,dr \int_{r^2}^2 r^2\,dz$$

$$= 2\pi \int_0^{\sqrt{2}} r^3(2 - r^2)\,dr = 2\pi \int_0^{\sqrt{2}} (2r^3 - r^5)\,dr$$

$$= 2\pi\left[\frac{r^4}{2} - \frac{r^6}{6}\right]_0^{\sqrt{2}} = 2\pi\left[\frac{4}{2} - \frac{8}{6}\right] = 2\pi\left(2 - \frac{4}{3}\right) = \frac{4\pi}{3} \quad \square$$

---

## 四、球坐标

### 4.1 球坐标变换

> $$x = \rho\sin\varphi\cos\theta, \quad y = \rho\sin\varphi\sin\theta, \quad z = \rho\cos\varphi$$
>
> 其中 $\rho \ge 0$，$0 \le \varphi \le \pi$，$0 \le \theta \le 2\pi$。
>
> 体积元素：$\boxed{dv = \rho^2\sin\varphi\,d\rho\,d\varphi\,d\theta}$
>
> $$\iiint_\Omega f\,dv = \iiint_{\Omega'} f \cdot \rho^2\sin\varphi\,d\rho\,d\varphi\,d\theta$$

> $dv = \rho^2 \sin\varphi\,d\rho\,d\varphi\,d\theta$，**三个因子缺一不可**！
>
> 记忆方法：$\rho^2\sin\varphi$ 来自雅可比行列式。

### 4.2 适用球坐标的情形

> 1. 积分区域 $\Omega$ 是**球体**或球体的一部分
> 2. 被积函数含 $x^2 + y^2 + z^2$
> 3. 区域由球面和锥面围成

### 4.3 球坐标下积分限的确定

> 1. $\theta$ 的确定：$\Omega$ 在 $xOy$ 面投影区域的角度范围
> 2. $\varphi$ 的确定：从正 $z$ 轴开始量起的天顶角
> 3. $\rho$ 的确定：从原点出发的射线穿入和穿出 $\Omega$ 的距离
>
> 若原点在 $\Omega$ 内部，$\rho$ 的下限为 $0$。

**常见区域的球坐标表示**：

| 区域 | 球坐标表示 |
|------|-----------|
| 球 $x^2+y^2+z^2 \le R^2$ | $0 \le \rho \le R, 0 \le \varphi \le \pi, 0 \le \theta \le 2\pi$ |
| 上半球 $x^2+y^2+z^2 \le R^2, z \ge 0$ | $0 \le \rho \le R, 0 \le \varphi \le \frac{\pi}{2}, 0 \le \theta \le 2\pi$ |
| 锥面 $z = \sqrt{x^2+y^2}$ 的内部 | $\varphi = \frac{\pi}{4}$（锥面的半顶角） |

### 4.4 经典例题

**【例3】** 计算 $\displaystyle\iiint_\Omega (x^2 + y^2 + z^2)\,dv$，其中 $\Omega: x^2 + y^2 + z^2 \le R^2$。

**解**：球坐标

$$\iiint_\Omega (x^2+y^2+z^2)\,dv = \int_0^{2\pi} d\theta \int_0^\pi \sin\varphi\,d\varphi \int_0^R \rho^2 \cdot \rho^2\,d\rho$$

$$= 2\pi \cdot [-\cos\varphi]_0^\pi \cdot \frac{R^5}{5} = 2\pi \cdot 2 \cdot \frac{R^5}{5} = \frac{4\pi R^5}{5} \quad \square$$

**【例4】** 计算 $\displaystyle\iiint_\Omega z\,dv$，其中 $\Omega$ 由 $z \ge \sqrt{x^2+y^2}$ 和 $x^2+y^2+z^2 \le 1$（$z \ge 0$）围成。

**解**：$\Omega$ 是上半球体被锥面 $z = \sqrt{x^2+y^2}$ 截下的部分。

锥面 $z = \sqrt{x^2+y^2}$ 在球坐标下 $\varphi = \dfrac{\pi}{4}$。

$$\iiint_\Omega z\,dv = \int_0^{2\pi} d\theta \int_0^{\pi/4} \sin\varphi\,d\varphi \int_0^1 \rho\cos\varphi \cdot \rho^2\sin\varphi\,d\rho$$

$$= 2\pi \int_0^{\pi/4} \sin^2\varphi\cos\varphi\,d\varphi \int_0^1 \rho^3\,d\rho$$

$$= 2\pi \cdot \frac{\sin^3\varphi}{3}\bigg|_0^{\pi/4} \cdot \frac{1}{4} = 2\pi \cdot \frac{1}{3}\left(\frac{\sqrt{2}}{2}\right)^3 \cdot \frac{1}{4}$$

$$= 2\pi \cdot \frac{1}{3} \cdot \frac{\sqrt{2}}{4} \cdot \frac{1}{4} = \frac{\pi\sqrt{2}}{24} \quad \square$$

---

## 五、利用对称性简化三重积分

### 5.1 对称性

> 若 $\Omega$ 关于 $xOy$ 面对称，$\Omega_1$ 为 $\Omega$ 在 $z \ge 0$ 的部分：
>
> - 若 $f(x, y, -z) = -f(x, y, z)$（关于 $z$ 为奇函数）：$\displaystyle\iiint_\Omega f\,dv = 0$
> - 若 $f(x, y, -z) = f(x, y, z)$（关于 $z$ 为偶函数）：$\displaystyle\iiint_\Omega f\,dv = 2\iiint_{\Omega_1} f\,dv$

### 5.2 轮换对称性

> 若 $\Omega$ 关于 $x, y, z$ 具有轮换对称性（即交换任意两个变量后区域不变），则：
>
> $$\iiint_\Omega f(x)\,dv = \iiint_\Omega f(y)\,dv = \iiint_\Omega f(z)\,dv$$

**【例5】** 设 $\Omega: x^2 + y^2 + z^2 \le R^2$，计算 $\displaystyle\iiint_\Omega (x + y + z)^2\,dv$。

**解**：展开 $(x+y+z)^2 = x^2 + y^2 + z^2 + 2xy + 2xz + 2yz$。

$\Omega$ 关于各坐标面对称，$xy, xz, yz$ 关于相应变量为奇函数，积分均为 $0$。

$$\iiint_\Omega (x+y+z)^2\,dv = \iiint_\Omega (x^2+y^2+z^2)\,dv = \frac{4\pi R^5}{5} \quad \square$$

---

## 六、综合例题

**【例6】** 计算 $\displaystyle\iiint_\Omega e^{|z|}\,dv$，其中 $\Omega: x^2 + y^2 + z^2 \le 1$。

**解**：$\Omega$ 关于 $xOy$ 面对称，$e^{|z|}$ 关于 $z$ 为偶函数。

$$\iiint_\Omega e^{|z|}\,dv = 2\iiint_{\Omega_1} e^z\,dv \quad (\Omega_1: x^2+y^2+z^2 \le 1, z \ge 0)$$

用截面法：截面 $D(z): x^2 + y^2 \le 1 - z^2$，面积 $\pi(1-z^2)$。

$$= 2\int_0^1 e^z \cdot \pi(1-z^2)\,dz = 2\pi\int_0^1 (1-z^2)e^z\,dz$$

$$= 2\pi\left[(1-z^2)e^z\bigg|_0^1 + 2\int_0^1 ze^z\,dz\right]$$

$$= 2\pi\left[-1 + 2(ze^z - e^z)\bigg|_0^1\right] = 2\pi[-1 + 2(0 + 1)] = 2\pi \quad \square$$

---

## 七、考研真题精选

### 【真题1】（2020年数一·解答·10分）

**题目**：计算 $\displaystyle I = \iiint_\Omega z^2\,dv$，其中 $\Omega$ 由曲面 $x^2 + y^2 + z^2 = 2z$ 围成。

**解**：$x^2 + y^2 + z^2 = 2z$ 即 $x^2 + y^2 + (z-1)^2 = 1$，球心 $(0, 0, 1)$，半径 $1$。

用截面法：$z$ 的范围 $0 \le z \le 2$，截面 $D(z): x^2 + y^2 \le 2z - z^2$，面积 $\pi(2z - z^2)$。

$$I = \int_0^2 z^2 \cdot \pi(2z - z^2)\,dz = \pi\int_0^2 (2z^3 - z^4)\,dz$$

$$= \pi\left[\frac{z^4}{2} - \frac{z^5}{5}\right]_0^2 = \pi\left(8 - \frac{32}{5}\right) = \frac{8\pi}{5} \quad \square$$

---

## 📝 本节要点总结

| 坐标系 | 体积元素 | 适用情形 |
|--------|----------|----------|
| 直角坐标 | $dx\,dy\,dz$ | 一般区域 |
| 柱坐标 | $r\,dr\,d\theta\,dz$ | 柱体、锥体、旋转体 |
| 球坐标 | $\rho^2\sin\varphi\,d\rho\,d\varphi\,d\theta$ | 球体、球冠 |

| 方法 | 特点 |
|------|------|
| 投影法（先一后二） | 先积 $z$，再积 $xOy$ 上的二重积分 |
| 截面法（先二后一） | 先积截面，再积高度 $z$；适合 $f(z)$ 或圆截面 |

> 1. 柱坐标别忘 $r$，球坐标别忘 $\rho^2\sin\varphi$
> 2. 截面法是解决旋转体类三重积分的利器
> 3. 利用对称性可大幅简化计算——先判断再动手

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 44：二重积分]] — 二重积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 45：二重积分的计算]] — 计算
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 60：第二类曲面积分]] — 曲面积分
